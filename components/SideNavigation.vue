<template>
  <div class="SideNavigation">
    <div class="SideNavigation-HeadingContainer sp-flex">
      <v-icon
        class="SideNavigation-HeadingIcon pc-none"
        :aria-label="$t('サイドメニュー項目を開く')"
        @click="openNavi"
      >
        mdi-menu
      </v-icon>
      <nuxt-link :to="localePath('/')" class="SideNavigation-HeadingLink">
        <div class="SideNavigation-Logo">
          <img src="/logo.svg" :alt="$t('兵庫県')" />
        </div>
        <h1 class="SideNavigation-Heading">
          {{ $t('新型コロナウイルス感染症') }}<br />{{ $t('対策サイト') }}
        </h1>
      </nuxt-link>
    </div>
    <v-divider class="SideNavigation-HeadingDivider" />
    <div class="sp-none" :class="{ open: isNaviOpen }">
      <v-icon
        class="SideNavigation-ListContainerIcon pc-none"
        :aria-label="$t('サイドメニュー項目を閉じる')"
        @click="closeNavi"
      >
        mdi-close
      </v-icon>
      <v-list :flat="true">
        <v-container
          v-for="(item, i) in items"
          :key="i"
          class="SideNavigation-ListItemContainer"
          @click="closeNavi"
        >
          <ListItem :link="item.link" :icon="item.icon" :title="item.title" />
          <v-divider v-show="item.divider" class="SideNavigation-Divider" />
        </v-container>
      </v-list>
      <div class="SideNavigation-LanguageMenu">
        <LanguageSelector />
      </div>
      <div class="SideNavigation-Footer">
        <!--
        <div class="SideNavigation-SocialLinkContainer">
          <a
            href="https://line.me/R/ti/p/%40822sysfc"
            target="_blank"
            rel="noopener"
          >
            <img src="/line.png" alt="LINE" />
          </a>
          <a
            href="https://twitter.com/Hyogo_bousai"
            target="_blank"
            rel="noopener"
          >
            <img src="/twitter.png" alt="Twitter" />
          </a>
          <a
            href="https://www.facebook.com/tochokoho"
            target="_blank"
            rel="noopener"
          >
            <img src="/facebook.png" alt="Facebook" />
          </a>
          <a href="https://github.com/Hyogo-metropolitan-gov/covid19">
            <img src="/github.png" alt="GitHub" />
          </a>
        </div>
// -->
        <small class="SideNavigation-Copyright">
          {{ $t('このサイトの内容物は') }}
          <a
            rel="license"
            target="_blank"
            :href="$t('https://creativecommons.org/licenses/by/4.0/deed.ja')"
          >
            {{ $t('クリエイティブ・コモンズ 表示 4.0 ライセンス') }}
          </a>
          {{ $t('の下に提供されています。') }}
          <br />
          2020 Hyogo Metropolitan Government
        </small>
      </div>
    </div>
  </div>
</template>

<i18n>
{
  "ja": {
    "サイドメニュー項目を開く": "サイドメニュー項目を開く",
    "サイドメニュー項目を閉じる": "サイドメニュー項目を閉じる",
    "兵庫県": "兵庫県",
    "新型コロナウイルス感染症": "新型コロナウイルス感染症",
    "対策サイト": "対策サイト",
    "県内の最新感染動向": "県内の最新感染動向",
    "新型コロナウイルス感染症が心配なときに": "新型コロナウイルス感染症が心配なときに",
    "お子様をお持ちの皆様へ": "お子様をお持ちの皆様へ",
    "県民の皆様へ": "県民の皆様へ",
    "企業の皆様・はたらく皆様へ": "企業の皆様・はたらく皆様へ",
    "兵庫県新型コロナウイルス感染症対策本部報": "兵庫県新型コロナウイルス感染症対策本部報",
    "兵庫県主催等 中止又は延期するイベント等": "兵庫県主催等 中止又は延期するイベント等",
    "兵庫県公式ホームページ": "兵庫県公式ホームページ",
    "知事からのメッセージ": "知事からのメッセージ",
    "当サイトについて": "当サイトについて",
    "このサイトの内容物は": "このサイトの内容物は",
    "https://creativecommons.org/licenses/by/4.0/deed.ja":"https://creativecommons.org/licenses/by/4.0/deed.ja",
    "クリエイティブ・コモンズ 表示 4.0 ライセンス": "クリエイティブ・コモンズ 表示 4.0 ライセンス",
    "の下に提供されています。": "の下に提供されています。"
  },
  "en": {
    "サイドメニュー項目を開く": "Open side menu items",
    "サイドメニュー項目を閉じる": "Close side menu items",
    "兵庫県": "Hyogo",
    "新型コロナウイルス感染症": "COVID-19",
    "対策サイト": "Task Force website",
    "県内の最新感染動向": "Latest updates on COVID-19 in Hyogo",
    "新型コロナウイルス感染症が心配なときに": "If you suspect having COVID-19",
    "お子様をお持ちの皆様へ": "For families with children",
    "県民の皆様へ": "For residents in Hyogo (in Japanese)",
    "企業の皆様・はたらく皆様へ": "For enterprises, employees and SMEs",
    "兵庫県新型コロナウイルス感染症対策本部報": "Official statements from Hyogo COVID-19 Task Force (in Japanese)",
    "兵庫県主催等 中止又は延期するイベント等": "Cancelled or Postponed public events (in Japanese)",
    "兵庫県公式ホームページ": "Official website of the Hyogo Metropolitan Government (in Japanese)",
    "知事からのメッセージ": "Message from Governor Koike on COVID-19 (in Japanese)",
    "当サイトについて": "About the website",
    "このサイトの内容物は": "Content on This Site is Licensed Under a",
    "https://creativecommons.org/licenses/by/4.0/deed.ja":"https://creativecommons.org/licenses/by/4.0/",
    "クリエイティブ・コモンズ 表示 4.0 ライセンス": "Creative Commons Attribution 4.0 International License",
    "の下に提供されています。": " "
  },
  "zh-cn": {
    "サイドメニュー項目を開く": "打开侧栏菜单",
    "サイドメニュー項目を閉じる": "关闭侧栏菜单",
    "兵庫県": "东京都",
    "新型コロナウイルス感染症": "新型冠状病毒",
    "対策サイト": "资讯站",
    "県内の最新感染動向": "东京県内最新疫情",
    "新型コロナウイルス感染症が心配なときに": "如果您对新冠肺炎感到担心",
    "お子様をお持ちの皆様へ": "致各位家中有小孩子的家长",
    "県民の皆様へ": "致东京都居民（内容为日语）",
    "企業の皆様・はたらく皆様へ": "致企业及员工",
    "兵庫県新型コロナウイルス感染症対策本部報": "东京都新型冠状病毒官方通告（内容为日语）",
    "兵庫県主催等 中止又は延期するイベント等": "延期或取消的大型活动（仅限东京都主办等）（内容为日语）",
    "兵庫県公式ホームページ": "东京都官方网站（内容为日语）",
    "知事からのメッセージ": "东京都知事寄语（内容为日语）",
    "当サイトについて": "关于本站",
    "このサイトの内容物は": "Content on This Site is Licensed Under a",
    "https://creativecommons.org/licenses/by/4.0/deed.ja":"https://creativecommons.org/licenses/by/4.0/deed.zh",
    "クリエイティブ・コモンズ 表示 4.0 ライセンス": "Creative Commons Attribution 4.0 International License",
    "の下に提供されています。": " "
  },
  "zh-tw": {
    "サイドメニュー項目を開く": "打開側邊選單",
    "サイドメニュー項目を閉じる": "關閉側邊選單",
    "兵庫県": "兵庫県",
    "新型コロナウイルス感染症": "新型冠狀病毒",
    "対策サイト": "疫情中心",
    "県内の最新感染動向": "兵庫県最新疫情資訊",
    "新型コロナウイルス感染症が心配なときに": "若您擔心遭受感染",
    "お子様をお持ちの皆様へ": "給家中有小孩的家長",
    "県民の皆様へ": "給兵庫県市民（日文網站）",
    "企業の皆様・はたらく皆様へ": "給企業與勞工",
    "兵庫県新型コロナウイルス感染症対策本部報": "兵庫県新型冠狀病毒官方公告（日文網站）",
    "兵庫県主催等 中止又は延期するイベント等": "大型活動延期或取消公告（限兵庫県主、協辦）（日文網站）",
    "兵庫県公式ホームページ": "兵庫県官方網站（日文網站）",
    "知事からのメッセージ": "兵庫県知事的話（日文網站）",
    "当サイトについて": "關於本站",
    "このサイトの内容物は": "Content on This Site is Licensed Under a",
    "https://creativecommons.org/licenses/by/4.0/deed.ja":"https://creativecommons.org/licenses/by/4.0/deed.zh_TW",
    "クリエイティブ・コモンズ 表示 4.0 ライセンス": "Creative Commons Attribution 4.0 International License",
    "の下に提供されています。": " "
  },
  "ko": {
    "サイドメニュー項目を開く": "사이트 메뉴를 열기",
    "サイドメニュー項目を閉じる": "사이트 메뉴를 닫기",
    "兵庫県": "도쿄도",
    "新型コロナウイルス感染症": "코로나19",
    "対策サイト": "TF 웹사이트",
    "県内の最新感染動向": "도쿄도내 확진자수 현황",
    "新型コロナウイルス感染症が心配なときに": "감염이 의심될 때",
    "お子様をお持ちの皆様へ": "아이가 있는 가정의 경우",
    "県民の皆様へ": "도쿄 거주자의 경우 (일본어)",
    "企業の皆様・はたらく皆様へ": "직장과 근로자의 경우",
    "兵庫県新型コロナウイルス感染症対策本部報": "도쿄도 코로나 TF 공식 발표 (일본어)",
    "兵庫県主催等 中止又は延期するイベント等": "대규모 행사 연기 또는 취소 (일본어)",
    "兵庫県公式ホームページ": "도쿄도청 공식 사이트 (일본어)",
    "知事からのメッセージ": "코로나19에 대한 도쿄 도지사의 메세지 (일본어)",
    "当サイトについて": "사이트 소개",
    "このサイトの内容物は": "Content on This Site is Licensed Under a",
    "https://creativecommons.org/licenses/by/4.0/deed.ja":"https://creativecommons.org/licenses/by/4.0/deed.ko",
    "クリエイティブ・コモンズ 表示 4.0 ライセンス": "Creative Commons Attribution 4.0 International License",
    "の下に提供されています。": " "
  },
  "ja-basic": {
    "サイドメニュー項目を開く": "なにかしりたいときに ひだりの サイドメニュー ボタンを おす",
    "サイドメニュー項目を閉じる": "なにか しりたいときに ひだりの サイドメニュー ボタンを とじる",
    "兵庫県": "とうきょうと",
    "新型コロナウイルス感染症": "あたらしいコロナウイルスの",
    "対策サイト": "びょうきについて",
    "県内の最新感染動向": "とうきょうとでの コロナウイルスの あたらしいじょうほう",
    "新型コロナウイルス感染症が心配なときに": "コロナウイルスがこわいときに",
    "お子様をお持ちの皆様へ": "こどもが いる ひと へ",
    "県民の皆様へ": "とうきょうとに すんでいる ひと へ",
    "企業の皆様・はたらく皆様へ": "はたらいている ひと へ",
    "兵庫県新型コロナウイルス感染症対策本部報": "とうきょうと からの おしらせ",
    "兵庫県主催等 中止又は延期するイベント等": "コロナウイルスのため やめた あつまり",
    "兵庫県公式ホームページ": "とうきょうとの ウェブサイト",
    "知事からのメッセージ": "えらいひとからの ことば",
    "当サイトについて": "この ウェブサイトについて",
    "このサイトの内容物は": "この ウェブサイトの ないようは",
    "https://creativecommons.org/licenses/by/4.0/deed.ja":"https://creativecommons.org/licenses/by/4.0/deed.ja",
    "クリエイティブ・コモンズ 表示 4.0 ライセンス": "クリエイティブ・コモンズ 表示 4.0 ライセンス",
    "の下に提供されています。": "で ていきょう します"
  }
}
</i18n>

<script>
import ListItem from '@/components/ListItem'
import LanguageSelector from '@/components/LanguageSelector.vue'

export default {
  components: {
    ListItem,
    LanguageSelector
  },
  props: {
    isNaviOpen: {
      type: Boolean,
      required: true
    }
  },
  computed: {
    items() {
      return [
        {
          icon: 'mdi-chart-timeline-variant',
          title: this.$t('県内の最新感染動向'),
          link: this.localePath('/')
        },
        {
          icon: 'covid',
          title: this.$t('新型コロナウイルス感染症が心配なときに'),
          link: this.localePath('/flow'),
          divider: true
        },
        {
          icon: 'parent',
          title: this.$t('お子様をお持ちの皆様へ'),
          link: this.localePath('/parent')
        },
        {
          icon: 'mdi-account-multiple',
          title: this.$t('県民の皆様へ'),
          link: 'https://web.pref.hyogo.lg.jp/kk03/200129.html'
        },
        {
          icon: 'mdi-domain',
          title: this.$t('企業の皆様・はたらく皆様へ'),
          link: this.localePath('/worker'),
          divider: true
        },
        {
          title: this.$t('兵庫県新型コロナウイルス感染症対策本部報'),
          link: 'https://web.pref.hyogo.lg.jp/kk03/singatakoronataiou.html'
        },
        //        {
        //          title: this.$t('兵庫県主催等 中止又は延期するイベント等'),
        //          link:
        //            'https://www.seisakukikaku.metro.Hyogo.lg.jp/information/event02.html'
        //        },
        //        {
        //          title: this.$t('知事からのメッセージ'),
        //          link:
        //            'https://www.metro.Hyogo.lg.jp/tosei/governor/governor/katsudo/2020/03/03_00.html'
        //        },
        {
          title: this.$t('当サイトについて'),
          link: this.localePath('/about')
        },
        {
          title: this.$t('兵庫県公式ホームページ'),
          link: 'https://web.pref.hyogo.lg.jp/',
          divider: true
        }
      ]
    },
    isClass() {
      return item => (item.title.charAt(0) === '【' ? 'kerningLeft' : '')
    }
  },
  methods: {
    openNavi() {
      this.$emit('openNavi')
    },
    closeNavi() {
      this.$emit('closeNavi')
    }
  }
}
</script>

<style lang="scss" scoped>
.SideNavigation {
  position: relative;
  height: 100%;
  background: $white;
  box-shadow: 0px 0px 2px rgba(0, 0, 0, 0.15);
  &-HeadingContainer {
    padding: 1.25em 0 1.25em 1.25em;
    align-items: center;
    @include lessThan($small) {
      padding: 7px 0 7px 20px;
    }
  }
  &-HeadingIcon {
    margin-right: 16px;
  }
  &-HeadingLink {
    @include lessThan($small) {
      display: flex;
      align-items: center;
    }
    text-decoration: none;
  }
  &-ListContainerIcon {
    margin: 24px 16px 0;
  }
  &-ListItemContainer {
    padding: 2px 20px;
  }
  &-Logo {
    margin: 20px 16px 0 0;
    width: 110px;
    @include lessThan($small) {
      margin-top: 0;
    }
  }
  &-Heading {
    margin-top: 8px;
    font-size: 13px;
    color: #898989;
    padding: 0.5em 0;
    text-decoration: none;
    @include lessThan($small) {
      margin-top: 0;
    }
  }
  &-HeadingDivider {
    margin: 0px 20px 4px;
    @include lessThan($small) {
      display: none;
    }
  }
  &-Divider {
    margin: 12px 0;
  }
  &-LanguageMenu {
    padding: 0 20px;
    background: #fff;
  }
  &-Footer {
    padding: 20px;
    background-color: $white;
  }
  &-SocialLinkContainer {
    display: flex;
    & img {
      width: 30px;
      &:first-of-type {
        margin-right: 10px;
      }
    }
  }
  &-Copyright {
    display: block;
    margin-top: 10px;
    font-size: 8px;
    line-height: 1.2;
    color: $gray-1;
    font-weight: bold;
  }
}
.open {
  @include lessThan($small) {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    display: block !important;
    width: 100%;
    z-index: z-index-of(opened-side-navigation);
    background-color: $white;
    height: 100%;
    overflow-y: scroll;
  }
}
@include largerThan($small) {
  .pc-none {
    display: none;
  }
}
@include lessThan($small) {
  .sp-flex {
    display: flex;
  }
  .sp-none {
    display: none;
  }
}
</style>
