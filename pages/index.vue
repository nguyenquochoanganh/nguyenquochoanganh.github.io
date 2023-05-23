<template>
	<v-sheet min-height="100vh" class="d-flex align-center justify-center">
		<v-card
			rounded="xl"
			class="ma-16"
			elevation="12"
			:width="widthCard"
			style="background: linear-gradient(75deg, #FFC107 36.9%, #ffffff 37%);"
		>
			<div class="d-flex mt-5 mx-md-5">
				<v-spacer />

				<v-tabs
					v-model="tab"
					color="#FFC107"
					right
				>
					<v-tabs-slider color="#FFC107"></v-tabs-slider>

					<v-tab
						v-for="item in items"
						:key="item.title"
						class="text-caption text-md-h6"
					>
						{{ item.title }}
					</v-tab>
				</v-tabs>
			</div>

			<v-tabs-items v-model="tab" color="transparent" style="background-color: transparent;">
				<v-tab-item
					color="transparent"
				>
					<div
						class="d-flex flex-md-row flex-column justify-center align-center"
					>
						<v-img src="https://raw.githubusercontent.com/thuanpham113/project-CV/master/static/person.png" aspect-ratio="0.9" :width="$vuetify.breakpoint.mdAndUp ? '30vw' : '60vw'" class="rounded-xl mx-5 my-6 my-md-0"></v-img>
						<div class="d-flex flex-column align-center justify-center mx-16 my-8">
							<v-spacer />
							<v-sheet max-width="500" color="transparent">
								<div class="text-h4 text-md-h3 text-center font-weight-bold">Nguyen Quoc</div>
								<div class="text-h4 text-md-h3 text-center font-weight-bold my-1">Hoang Anh</div>
								<div class="my-5 text-h6 text-md-h5 text-justify mx-auto">
									I am a student studying at University of Social Sciences and Humanities, VNU-HCMC. With the goal of seeking superior knowledge of social media marketing and developing advanced communication skills. I will gain experience to become a creative manager.
								</div>
							</v-sheet>
							<v-spacer />
							<div class="d-flex justify-end ">
								<div v-for="(icon, indexIcon) in icons" :key="indexIcon">
									<v-btn icon class="ma-4" :href="icon.href">
										<v-icon size="40">{{ icon.icon }}</v-icon>
									</v-btn>
								</div>
							</div>
						</div>
					</div>
				</v-tab-item>

				<v-tab-item>
					<div
						class="d-flex flex-md-row flex-column justify-center align-center"
					>
						<v-img src="https://raw.githubusercontent.com/thuanpham113/project-CV/master/static/infor.png" aspect-ratio="0.9" :width="$vuetify.breakpoint.mdAndUp ? '30vw' : '60vw'" class="rounded-xl mx-5 my-6 my-md-0"></v-img>
						<div class="d-flex flex-column justify-center mx-16 my-8">
							<div class="text-h3 my-3 font-weight-bold">Contact Info</div>
							<div
								v-for="(inforContacts, indexContact) in inforContacts"
								:key="indexContact"
								class="pl-6"
							>
								<v-icon>{{ inforContacts.icon }}</v-icon>
								<a :href="inforContacts.href"> {{ inforContacts.title }} </a>
							</div>
							<div class="text-h3 my-3 font-weight-bold">Education</div>
							<div
								class="d-flex pl-6 align-center"
							>
								<div class="text-h3 mr-2"> 2021 </div>
								<div>
									<div>
										Student majoring in Vietnamese studies
									</div>
									<div>
										University of Social Sciences and Humanities, VNU - HCMC
									</div>
								</div>
							</div>
							<div class="text-h3 my-3 font-weight-bold">Skills</div>

							<div
								v-for="skill in skills"
								:key="skill"
								class="pl-6"
							>
								<v-icon>mdi-star-outline</v-icon>
								{{ skill }}
							</div>
						</div>
					</div>
				</v-tab-item>

				<v-tab-item>
					<div
						class="d-flex flex-md-row flex-column justify-center align-center"
					>
						<v-img src="https://raw.githubusercontent.com/thuanpham113/project-CV/master/static/infor.png" aspect-ratio="0.9" :width="$vuetify.breakpoint.mdAndUp ? '30vw' : '60vw'" class="rounded-xl mx-5 my-6 my-md-0"></v-img>
						<div class="d-flex flex-column justify-center mx-16 my-8">
							<v-timeline
								align-top
								dense
							>
								<v-timeline-item small color="#F94A29">
									<div class="mt-1">
										Tutor | 10-2021
									</div>
									<div class="text-h5 font-weight-bold">
										Instruction for 3rd graders
									</div>
									<div>
										<ul>
											<li>
												Prepared lesson plans before class
											</li>
											<li>
												Instructed knowledge
											</li>
											<li>
												Talked, consulted with student
											</li>
										</ul>
									</div>
								</v-timeline-item>
								<v-timeline-item color="#F94A29">
									<div class="mt-2">
										Data insert | 08-2022 to 04-2023
									</div>
									<div class="text-h5 font-weight-bold">
										Synode.ai
									</div>
									<div>
										<ul>
											<li>
												Inserted data
											</li>
											<li>
												Quality assurance
											</li>
											<li>
												Maked plan weekly
											</li>
											<li>
												Trained
											</li>
										</ul>
									</div>
								</v-timeline-item>
							</v-timeline>
						</div>
					</div>
				</v-tab-item>
				<v-tab-item>
					<div
						class="d-flex flex-column justify-center align-center"
					>
						<v-img src="https://raw.githubusercontent.com/thuanpham113/project-CV/master/static/qrcode.png" aspect-ratio="1" :width="$vuetify.breakpoint.mdAndUp ? '20vw' : '60vw'" class="ma-16"></v-img>
						<div class="my-5 px-5">
							https://thuanpham113.github.io/project-CV/
						</div>
					</div>
				</v-tab-item>
			</v-tabs-items>
		</v-card>
	</v-sheet>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
	return {
		items: [
			{
				title: 'Home'
			},
			{
				title: 'About'
			},
			{
				title: 'Portfolio'
			},
			{
				title: 'Share'
			}
		],
		icons: [
			{
				icon: "mdi-facebook",
				href: "https://www.facebook.com/h.anhhh178"
			},
			{
				icon: "mdi-instagram",
				href: "https://www.instagram.com/bunboboo"
			},
			{
				icon: "mdi-email",
				href: "mailto:hganh178@gmail.com"
			},
			{
				icon: "mdi-phone",
				href: "tel:+84833775712"
			}
		],
		inforContacts:[
			{
				icon: "mdi-phone",
				title: "(08) 3377 5712",
				href: "tel:+84833775712"
			},
			{
				icon: "mdi-email",
				title: "hganh178@gmail.com",
				href: "mailto:hganh178@gmail.com"
			},{
				icon: "mdi-map-marker",
				title: "Thu Duc, HCMC",
				href: "http://maps.google.com/?q=Thu Duc, HCMC"
			}
		],
		skills: [
			"Handle situations","English communication", "Creative thinking", "Using Office Informatics: Word, Excel, Power Point, Canva"
		],
		tab: 0
	}
  },
  computed: {
	widthCard(){
		switch (this.$vuetify.breakpoint.name) {
			case "xl":
				return "1600"
				break
			case "lg":
				return "1264"
				break
			case "md":
				return "960"
				break
			case "sm":
				return "600"
				break
			default:
				return "400"
				break
		}
	}
  }
}
</script>
