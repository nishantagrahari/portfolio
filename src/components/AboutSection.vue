<template>
  <div id="about-me" class="about-section">
    <div class="section q-mt-md">
      <div class="image-div lt-sm q-mb-lg">
        <q-list>
          <q-item class="q-pl-none">
            <q-item-section avatar>
              <q-avatar size="96px">
                <img
                  :src="
                    getImgUrl(
                      'assets/profile_pics/',
                      pics[randomNumber(0, pics.length - 1)]
                    )
                  "
                  alt="user image"
                />
              </q-avatar>
            </q-item-section>
            <q-item-section class="q-ml-none">
              <q-item-label class="text-h6 text-weight-bold">
                Nishant Agrahari
              </q-item-label>
              <q-item-label caption>
                agrahari.nishant007@gmail.com
              </q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </div>
      <div class="content-div">
        <div class="about-header text-h4 text-weight-bold">About Me</div>
        <div class="q-mt-md">
          <p>
            I am a <b>Software Engineer</b>. Over a period of
            <b>{{ years }}+</b> years, I have been building web applications
            with focus on making them simple and user-friendly.
          </p>
          <p>
            On my free time, I read, spend time with my friends or do courses on
            technologies that interest me.
          </p>
          <p>
            You can find me on
            <a
              href="https://www.linkedin.com/in/nishant-agrahari-bba129167/"
              target="_blank"
              rel="noopener noreferrer"
              class="href-link text-primary"
            >
              Linkedin
            </a>
            or
            <a
              href="https://github.com/nishantagrahari"
              target="_blank"
              rel="noopener noreferrer"
              class="href-link text-primary"
            >
              GitHub
            </a>
          </p>
          <p>
            <span class="sub-label">
              <q-icon name="fas fa-location-dot" size="18px" />
              Janakpur,
            </span>
            <span style="font-style: italic">Nepal</span>

            <span class="q-px-md gt-xs">
              <q-icon name="fas fa-circle" size="6px" />
            </span>

            <span class="sub-label gt-xs">
              <q-icon name="fas fa-square-envelope" size="18px" />
            </span>
            <span style="font-style: italic" class="gt-xs">
              agrahari.nishant007@gmail.com
            </span>

            <br />
            <span class="q-px-md">
              <q-icon name="fas fa-circle" size="7px" />
            </span>

            <span class="sub-label">
              <span class="gt-xs">Languages:</span>
              <q-icon
                name="fas fa-language"
                size="18px"
                style="padding-right: 2px"
                class="lt-sm"
              />
            </span>

            <span style="font-style: italic">English, Nepali, Hindi</span>
            <!-- <span class="q-px-sm">
              <q-icon name="fas fa-circle" size="3px" /> -->
            <!-- </span>
            <span style="font-style: italic">Nepali</span> -->
          </p>
        </div>
      </div>
      <div class="image-div gt-xs">
        <q-avatar size="300px">
          <img
            :src="
              getImgUrl(
                'assets/profile_pics/',
                pics[randomNumber(0, pics.length - 1)]
              )
            "
            alt="user image"
          />
        </q-avatar>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";
import { getImgUrl, randomNumber } from "../utils/helpers";

export default defineComponent({
  name: "AboutSection",

  setup() {
    return {
      years: ref(new Date().getFullYear() - 2021),
      pics: ref(["dp_primary.jpg", "dp_secondary.jpg"]),
    };
  },

  methods: {
    isHandset() {
      return screen.width <= 575 ? true : false;
    },

    getImgUrl,
    randomNumber,
  },
});
</script>

<style lang="scss" scoped>
#about-me {
  font-family: "Avenir";
  font-size: 16px;
}
.about-section {
  margin-top: 64px;
  margin-bottom: 64px;
}
.section {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}
.image-div {
  width: 40%;
  max-width: 50%;
  align-content: center;
  text-align: center;
  flex-grow: 1;
}
.content-div {
  width: 60%;
  max-width: 60%;
  margin-right: 24px;
  align-content: center;
  flex-grow: 1;
}
.href-link {
  text-decoration: none;
}
.href-link:hover {
  text-decoration: underline;
}
.sub-label {
  padding-right: 2px;
  color: #6c757d;
  font-weight: bold;
}

@media only screen and (max-width: 575px) {
  #about-me {
    font-size: 14px;
  }
  .about-section {
    margin-top: 24px;
    margin-bottom: 32px;
  }
  .section {
    flex-direction: column;
    text-align: center;
    padding: 16px;
  }
  .image-div {
    width: 100%;
    max-width: 100%;
  }
  .content-div {
    width: 100%;
    max-width: 100%;
    text-align: left;
  }
  .about-header {
    margin-top: 24px;
  }
}
</style>
