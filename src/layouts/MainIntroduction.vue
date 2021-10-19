<template>
  <div class="mainBody">
    <span style="color: #eec08b">let</span> xiu = {<br>
    <indented-line>name: <string-wrapper>刘秀</string-wrapper></indented-line>
    <indented-line>id: <string-wrapper>6thSh0w</string-wrapper></indented-line>
    <indented-line>email: <string-wrapper><a href="mailto:i@xiu.buzz">i@xiu.buzz</a></string-wrapper></indented-line>
    <indented-line>profession: <string-wrapper>{{ $t('profession') }}</string-wrapper></indented-line>
    <sub-obj name="links">
      <indented-line v-for="link in links" :key="link.title"><indentation /><string-wrapper><a :href="link.link" @click="onLinkClick(link)">{{ $t(link.title) }}</a></string-wrapper></indented-line>
    </sub-obj>
    <sub-obj name="contacts">
      <indented-line><indentation />QQ: <string-wrapper>1364109425</string-wrapper></indented-line>
      <indented-line><indentation />Mobile: <string-wrapper>+86 18998490182</string-wrapper></indented-line>
    </sub-obj>
    <sub-obj name="identities" v-if="expanded">
      <indented-line v-for="identity in 9" :key="identity"><indentation /><string-wrapper>{{ $t('identities.' + identity) }}</string-wrapper></indented-line>
    </sub-obj>
    <indented-line v-else>identities: [ <a href="#" @click="expanded = true">...</a> ]</indented-line>
    };

    <q-dialog v-model="showWeChat" seamless>
      <q-card>
        <q-card-section>
          <div class="text-h6">{{ $t('wechat') }}</div>
        </q-card-section>

        <q-card-section class="q-pt-none">
          <img src="assets/wechat.png" style="width: 100%; height: 100%" />
        </q-card-section>

        <q-card-actions align="right">
          <q-btn flat label="OK" color="primary" v-close-popup />
        </q-card-actions>
      </q-card>
    </q-dialog>
  </div>
</template>

<script>
import IndentedLine from "components/IndentedLine";
import SubObj from "components/subObj";
import Indentation from "components/Indentation";
import StringWrapper from "components/StringWrapper";

const links = [
  { title: 'blog', link: 'https://liuxiu233.com' },
  { title: 'github', link: 'https://github.com/LiuXiu233' },
  { title: 'gitee', link: 'https://gitee.com/liuxiu233' },
  { title: 'twitter', link: 'https://twitter.com/Liuxiu233' },
  { title: 'steam', link: 'https://steamcommunity.com/id/liuxiu233/' },
  { title: 'weibo', link: 'https://weibo.com/junhunz' },
  { title: 'wechat', link: '#' },
  { title: 'facebook', link: 'https://www.facebook.com/profile.php?id=100048228247720' },
  { title: 'linkedin', link: 'https://www.linkedin.com/in/liuxiu233' },
];

export default {
  name: "MainIntroduction",
  components: { StringWrapper, Indentation, SubObj, IndentedLine },

  setup() {
    return {
      links,
    }
  },

  data() {
    return {
      expanded: false,
      showWeChat: false
    }
  },

  methods: {
    onLinkClick(link) {
      if (link.title === 'wechat') {
        this.showWeChat = true;
      }
    }
  }
}
</script>

<style>
/*.mainBody :after {
  content: "|";
  -webkit-animation: blink 500ms linear infinite alternate;
  animation: blink 500ms linear infinite alternate;
}*/
</style>
