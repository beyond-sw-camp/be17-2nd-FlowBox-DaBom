<script setup>
import { reactive } from 'vue'
import api from '@/api/channel'

// props 선언 (defineProps 사용)
const props = defineProps({
  isActive: Boolean
})

// 폼 데이터 선언
const channelInfoForm = reactive({
  id: "12345",
  name: '',
  content: '',
  image: [],
  banner: [],
  email: '',
  sns01: '',
  sns02: ''
})

// 저장 이벤트 함수
const onSubmit = async() => {
  const res = await api.postChannelInfo()
  Object.assign(channelInfoForm, res)
  alert('저장되었습니다!')
}
</script>

<template>
  <section id="section-info" class="dashboard-section" :class="{ active: props.isActive }">
    <h2>채널 정보 수정</h2>

    <form class="channel-info-form" @submit.prevent="onSubmit">
      <label>
        채널 이름
        <input type="text" v-model="channelInfoForm.name" placeholder="크리에이티브 채널">
      </label>
      <label>
        채널 설명
        <textarea rows="3" v-model="channelInfoForm.content" placeholder="창작과 영감을 나누는 공간입니다."></textarea>
      </label>
      <label>
        채널 프로필 이미지
        <input type="file" accept="image/*" @change="onImageChange">

      </label>
      <label>
        배너(커버) 이미지
        <input type="file" accept="image/*">
      </label>
      <label>
        연락처 이메일
        <input type="email" v-model="channelInfoForm.email" placeholder="creative@dabom.com">
      </label>
      <label>
        소셜 링크
        <input type="text" v-model="channelInfoForm.sns01" placeholder="https://twitter.com/dabom">
        <input type="text" v-model="channelInfoForm.sns02" placeholder="https://instagram.com/dabom">
      </label>
      <button class="btn-save" type="submit"><i class="fas fa-save"></i> 저장</button>
    </form>
  </section>
</template>

<style scoped>
@import url(@/assets/channel/mychannel);
</style>
