<template>
    <view>
      <wuc-tab :tab-list="tabList" :tabCur.sync="TabCur" @change="tabChange"></wuc-tab>
      <swiper class="uni-swiper_" :current="TabCur" duration="300" @change="swiperChange">
        <swiper-item v-for="(item,index) in tabList" :key="index">
          <view v-if="tabList[index].items">
            <MediaList
              :items='tabList[index].items'
            />
          </view>
        </swiper-item>
      </swiper>
      <view class="tabbar">
        <view class="tab">
          <text class="icon icon-djxx"></text>
          <text class="text">党建信息</text>
        </view>
        <view class="tab">
          <text class="icon icon-xxs"></text>
          <text class="text">学习所</text>
        </view>
        <view class="tab">
          <text class="icon icon-home"></text>
        </view>
        <view class="tab">
          <text class="icon icon-zzsh"></text>
          <text class="text">组织生活</text>
        </view>
        <view class="tab">
          <text class="icon icon-wode"></text>
          <text class="text">我的</text>
        </view>
      </view>
    </view>
</template>
<script>
  import WucTab from '@/components/wuc-tab/wuc-tab.vue';
  import MediaList from '../component/mediaList.vue';
	export default {
      data() {
          return {
            TabCur: 0,
            tabList: [
            {
              name: '街道党建服务中心',
              items: [{
                img: '/static/item-img1.png',
                title: '街道党建服务中心',
                address: '武宁南路241号',
                phone: '18901837654',
                location: '276m'
              },{
                img: '/static/item-img2.png',
                title: '静安区街道社区党建服务中心',
                address: '常熟路113弄23号',
                phone: '54361720',
                location: '456m'
              },{
                img: '/static/item-img3.png',
                title: '曹家渡街道社区党建服务中心',
                address: '余姚路346号',
                phone: '52562215',
                location: '1.2km'
              },{
                img: '/static/item-img4.png',
                title: '江宁路街道社区党建服务中心',
                address: '西康路370弄50号二楼',
                phone: '62535982',
                location: '1.5km'
              }]
            },
            {
              name: '白领驿家党建服务中心',
              items: [{
                img: '/static/item-img1.png',
                title: '街道党建服务中心',
                address: '武宁南路241号',
                phone: '18901837654',
                location: '276m'
              },{
                img: '/static/item-img2.png',
                title: '静安区街道社区党建服务中心',
                address: '常熟路113弄23号',
                phone: '54361720',
                location: '456m'
              },{
                img: '/static/item-img3.png',
                title: '曹家渡街道社区党建服务中心',
                address: '余姚路346号',
                phone: '52562215',
                location: '1.2km'
              },{
                img: '/static/item-img4.png',
                title: '江宁路街道社区党建服务中心',
                address: '西康路370弄50号二楼',
                phone: '62535982',
                location: '1.5km'
              }]
            },
            {
              name: '居民区党建服务中心',
              items: [{
                img: '/static/item-img1.png',
                title: '街道党建服务中心',
                address: '武宁南路241号',
                phone: '18901837654',
                location: '276m'
              },{
                img: '/static/item-img2.png',
                title: '静安区街道社区党建服务中心',
                address: '常熟路113弄23号',
                phone: '54361720',
                location: '456m'
              },{
                img: '/static/item-img3.png',
                title: '曹家渡街道社区党建服务中心',
                address: '余姚路346号',
                phone: '52562215',
                location: '1.2km'
              },{
                img: '/static/item-img4.png',
                title: '江宁路街道社区党建服务中心',
                address: '西康路370弄50号二楼',
                phone: '62535982',
                location: '1.5km'
              }]
            }
          ]
        }
      },
      onLoad: function(){
        console.log('onLoad');
        this.request();
      },
      components: { WucTab, MediaList },
      methods: {
          tabChange(index) {
              this.TabCur = index;
          },
          swiperChange: function(e){
            console.log(e);
            this.TabCur = e.detail.current;
          },
          async request(){

            //党建阵地1
            {
              let [error, res] = await uni.request({
                url: '/api/getData'
              });
              console.log(res && res.data);
            }
          }
      }
  }
</script>

<style>
  .uni-swiper_{
    height: 100%;
    position: absolute;
    left: 0;
    right: 0;
    top: 4.4em;
    bottom: 4.4em;
  }
  .tabbar{
    display: flex;
    height: 4.4em;
    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;
    background: #fff;
    border-top: 1px solid #e2e2e2;
  }
  .tabbar .tab{
    flex: 2;
    text-align: center;
    width: 4.4em;
    height: 4.4em;
    color: #9c9c9c;
  }
  .tab .text{
    display: block;
    margin: 0 auto;
  }
  .tab .icon{
    display: block;
    margin: 0 auto;
    margin-top: 16upx;
  }
</style>
