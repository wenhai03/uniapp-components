<template>
  <view class="home">
    <!-- 自定义导航栏 -->
    <navbar></navbar>

    <view class="scroll">
      <scroll-view class="list-scroll" scroll-y>
        <view>
          <view v-for="item in 100">
            {{item}}内容那个
          </view>
        </view>
      </scroll-view>
    </view>
  </view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello0000',
				tabList: [],
				tabIndex:0,
				activeIndex:0
			}
		},
		onLoad() {

		},
		methods: {
      change(current){
        this.tabIndex = current
        this.activeIndex = current
        // console.log('当前swiper的值：',current);
      },
      tab({data,index}){
        console.log(data,index);
        this.activeIndex = index
      },
      getLabel() {
        // 调用云函数方法
        /*this.$api.get_label().then((res) => {
          const {
            data
          } = res
          console.log('标签 ',data);
          data.unshift({
            name:'全部'
          })
          this.tabList = data
          // 	console.log(this.tabList);
        })*/

      }
		}
	}
</script>

<style>
  page {
    height: 100%;
    display: flex;
  }
  .list-scroll {
    height: 100%;
  }
  .home  {
    display: flex;
    flex-direction: column;
    flex: 1;

    .scroll {
      flex:1;
      /*overflow: hidden;*/
      box-sizing: border-box;
    }
  }

</style>
