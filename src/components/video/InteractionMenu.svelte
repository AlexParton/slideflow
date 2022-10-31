<script lang="ts">
  export let isLiked: boolean;
  export let isBookmarked: boolean;
</script>


<section>
  <button><img src={isLiked ? "/icons/starred.svg" : "/icons/star.svg"} alt="star"></button>
  <button><img src={isBookmarked ? "/icons/bookmarked.svg" : "/icons/bookmark.svg"} alt="bookmark"></button>
  <button><img src="/icons/share.svg" alt="share"></button>
  <button><img src="/icons/comment.svg" alt="comment"></button>
  <button><img src="/icons/info.svg" alt="info"></button>
</section>

<style>
  section {
    position: absolute;
    bottom: 14vh;
    right: 3vw;
    z-index: 5;
    width: 10vw;
    display: flex;
    gap: 6vw;
    flex-wrap: wrap;
  }

  img {
    opacity: .7;
  }
</style>