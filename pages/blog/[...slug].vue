 <template>
   <div>
     <article>
       <ContentDoc/>
     </article>
   </div>
 </template>
 <script setup lang="ts">
 const route = useRoute();
 console.log(route.params.slug);
 </script>