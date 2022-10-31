<section>
  <slot />
</section>


<style>
  section {
    height: var(--screenHeight);
    overflow: scroll;
    scroll-snap-type: y mandatory;
    padding: var(--headerHeight) 0 var(--bottomHeight);
}
</style>