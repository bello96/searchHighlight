<template>
  <div>
    <Hello :cityMEList="cityMEList"></Hello>
  </div>
</template>

<script>
import Hello from "./components/Hello.vue";
export default {
  name: "App",
  components: {
    Hello,
  },
  data() {
    return {
      cityMEList: [
        {
          id: 1,
          comtent: "你开心吗？",
        },
        {
          id: 2,
          comtent: "什么是快乐星球",
        },
        {
          id: 3,
          comtent: "快快乐乐",
        },
        {
          id: 4,
          comtent: "如果你开心的话，我就带你去快乐星球",
        },
        {
          id: 5,
          comtent: "笑只是一种表情，与快乐无关",
        },
        {
          id: 6,
          comtent: "哈哈大笑",
        },
        {
          id: 7,
          comtent: "笑傲江湖",
        },
      ],
    };
  },
};
</script>
