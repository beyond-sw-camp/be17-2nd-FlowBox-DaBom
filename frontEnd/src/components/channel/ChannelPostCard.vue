<script setup>
import channelCommentModal from '@/components/channel/ChannelCommentModal.vue';

import { useRouter } from 'vue-router';

const router = useRouter()

const clickLikeBtn = () => {
    
}

const clickPost = () => {
    router.push('/channel/community/1')
}
</script>

<template>
<div class="community-post">
    <div class="post"s>
    <div class="post-header">
        <div class="post-author">
            <img src="https://via.placeholder.com/40" alt="채널" class="author-avatar">
            <div class="author-info">
                <span class="author-name">크리에이티브 채널</span>
                <span class="post-time">3시간 전</span>
            </div>
        </div>
        <div class="post-title">
            <span class="title">제목입니다.</span>
        </div>
    </div>
    <div class="post-content">
        <p>안녕하세요! 새로운 Together 모드 업데이트에 대한 피드백을 받고 있습니다. 어떤 기능을 추가했으면 좋겠는지 댓글로 알려주세요! 🎉</p>
        <div class="post-image">
            <img src="https://via.placeholder.com/500x300" alt="게시물 이미지">
        </div>
    </div>
    </div>
    <div class="post-actions">
        <button class="post-action-btn like-btn" @click="clickLikeBtn">
            <i class="fas fa-heart"></i>
                124
        </button>
        <button class="post-action-btn comment-btn" @click="clickPost">
            <i class="fas fa-comment"></i>
                32
        </button>
    </div>
    <div v-if="commentModal" @click.stop>
        <channelCommentModal  />
    </div>
</div>
</template>

<style scoped>
    @import url('@/assets/channel/ChannelPostCard.css');
</style>