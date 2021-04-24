<template>
  <div class="box">
    <input type="text" v-model.trim="SerachValue" />
    <button @click="serach">搜索</button>
    <ul>
      <li v-for="item in newcityMEList" :key="item.id">
        <span v-if="!isserach" v-html="item"></span>
        <span v-else>{{ item.comtent }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      SerachValue: "",
      newcityMEList: [],
      isserach: false,
    };
  },
  props: {
    cityMEList: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  methods: {
    serach() {
      if (!this.SerachValue) {
        this.newcityMEList = this.cityMEList;
        this.isserach = true;
        return;
      }
      this.isserach = false;
      this.newcityMEList = [];
      this.cityMEList.forEach((item) => {
        if (item.comtent.includes(this.SerachValue)) {
          let itemdata = JSON.parse(JSON.stringify(item));
          let dataArr = itemdata.comtent.split(this.SerachValue);
          let str = dataArr.join(
            `<span style="color:red">${this.SerachValue}</span>`
          );
          this.newcityMEList.push(str);
        }
      });
    },
  },
};
</script>

<style lang="less">
ul,
li {
  margin: 0;
  padding: 0;
  list-style: none;
}
</style>
