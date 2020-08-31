<template>
  <q-carousel-slide class="q-pa-none" :name="1" img-src="/statics/images/image_1.jpg">
<div class="full-height full-width flex flex-center" style="background-color: rgba(0, 0, 0, 0.68) !important;">
            <div class="custom-caption">
              <div class="text-h2 main_line animation_2"><span :style="'color:'+theme_color">{{title}}</span></div><br><br><br>
              <div class="text-h4 animation_1">{{content}}</div><br><br><br>
              <div class="animation_2">
              <!--<q-btn size="md" :style="'background:'+ theme_color +'; color: white'" label="READ MORE"/>-->
              </div>
            </div>
</div>
          </q-carousel-slide>
</template>

<script>
export default { 
  props: {
    title: {
      type: String,
      required: true
    },

    content: {
      type: String,
      default: ''
    },
  },
  data() {
            return {
                slide: 1,
		            review_slide: 'style',
                selected_tab: 't_0',
                team_slide: 1,
                bg_color: 'rgb(0, 163, 82)',
                hover: false,
                active: false,
                theme_color: 'rgb(0, 163, 82)',
                background_style: 'background-color:rgba(0, 163, 82, 0.7);',
                about_heading_1: [],
                about_heading_2: [],
                about_heading_3: [],
                about_heading_color_1: '#424242',
                about_heading_color_2: '#424242',
                about_heading_color_3: '#424242',
                page: ''
            }
        },
  mounted(){
      this.getGroupSlider()
  },
  methods: {
        getGroupSlider: function() {
                    var slider_1 = this.page.acf.group_slider_
                    this.title = slider_1.title
                    this.content = slider_1.content
                    console.log(slider_1)
                    return slider_1
        }
    },
    computed: {
            style() {
                return {
                    width: '340px',
                    height: '263px',
                    backgroundImage: `url('https://raw.githubusercontent.com/quasarframework/quasar-ui-qflashcard/dev/demo/src/statics/bgimg.jpg')`, // eslint-disable-line
                    textAlign: 'center',
                    boxShadow: '1px 1px 2px #e6e6e6',
                    display: 'inline-block'
                }
            },
    }
}
</script>
<style lang="sass" scoped>
    .main_line
      font-size: 75px;
      letter-spacing: 5px;
      line-height: 60px;
      font-weight: 600;

    .custom-caption
      text-align: center;
      padding: 12px;
      color: white;

    .animation_1
      -webkit-animation: bounceIn 1s ease-in 800ms both;
      animation: bounceIn 1s ease-in 800ms both;

    .animation_2
      -webkit-animation: flipInX 2s ease-in-out 800ms both;
      animation: flipInX 1s ease-in-out 800ms both;

    .animation_3
      -webkit-animation: lightSpeedIn 1s ease-in 800ms both;
      animation: lightSpeedIn 1s ease-in 800ms both;

    .description
      padding: 10px
      background-color: black
      color: white
      box-shadow: 1px 1px 2px #e6e6e6

    .my-header
      width: 200px
      top: 0
      height: 45px
      color: black
      background-color: rgba(255,255,255, 0.8)
      text-transform: uppercase
      text-align: center
      font-size: 17px
      margin: 20px 0 0 68px
      padding: 25px

    .my-text
      width: 100%
      top: 0
      height: 90px
      color: white
      text-align: center
      font-size: 15px
      margin: 79px 0 0 0
      padding: 20px
      line-height: normal
      font-family: Georgia, serif
      font-style: italic

    .my-button-container
      width: 100%

    .my-button
      text-decoration: none
      text-transform: uppercase
      margin: 0 0 20px 0
      text-align: center
      padding: 7px 14px
      background-color: #000
      color: #fff
      text-transform: uppercase
      box-shadow: 0 0 1px #000
      transition-delay: 0.2s

    .my-button:hover
      box-shadow: 0 0 5px #000

    .box-shadow:hover
      box-shadow: 0 10px 13px -6px rgba(0, 0, 0, 0.2), 0 20px 31px 3px rgba(0, 0, 0, 0.14), 0 8px 38px 7px rgba(0, 0, 0, 0.12) !important;

    .my-card
      width: 350px
      max-width: 350px
      margin-top: 10px

    .team-header
      width: 100%
      top: 0
      height: 45px
      color: white
      text-transform: uppercase
      text-align: center
      font-size: 17px
      margin: 60px 0 0 0
      padding: 12px

    .team-text
      width: 100%
      top: 0
      height: 90px
      color: white
      text-align: center
      font-size: 15px
      margin: 100px 0 0 0
      padding: 20px
      line-height: normal
      font-family: Georgia, serif
      font-style: italic
    
    .quote
      background: url(/statics/images/parallax.jpg);
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
      background-repeat: no-repeat;
    
    .pricing
      background: url(/statics/images/pricing.jpg);
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
      background-repeat: no-repeat;
    
    .contact_us
      background: url(/statics/images/contact_us.jpg);
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
      background-repeat: no-repeat;
    
    .custom_tab
      width: 130px;
</style>
