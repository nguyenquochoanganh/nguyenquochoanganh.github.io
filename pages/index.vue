<template>
	<v-sheet min-height="100vh" class="d-flex align-center justify-center">
		<v-card
			rounded="xl"
			class="ma-16"
			elevation="12"
			:width="widthCard"
			style="background: linear-gradient(75deg, #FFC107 36.9%, #ffffff 37%);"
		>
			<div class="d-flex">
				<v-spacer />
				<div v-for="(item, index) in items" :key="index" class="mx-4 mt-4 text-h5">
					{{ item.title }}
				</div>
			</div>
			<div class="d-flex flex-md-row flex-column justify-center align-center">
				<v-img src="https://github.com/thuanpham113/project-CV/blob/master/static/person.png" aspect-ratio="0.9" :width="$vuetify.breakpoint.mdAndUp ? '30vw' : '60vw'" class="rounded-xl mx-5 my-6 my-md-0"></v-img>
				<div class="d-flex flex-column align-center justify-center mx-16 my-8">
					<v-spacer />
					<v-sheet max-width="500" color="transparent">
						<div class="text-h4 text-md-h3 text-center font-weight-bold">Nguyen Quoc</div>
						<div class="text-h4 text-md-h3 text-center font-weight-bold my-1">Hoang Anh</div>
						<div class="my-5 text-h6 text-md-h5 text-justify mx-auto">
							I am a student studying at University of Social Sciences and Humanities, VNU-HCMC. With the goal of seeking superior knowledge of social media marketing and developing advanced communication skills. I would like to become a creative manager.
						</div>
						<div> Read more </div>
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
		]
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
				return "1000"
				break
		}
	}
  }
}
</script>
