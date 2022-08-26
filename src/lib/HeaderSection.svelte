<script>

    export let phase
    </script>
    
    <div class="section-2 wf-section {phase==0 ? "small" : ''}">
      <div class="div-block-3">
        <a href="/"><h1 class="heading">marvel</h1></a>
        <h1 class="heading-2">cinematic network</h1>
        <div class="text-block-3">By <a href="http://www.ladataviz.com" target="_blank" class="link"><strong class="bold-text-3">Tristan Guillevin</strong></a>
        </div>
      </div>
      <p class="paragraph-2"><strong>Explore the Marvel Cinematic Universe like never before!</strong>
        {#if phase==1}
          <br><strong>Scroll down</strong> to see how the MCU evolved during the <strong>Phase One</strong>, <em>from </em><strong><em>Iron Man</em></strong> <em>to </em><strong><em>The Avengers</em></strong>. 
        {:else if phase ==2 }
          <br><strong>Scroll down</strong> to see how the MCU evolved during the <strong>Phase Two</strong>, <em>from </em><strong><em>Iron Man 3</em></strong> <em>to </em><strong><em>Ant-Man</em></strong>. 
        {/if}
        <br>Each main <strong>character</strong> is connected to the <strong>movies</strong> they appear in, allowing you to see the <strong>connections</strong> between your favorite Marvel heroes <em>(or villains)</em>. <em>Of course, if you haven&#x27;t seen the movie, spoiler ahead!</em>
      </p>
      {#if phase<=1}
        <img src="images/legend.png" loading="lazy" height="" width="500" sizes="(max-width: 767px) 100vw, 500px" alt="" class="image">
      {:else}
        <img src="images/legendPhase23.png" loading="lazy" height="" width="500" sizes="(max-width: 767px) 100vw, 500px" alt="" class="image">
      {/if}
    
    </div>