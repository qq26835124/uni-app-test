<template lang="html">
  <view>
    <view v-for="(item,index) in items" class="item">
      <view class="item-img"><image class="image" :src="item.img" alt=""></image></view>
      <view class="item-content">
        <view class="title">{{item.title}}</view>
        <view class="address">地址：{{item.address}}</view>
        <view class="phone">电话：{{item.phone}}</view>
        <view class="btns">
          <button class="mini-btn seeMap" size="mini" type="warn">查看地图</button>
          <button class="mini-btn subscribe" size="mini" type="warn">预约</button>
        </view>
      </view>
      <view class="item-end">
        <view class="shoucang">
          <text class="icon icon-star"></text>
        </view>
        <view class="location">
          <text class="icon icon-location"></text><text class="text">{{item.location}}</text>
        </view>
      </view>
    </view>
  </view>
</template>

<script>

  export default {
      data(){
        return {}
      },
      props: {
        items: {
          type: Array,
          default(){
            return [];
          }
        }
      }
  }

</script>

<style lang="css" scoped>
  .item{
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16upx;
  }
  .item-img{
    flex: 4;
    font-size: 0;
  }
  .item-img .image{
    width: 200upx;
    height: 200upx;
  }
  .item-content{
    flex: 9;
    margin-left: 18upx;
    color: #7b7b7b;
    font-size: 22upx;
  }
  .item-content .btns{
    margin-top: 10upx;
  }
  .mini-btn{
    margin-right: 10upx
  }
  .item-content .title{
    font-size: 28upx;
    color: #000;
  }
  .item-content .address,.item-content .phone{
    line-height: 40upx;
  }
  .item-content .address{
    margin-top: 10upx;
    width:100%;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  .item-end{
    flex: 3;
    text-align: right;
  }

  .item-end .location{
    margin-top: 60upx;
  }
  .item-end .location .text{
    margin-left: 20upx;
    color: #4b4b4b;
  }
  .mini-btn{
    padding: 0 10upx;
    line-height: 2;
  }
</style>