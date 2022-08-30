<script>
	export let name;
    export let score;
    export let boxOffice;
    export let sort
    export let release
    export let phase

    let options = { year: 'numeric', month: 'long'  };
    let date  = new Date(release);

</script>

<div class="section { (sort > 11 ? parseInt(sort)+2 : sort>7 ? (parseInt(sort)+1) : sort)%2 ==1 ? 'grey'  : '' } wf-section">
  <div class="div-block-7 {sort==7 || sort == 11 ? "bottom" : sort==8 || sort == 12 ? "top" : ""}">
    <div class="explanation">
      {#if sort != 8 && sort != 12}
      <h3 class="heading-4">{name}</h3>
      <h1 class="heading-5">{date.toLocaleDateString("en-US", 
// @ts-ignore
      options)}</h1>
        <div class="text-block">Score: <strong>{score}%</strong> <em>(Rotten Tomatoes)</em></div>
        <div class="text-block">Box Office: <strong>{Intl.NumberFormat('en-US', { style: 'currency', currency: 'USD', maximumFractionDigits: 0},).format(boxOffice)}</strong></div>
      {/if}
      <div class="div-block-9">
        {#if phase==1}
          {#if sort == 1}
            <p class="paragraph">Everything started in <strong>2008</strong> with <strong>Iron Man</strong>, the <strong>first</strong> movie of the <strong>Marvel Cinematic Universe</strong>.
              <br> <br><strong>Tony Stark</strong> <em>(Robert Downey</em> <em>Jr)</em> is an eccentric <strong>billionaire</strong> who made his fortune by building and selling <strong>weapons</strong>.
              <br> <br><strong>Stark</strong> is <strong>kidnapped</strong> by a <strong>terrorist organization</strong>.
              He <strong>escapes</strong> by secretly building an <strong>iron suit</strong>.
              Back home, Tony announces that his company will <strong>stop</strong> manufacturing weapons. 
              <br><br>Stark <strong>perfects</strong> his suit and saves villagers in Afghanistan. He discovers that his friend, <strong>Obadiah Stane</strong> <em>(Jeff Bridges)</em>, planned his kidnapping to get control over <strong>Stark Industries</strong> and stops him.
              <br><br>At the movie&#x27;s end, Tony Stark reveals his identity: <br> &quot;<strong>I am Iron Man</strong>&quot;.
              <br><br>In the post-credit scene, Nick Furry <em>(</em><em>Samuel L. Jackson</em>) invites Stark to join the <strong>Avengers</strong>.
               </p>
          {:else if sort == 2}
            <p class="paragraph"><strong>Incredible Hulk</strong> is the <strong>second</strong> movie of the MCU.
              In this movie <em>(and this one only)</em>, <strong>Bruce Banner </strong>is played by <em>Edward Norton</em>.
              <br><br><strong>Banner</strong> transforms into the <strong>Hulk</strong> after exposure to <strong>gamma radiation</strong>.
              <br><br><strong>General Thaddeus Ross</strong> <em>(William Hurt)</em>, who worked with <strong>Bruce</strong>, wants to capture and <strong>weaponize</strong> the Hulk.
              He tracks Banner and sends special forces, led by <strong>Emil Blonsky</strong> <em>(Tim Roth)</em>, to capture him.
              <br><br>Blonsky is injected with Banner&#x27;s blood and mutates into the <strong>Abomination</strong>.
              The Hulk defeats the Abomination but spares his life.
              <br><br><strong>Stark</strong> approaches <strong>Ross</strong> at a local bar and informs him that a <strong>team</strong> is being put together.
              <br><br>The <strong>Marvel Cinematic Universe</strong> is on.</p>
            {:else if sort == 3}
            <p class="paragraph">The <strong>third</strong> movie of the MCU is a direct <strong>sequel</strong> to the first Iron Man and <strong>Natasha Romanoff</strong><em> (Scarlett Johansson)</em> debut.
              <br><br> <strong>Stark</strong> learns that the <strong>palladium</strong> that keeps him alive and powers the suit is <strong>poisoning</strong> and <strong>killing</strong> him.
              <br><br>At the Monaco Grand Prix, <strong>Stark</strong> is attacked by <strong>Ivan Vanko</strong> <em>(Mickey Rourke)</em>, who wants to prove to the world that <strong>Iron Man</strong> is not invincible and get revenge for his father.
              <br><br>At <strong>Stark</strong>'s birthday party, <strong>Rhodes</strong> <em>(Don Cheadle)</em> confiscates on of Stark's suit.
              Later, <strong>Stark</strong> discovers a hidden message from his <strong>dad</strong> and manages to synthesize a new <strong>element</strong> to replace the palladium, saving his life.
              <br><br><strong>Stark</strong>, <strong>Rhodes</strong>, and <strong>Romanoff</strong> defeat <strong>Vanko</strong>, who built and army of drones for Stark's competitor <strong>Justin Hammer</strong> <em>(Sam Rockwell)</em>.
              <br><br>In a post-credits scene, agent <strong>Coulson</strong> reports the discovery of a <strong>large hammer</strong> in New Mexico.
        
            </p>
            {:else if sort == 4}
            <p class="paragraph">The <strong>fourth</strong> movie of the MCU introduces <strong>Thor</strong> <em>(Chris Hemsworth)</em>, <strong>Loki</strong> <em>(Tom Hiddleston)</em>, and <strong>Clint Barton</strong> <em>(Jeremy Renner)</em>.
              <br><br>The movie starts in <strong>Asgard</strong>, when <strong>Odin&#x27;s</strong> son, <strong>Thor</strong>, prepares to become <strong>king</strong>.
              After a fight, Odin punishes his son for his <strong>arrogance</strong> by removing his power and exiling him to Earth with his hammer, <strong>Mjölnir</strong>, that can only be lifted by someone <strong>worthy</strong>.
              <br><br>Thor lands in New Mexico and receives help from <strong>Dr. Jane Foster</strong> <em>(Natalie Portman)</em> and <strong>Dr. Selvig</strong> <em>(Stellan Skarsgard)</em>.
              He finds <strong>Mjölnir</strong> but is unable to lift it. 
              <br><br>Thor&#x27;s brother, <strong>Loki</strong>, who is plotting against him to take the throne, sends the <strong>Destroyer</strong> on Earth to kill Thor.
              By being willing to sacrifices for others, <strong>Thor</strong> becomes <strong>worthy</strong> of his hammer again and destroy the Destroyer.
              <br><br><strong>Thor</strong> confronts Loki, who falls into the abyss to his apparent death.
              Ultimately, <strong>Selvig</strong> meets <strong>Nick Fury</strong>, who asks him to study the <strong>Tesseract</strong>.</p>
            {:else if sort == 5}
            <p class="paragraph">The <strong>fifth</strong> movie is <strong>first </strong>in <strong>chronological</strong> order.
              <br><br><strong>Steve Rogers</strong> <em>(Chris Evans)</em> enlists in a <strong>super-soldier</strong> experiment program giving him <strong>extraordinary strength</strong>.
              He meets agent <strong>Peggy Carter</strong> <em>(Hayley Atwell)</em> and <strong>Howard Stark</strong> <em>(Dominic Cooper)</em>, who gives him a <strong>shield</strong> made of <strong>vibranium</strong>.
              Steve Rogers becomes <strong>Captain America</strong>.
              <br><br>During a mission, Steve&#x27;s best friend, <strong>James "Bucky" Barnes</strong> <em>(Sebastian Stan)</em>, falls from a train to his apparent death.
              <br><br> Steve discovers the location of the last Hydra base and plans to stop Hydra's head, <strong>Johann Schmidt</strong> <em>(Hugo Weaving)</em>.
              <br><br> During the final fight, Schmidt handles the <strong>Tesseract</strong> and end up <strong>swallowed</strong> into space.
              The <strong>Tesseract</strong> and <strong>Rogers</strong> end up <strong>crashing</strong> into the <strong>Arctic ocean</strong>.
              <br><br>Rogers awakens, and <strong>Fury</strong> informs him that he has been asleep for nearly <strong>70 years</strong> and has a new <strong>mission</strong> for him.</p>
            {:else if sort == 6}
            <p class="paragraph">The <strong>last</strong> movie brings all heroes <span class="text-span-2"><sub class="subscript">○</sub></span> <strong>together</strong>! 
              <br><br><strong>Loki</strong> promises to the chief of the <strong>Chitauri</strong> to retrieve the <strong>Tesseract</strong> in exchange for an army able to conquer Earth.
              He steals the <strong>Tesseract</strong> from <strong>Selvig</strong> and <strong>Fury</strong>.
              <br><br><strong>Rogers</strong>, <strong>Stark</strong>, and <strong>Thor</strong> captures <strong>Loki</strong>.
              He escapes by awakening the <strong>Hulk</strong> <em>(Mark Ruffalo)</em>, and <strong>kills </strong><span class="text-span"><strong class="bold-text-2">Coulson</strong></span><strong>.
              </strong>Coulson's death <strong>motivates</strong> the <strong>Avengers</strong> to work together.
              <br><br>Loki opens a <strong>wormhole</strong> for the Chitauri to invade Earth.
              Together, <strong>the Avengers</strong> defend <strong>New York City</strong> and the <strong>Hulk</strong> beats <strong>Loki</strong>.
              <br><br><strong>Stark</strong> manages to destroy the Chitauri forces by diverting a <strong>nuclear weapon</strong> through the wormhole.
              <br><br>After the credit, <strong>Thanos</strong> is informed of the failure of the plan.
              <strong>Phase One</strong> ends with the heroes eating some well-deserved <strong>Shawarma</strong>.
              </p>
          {/if}
          
        {:else if phase==2}
          {#if sort == 1}
            <p class="paragraph"><strong>Phase Two</strong> also starts with an <strong>Iron Man</strong> movie.
              <br><br>After the event of <strong>The Avengers</strong>, <strong>Stark</strong> suffers from <strong>post-traumatic stress disorder</strong> while <strong>terrorist attacks</strong> are occurring in the country.
              <br><br>When <strong>Happy</strong> <em>(Jon Favreau) </em>gets hurt in one of the attacks, Stark decides to <strong>confront</strong> the <strong>Mandarin</strong>. 
              Stark's house and armors are <strong>destroyed </strong>, and he ends up in a small town after being nearly <strong>killed</strong>.
              <br><br>With the help of a local kid, Tony discovers that the bombings result from people rejecting a <strong>regenerative treatment</strong>, <strong>Extremis</strong>. 
              The <strong>Mandarin</strong> is a cover-up played by a Britsh actor, <strong>Trevor</strong> <em>(Ben Kingsley)</em>.
              <br><br><strong>Pepper Potts</strong> <em>(Gwyneth Paltrow)</em>, <strong>Rhodes </strong>, and Stark manages to fight and win against the real threat, <strong>Aldrich Kilian </strong><em>(Guy Pearce)</em>.
              <br><br>In the end, Stark gets <strong>surgery,</strong> making him less dependent on his technology, and promises Pepper to scale down as <strong>Iron Man</strong>.
            </p>
          {:else if sort == 2}
            <p class="paragraph">The <strong>second</strong> movie follows <strong>Thor</strong>, <strong>Loki</strong>, and <strong>Jane Foster</strong> in their new adventure.
              <br><br>The <strong>Convergence</strong> creates <strong>portals</strong> between the different <strong>worlds</strong>.
              <strong>Foster</strong> is <strong>teleported</strong> to a world where she absorbs the <strong>Aether</strong>, awakening the dark elf, <strong>Malekith</strong>.
              <br><br>Malekith attacks <strong>Asgard</strong>, and Thor seeks the <strong>help</strong> of his brother, <strong>Loki</strong>, who is imprisoned.
              They <strong>fight</strong> Malekith on <strong>Svartalfheim</strong> but <strong>fail</strong>: Malekith <strong>merges</strong> with the <strong>Aether</strong>, and <strong>Loki</strong> is <strong>stabbed</strong> to his <em>(again)</em> apparent <strong>death</strong>.
              <br><br><strong>Thor</strong> fights <strong>Malekith</strong> in <strong>London</strong> and <strong>defeats</strong> him with the help of <strong>Jane</strong> and <strong>Selvig</strong>.
              In Asgard, we learn that <strong>Loki</strong> is <strong>alive</strong> and impersonating Odin.
              <br><br>The Aether, containing the <strong>Reality Stone</strong>, is taken to <strong>Taneleer Tivar, </strong>aka the <strong>Collector</strong>, who reveals his desire to <strong>acquire</strong> the five other <strong>Infinity Stones</strong>.
            </p>
          {:else if sort == 3}
            <p class="paragraph">The <strong>third</strong> movie of Phase Two sees the return of <strong>Steve Rogers </strong>, <strong>Natasha Romanoff </strong>, and <strong>Bucky Barnes</strong>.
              It also introduces a new hero, <strong>Sam Wilson</strong> <em>(Anthony Mackie)</em>.
              <br><br><strong>Rogers</strong> is working for the <strong>S.H.I.E.L.D </strong>and learns about <strong>Project Insight</strong>, a way to <strong>preemptively</strong> eliminate <strong>threats</strong>.
              Fury is <strong>attacked</strong> by the <strong>Winter Soldier</strong> and warns Steve that S.H.I.E.L.D is <strong>compromised</strong>.
              <br><br><strong>Rogers</strong> and <strong>Romanoff</strong> recruit <strong>Wilson</strong>, aka <strong>Falcon</strong>. 
              They discover that Project Insight&#x27;s goal is to eliminate threats to <strong>Hydra</strong>, who is <strong>secretly</strong> reforming under <strong>Arnim Zola</strong>&#x27;s mind.
              <br><br><strong>Rogers</strong> discovers that the <strong>Winter Solider</strong> is his friend, <strong>Bucky</strong>, who was brainwashed and manages to <strong>stop</strong> Project Insight.
              <br><br><strong>Rogers</strong> and <strong>Wilson</strong> are planning to <strong>find Bucky</strong>.
              In the post-credit, we see <strong>Hydra</strong>' agent' with Loki&#x27;s <strong>scepter</strong> and two enhanced individuals.
            </p>
          {:else if sort == 4}
            <p class="paragraph">The <strong>fourth</strong> movie is the most critically acclaimed of Phase Two.
              It is taking us to space, and introduces the <strong>Guardians of the Galaxy</strong>.
              <br><br><strong>Peter Quill</strong> <em>(Chris Pratt) </em>finds a mysterious <strong>artifact</strong>, the <strong>Orb</strong>.
              <strong>Ronan</strong>, under the command of <strong>Thanos</strong>, sends <strong>Gamora</strong> <em>(Zoe Saldaña) </em>to retrieve the artefact.
              <br><br>After a fight, <strong>Quill</strong> and <strong>Gamora</strong> end up in prison with <strong>Rocket </strong><em>(Bradey Cooper)</em>, <strong>Groot </strong><em>(Vin Diesel)</em>, and <strong>Drax </strong><em>(Dave Bautista)</em>.
              Gamora reveals her plan to <strong>betray</strong> Ronan, and they <strong>escape</strong> the prison altogether.
              <br><br>They take the Orb to the <strong>Collector</strong>, who reveals that it is the <strong>Power Stone</strong>.
              With the help of the <strong>Ravagers</strong> and the <strong>Nova Corps</strong>, they fight Ronan&#x27;s force.
              <br><br>Using the force of the <strong>Stone</strong> together, the <strong>Guardians of the Galaxy</strong> manage to <strong>kill Ronan</strong>.
              The <strong>Power Stone</strong> is kept in safety with the <strong>Nova Corps</strong>.
              </p>
          {:else if sort == 5}
            <p class="paragraph">The <strong>fifth</strong> movie brings the <strong>heroes</strong> <span class="text-span-2"><sub class="subscript">○</sub></span> together and introduces new characters: <strong>Pietro</strong> <em>(Aaron Taylor-Johnson)</em> and <strong>Wanda </strong><em>(Elizabeth Olsen) </em><strong> Maximoff</strong><em>,</em> and <strong>Vision</strong> <em>(Paul Bettany).</em>
              <br><br>After the <strong>fall</strong> of the <strong>S.H.I.E.L.D</strong>, the <strong>Avengers</strong> raid a <strong>Hydra</strong> facility to retrieve Loki&#x27;s scepter.
              They fight <strong>Pietro</strong> and <strong>Wanda</strong> Maximoff.
              <br><br><strong>Stark</strong> and <strong>Banner </strong> discover that the scepter holds a <strong>gem</strong> with a conscious.
              They create <strong>Ultron</strong>, who decides that <strong>humanity</strong> must be <strong>eradicated</strong> to save the <strong>Earth</strong>. 
              <br><br><strong>Wanda</strong> and <strong>Pietro</strong> <strong>turn against</strong> Ultron.
              The <strong> Avengers</strong> discover that the gem is the <strong>Mind Stone</strong>; Combining <span class="text-span"><strong class="bold-text-2">JARVIS</strong></span>, the Stone, and a synthetic body, they create <strong>Vision</strong>.
              <br><br>Together, they fight <strong>Ultron</strong> and win.
              In the process, the country is <strong>destroyed</strong>, and <strong><span class="text-span"><strong class="bold-text-2">Pietro</strong></span> dies</strong>.
              <strong>Banner</strong> leaves Earth. <strong>Rogers</strong> and <strong>Romanoff</strong> plan to train the <strong>new Avengers</strong>: <strong>Rhodes</strong>, <strong>Vision</strong>, <strong>Wilson</strong>, and <strong>Wanda</strong>.
              <br><br><strong>Thanos</strong> decides to retrieve the Stones <strong>himself</strong>.
              </p>
            {:else if sort == 6}
            <p class="paragraph">The <strong>last</strong> movie of Phase Two introduces new characters: <strong>Scott Lang</strong> <em>(Paul Rudd)</em>, <strong>Hope van Dyne</strong> <em>(Evangeline Lilly)</em>, and <strong>Hank Pym</strong> <em>(Michael Douglas).</em>
              <br><br><strong>Pym</strong> invented a particle capable of <strong>increasing</strong> or <strong>reducing mass</strong>, <strong>density</strong>, and <strong>strength</strong><strong>.
              </strong>Fearing <strong>misuse, </strong>and decided to <strong>hide</strong> this technology.
              <strong>Cross</strong> <em>(Corey Stoll) </em> tries to replicate it with the <strong>Yellowjacket</strong>.
              <strong><br><br>Lang</strong> is released from prison but commits burglary again.
              He brakes into a house and steals a <strong>suit</strong>.
              He tries it and accidentally <strong>shrinks</strong> to the size of an <strong>ant</strong>.
              <br><br>Against the will of his daughter, <strong>Hope</strong>, Pym <strong>manipulated</strong> Scott to steal the suit to be the <strong>next Ant-Man</strong>.
              After training and fighting against <strong>Wilson</strong>, Lang and his crew manage to stop <strong>Cross</strong> and destroy the Yellowjacket.
              <br><br>In the end, Hank shows <strong>Hope</strong> a new suit, the <strong>Wasp</strong>. 
              <strong>Sam</strong> mentions that he &quot;know a guy&quot; to <strong>Rogers</strong>, who managed to find <strong>Bucky</strong>.
              </p>
          {/if}
        {:else}
          {#if sort == 1}
            <p class="paragraph"><strong>Civil War</strong> is the <strong>first movie</strong> of Phase Three and, by its <strong>scale</strong>, resembles more an <strong>Avengers</strong> movie than a <strong>Captain America</strong>.
              <br><br>The UN ratifies the <strong>Sokovia Accords</strong>, giving them more control over the <strong>Avengers</strong>.
              <strong>Stark</strong> is in <strong>favor</strong>, <strong>Rogers against</strong>.
              A <strong>bomb</strong>, presumably planted by <strong>Bucky Barnes</strong>, <strong>kills</strong> the king of <strong>Wakanda</strong>.
              His son, <strong>T&#x27;Challa</strong>, the <strong>Black Panther</strong>, wants revenge.
              <br><br>The real <strong>culprit</strong> is <strong>Zemo</strong>.
              <strong>Steve</strong>, <strong>Bucky</strong>, <strong>Sam</strong>, <strong>Wanda</strong>, <strong>Clint</strong>, and <strong>Scott</strong> are going <strong>against </strong><strong>orders</strong> to capture <strong>Zemo</strong>.
              <strong>Tony</strong>, <strong>Nathasha</strong>, <strong>T&#x27;Challa</strong>, <strong>James</strong>, <strong>Vision</strong>, and <strong>Peter</strong> try to stop them.
              <br> <br>Thanks to <strong>Natasha</strong>, <strong>Steve</strong> and <strong>Bucky </strong><strong>escape</strong>.
              <strong>Rhodes</strong> becomes partially <strong>paralyzed</strong>, and <strong>Steve&#x27;s</strong> crew is <strong>imprisoned</strong>.
              <strong>Tony</strong> goes after <strong>Steve</strong> and discovers that <strong>Bucky</strong> is responsible for his parent&#x27;s <strong>death</strong><strong></strong>.
              After a fight, <strong>Steve</strong> stops Tony, <strong>abandons</strong> his shield, and becomes a <strong>fugitive</strong>.
              <strong>Barnes</strong> is granted <strong>asylum</strong> in <strong>Wakanda</strong>.
            </p>
          {:else if sort == 2}
            <p class="paragraph">The second movie introduces a new important character, <strong>Dr.Strange</strong>, and an <strong>Infinity Stone</strong>.
              <br><br><strong>Stephen Strange</strong>, a famous <strong>neurosurgeon</strong>, <strong>loses</strong> the ability to use his <strong>hand</strong> in a <strong>car crash</strong>.
              Seeking a <strong>cure</strong>, Strange goes to <strong>Kamar-Taj</strong>.
              <br><br>With the help of the <strong>Ancient One </strong><em>(Tilda Swinton)</em>, <strong>Mordo </strong><em>(Chiwetel Ejiofor)</em>, and <strong>Wong </strong><em>(Benedict Wong)</em>, <strong>Strange</strong> learns about the <strong>Sanctums</strong> shielding the Earth, and the <strong>Eye of Agamotto</strong> that can bend <strong>time</strong>.
              <br><br><strong>Kaecilius </strong><em>(Mads Mikkelsen)</em>, a former student of <strong>Kamar-Taj</strong>, contacts <strong>Dormammu</strong>, who promises him <strong>eternal life </strong>for bringing the <strong>Dark Dimension</strong>.
              <br><br><strong>Kaecilius</strong> destroys the <strong>Sanctums</strong> and <strong>kills</strong> the <strong>Ancient One</strong>.
              As the Dark Dimension engulfs Earth, Strange uses the <strong>Eye of Agamotto</strong> to trap himself and <strong>Dormammu</strong> in an <strong>infinite </strong><strong>loop</strong>.
              Dormammu accepts to leave Earth <strong>alone</strong>.
              <br><br>The <strong>Eye of Agamotto</strong> is an <strong>Infinity Stone</strong>, and <strong>Strange</strong> accepts to help <strong>Thor</strong> and <strong>Loki</strong> to find <strong>Odin</strong>.
            </p>
          {:else if sort == 3}
            <p class="paragraph">In the <strong>third</strong> movie of <strong>Phase Three</strong>, we reunite with the <strong>Guardians of the Galaxy</strong>!
              <br><br>After <strong>stealing</strong> the batteries they were supposed to protect, the Guardians are <strong>attacked</strong>.
              They end up on a planet where they meet <strong>Ego</strong> <em>(Kurt Russell)</em>, a <strong>Celestial</strong> and <strong>Peter Quill</strong>&#x27;s<em>(Chris Pratt)</em> <strong>father</strong>.
              <br><br><strong>Yondu </strong><em>(Michael Rooker)</em> is hired to <strong>capture</strong> the Guardians.
              Meanwhile, Quill travels to Ego&#x27;s <strong>planet</strong> and meets <strong>Mantis</strong> <em>(Pom Klementieff)</em>.
              <br><br>To <strong>expand</strong>, Ego needs the power of <strong>another Celestial</strong>.
              To that end, he conceived <strong>progeny</strong> in countless worlds.
              Ego is the reason why Peter was <strong>abducted</strong> and his <strong>mother killed</strong>.
              <br><br>The <strong>Guardians</strong>, <strong>Mantis</strong>, <strong>Yondu</strong>, and <strong>Nebula</strong> <em>(Karen Gillan)</em>, team up to <strong>kill Ego</strong>.
              <span class="text-span"><strong class="bold-text-2">Yondu</strong></span> <strong>sacrifices</strong> to save Peter.
              The Guardians and the <strong>Ravager</strong> gather to give him a proper funeral.
              <br><br> <strong>Mantis</strong> joins the Guardians, and <strong>Nebula</strong> resumes her quest to kill <strong>Thanos</strong>.
              </p>
           {:else if sort == 4}
            <p class="paragraph">After being introduced in <strong>Civil War</strong>, it is time for <strong>Peter Parker</strong>, aka <strong>Spider-Man</strong>, to have his movie.
              <br><br>In 2012, <strong>Adrian Toomes&#x27;s</strong> <em>(Michael Keaton)</em> company is hired to <strong>clean</strong> New York.
              After <strong>losing</strong> the <strong>contract</strong>, he started creating and <strong>selling weapons</strong>.
              <br><br>After the event of <strong>Civil War</strong>, <strong>Parker</strong> continues to <strong>fight crimes</strong>.
              One day, Parker intercepts a weapons deal, but <strong>Toomes</strong> uses his <strong>Vulture</strong> suit to <strong>fight him</strong>.
              <br><br><strong>Stark</strong> rescues <strong>Parker</strong> and asks him to <strong>stop pursuing</strong> the criminals.
              Later, Parker <strong>fights</strong> Toomes again and puts <strong>many people</strong> in <strong>danger</strong>.
              Stark <strong>takes back</strong> Parker&#x27;s suit as <strong>punishment</strong>.
              <br><br>Eventually, Parker learns that Toomes plans to <strong>steal</strong> weapons from the <strong>Avengers Tower</strong> and <strong>stops</strong> him.
              In the end, Parker <strong>declines</strong> Stark&#x27;s invitation to <strong>join</strong> the <strong>Avengers</strong>.
              Stark <strong>returns</strong> him the <strong>Spider-Man</strong> suit.
              </p>
           {:else if sort == 5}
            <p class="paragraph">Thor is back in the <strong>fifth</strong> movie of Phase Three! 
              <br><br>With the help of <strong>Strange</strong>, <strong>Thor</strong> and <strong>Loki locate</strong> their father, <span class="text-span"><strong class="bold-text-2">Odin</strong></span>, who <strong>dies</strong>, freeing <strong>Hela</strong> <em>(Cate Blanchett)</em>.
              She is Odin&#x27;s first child and was <strong>imprisoned</strong> after becoming too <strong>ambitious</strong> and <strong>powerful</strong>.
              <br><br>Hella <strong>destroys</strong> Thor&#x27;s <strong>hammer</strong> and takes <strong>control</strong> of <strong>Asgard</strong>.
              Thor ends up on Sakaar where he&#x27;s enslaved by <strong>Valkyrie</strong> <em>(Tessa Thompson)</em> and forced to fight his friend from work, the <strong>Hulk</strong>.
              <br><br>Thor <strong>convinces</strong> Hulk and Valkyrie to <strong>help</strong> him <strong>save</strong> Asgard.
              Together, they <strong>fight</strong> Hela&#x27;s forces.
              <strong>Loki</strong> arrives and helps them <strong>rescue</strong> the citizens.
              <br><br>Thor sends Loki to revive the fire demon <strong>Surtur</strong>, who brings the prophesied <strong>Ragnarok</strong>, <strong>destroys</strong> Asgard, and <strong>kills Hela</strong>.
              <br><br><strong>Thor</strong>, now <strong>king</strong> of the Asgardians, decides to take his people to <strong>Earth</strong>. A <strong>spacecraft</strong> intercepts their vessel.
              </p>
           {:else if sort == 6}
            <p class="paragraph"><strong>Black Panther</strong> is the <strong>highest ranked</strong> movie of all MCU and expands on the <strong>eponymous</strong> character introduced in <strong>Civil War</strong>.
              <br><br>In <strong>1992</strong>, <strong>T&#x27;Chaka killed</strong> his <strong>brother N&#x27;Jobu</strong> for helping <strong>Klaue </strong><em>(Andy Serkis)</em> steal <strong>vibranium</strong>.
              <br><br><strong>T&#x27;Challa </strong><em>(Chadwick Boseman)</em><strong>,</strong> now <strong>king</strong> of Wakanda, tries to arrest Klaue, but <strong>Erik Stevens</strong> <em>(Michael B.Jordan)</em> manages to <strong>extract</strong> him.
              T&#x27;Challa learns that Erik, aka <strong>Killmonger</strong>, is <strong>N&#x27;Jobu&#x27;s son</strong>.
              <br><br>Killmonger <strong>kills</strong> Klaue, takes his body to Wakanda, and <strong>challenges</strong> T&#x27;Challa to <strong>ritual combat</strong>.
              T&#x27;Challa <strong>falls</strong> into a <strong>waterfall</strong> to his presumed <strong>death</strong>.
              <br><br>T&#x27;Challa is <strong>rescued</strong> and returns to <strong>fight</strong>.
              He manages to <strong>stab</strong> Killmonger, who <strong>refuses</strong> to be <strong>healed</strong>, preferring to <strong>die</strong> a <strong>free man</strong> rather than being <strong>enchained</strong>.
              <br><br>In the end, T&#x27;Challa <strong>reveals</strong> Wakanda&#x27;s true nature to the <strong>world</strong>, and <strong>Shuri </strong><em>(Letitia Wright)</em>, helps <strong>Bucky Barnes </strong>with his recovery.
              </p>
           {:else if sort == 7}
            <p class="paragraph"><strong>Infinity war </strong>is the <strong>seventh</strong> movie of <strong>Phase Three</strong>, <strong>tying</strong> almost all <strong>previous films</strong> and <strong>heroes</strong> <span class="text-span-2"><sub class="subscript">○</sub></span><strong>together</strong>.
              <br><br><strong>Thanos</strong>, having already acquired the <strong>Power Stone</strong>, intercepts <strong>Thor&#x27;s</strong> spaceship.
              He beats the <strong>Hulk</strong>, gets the <strong>Space Stone</strong>, and <strong>kills  <span class="text-span"><strong class="bold-text-2">Loki</strong></span></strong> and  <span class="text-span"><strong class="bold-text-2">Heimdall</strong></span>.
              <br><br><strong>Banner</strong> explains to <strong>Strange</strong>, <strong>Wong</strong>, and <strong>Stark</strong> that <strong>Thanos plans to destroy half of all life </strong> using the <strong>six Infinity Stones</strong>.
              At this moment, two of Thanos&#x27;s generals arrive to get the <strong>Time Stone</strong> and <strong>capture Strange</strong>.
              <strong>Parker</strong> and <strong>Stark</strong> sneak aboard the <strong>general&#x27;s spaceship</strong>.
              <br><br>The <strong>Guardians of the Galaxy</strong> rescue <strong>Thor</strong>.
              With <strong>Rocket</strong> and <strong>Groot</strong>, he travels to <strong>Nidavellir</strong> to get a <strong>new weapon</strong>.
              The other <strong>Guardians</strong> travel to the <strong>Collector</strong> to get the <strong>Reality Stone</strong> but arrive <strong>too late</strong>.
              <br><br><strong>Thanos</strong>, having three Stones, <strong>kidnaps Gamora</strong>, his daughter, and forces her to reveal the location of the <strong>Soul Stone</strong>.
              To get it, Thanos sacrifices <span class="text-span"><strong class="bold-text-2">Gamora</strong></span>.
                </p>
          {:else if sort == 8}
            <p class="paragraph"><br><strong>Maximoff</strong> and <strong>Vision</strong>, who exists thanks to the <strong>Mind Stone</strong>, are ambushed by Thanos&#x27;s generals.
              <strong>Rogers</strong>, <strong>Romanoff</strong>, and <strong>Wilson rescue</strong> them.
              The group travel to <strong>Wakanda</strong>, where they can <strong>extract</strong> the Stone <strong>without killing Vision</strong>.
              <br><br><strong>Stark</strong> and <strong>Parker rescue Strange</strong>.
              They land on <strong>Titan</strong>, where they meet <strong>Quill</strong>, <strong>Drax</strong>, <strong>Mantis</strong>, and <strong>Nebula</strong>.
              They make a plan to stop <strong>Thanos</strong> while <strong>Strange</strong> uses the Time Stone to <strong>view millions of possible</strong> futures, seeing only <strong>one</strong> in which they win.
              <br><br><strong>Thanos</strong> arrives, and the plan <strong>fails</strong> when <strong>Quill</strong> learns that Thanos <strong>killed</strong> Gamora.
              <strong>Strange offers</strong> the <strong>Time Stone</strong> to <strong>spare Stark&#x27;s</strong> life.
              <br><br><strong>Thanos's</strong> army <strong>invades</strong> Wakanda to get the last Stone.
              The <strong>Avengers</strong>, <strong>T&#x27;Challa</strong>, and <strong>Thor</strong>, armed with his new weapon, <strong>Stormbreaker</strong>, manage to <strong>repel</strong> the army.
              Unfortunately, <strong>Thanos arrives</strong> on the field, rapidly <strong>overpowers</strong> everyone, and finally <strong>rips the Stone</strong> from <strong> <span class="text-span"><strong class="bold-text-2">Vision</strong></span>&#x27;s</strong> forehead, <strong>killing him</strong>.
              <br><br>With all the Stones, <strong>Thanos snaps</strong> his fingers and <strong>eradicates half of all life</strong>.
              <span class="text-span"><strong class="bold-text-2">Barnes</strong></span>, <span class="text-span"><strong class="bold-text-2">T&#x27;Challa</strong></span>, <span class="text-span"><strong class="bold-text-2">Groot</strong></span>, <span class="text-span"><strong class="bold-text-2">Maximoff</strong></span>, <span class="text-span"><strong class="bold-text-2">Wilson</strong></span>, <span class="text-span"><strong class="bold-text-2">Mantis</strong></span>, <span class="text-span"><strong class="bold-text-2">Drax</strong></span>, <span class="text-span"><strong class="bold-text-2">Quill</strong></span>, <span class="text-span"><strong class="bold-text-2">Strange</strong></span>, <span class="text-span"><strong class="bold-text-2">Parker</strong></span>, <span class="text-span"><strong class="bold-text-2">Hill</strong></span>, and <span class="text-span"><strong class="bold-text-2">Fury</strong></span> are <strong>gone</strong>.
              Before vanishing, Fury can send an <strong>emergency signal</strong>.
              </p>
           {:else if sort == 9}
            <p class="paragraph"><strong>Ant-Man</strong> is back in the <strong>eighth</strong> movie of <strong>Phase Three</strong>.
              The <strong>events</strong> of this movie are happening <strong>before</strong> or <strong>at the same time</strong> as <strong>Infinity War</strong>.
              <br><strong></strong><br><strong>Hank Pym</strong> and <strong>Hope van Dyne</strong> try to open a tunnel to the <strong>Quantum Realm</strong> where Hope&#x27;s mother, <strong>Janet</strong>, may be <strong>trapped</strong>.
              <br><br>While retrieving a part needed for the tunnel, <strong>Hope</strong>, now wearing the <strong>Wasp</strong> outfit, is attacked by <strong>Ghost</strong>, who <strong>escapes</strong> with <strong>Pym&#x27;s lab</strong>.
              <br><br><strong>Ghost</strong> is <strong>Ava Starr</strong>, the daughter of one of Pym&#x27;s former partners who <strong>died</strong> during an <strong>experiment</strong> that caused her to be <strong>dying</strong> and constantly <strong>in pain</strong>.
              She plans to use <strong>Janet&#x27;s quantum energy</strong> to <strong>cure</strong> her.
              <br><br><strong>Lang</strong>, <strong>Pym</strong>, and <strong>Hope</strong> find the lab, and <strong>Pym rescues Janet</strong>, who helps <strong>Ava</strong> to <strong>stabilize</strong> her condition and <strong>end</strong> her <strong>suffering</strong>.
              <br><br><strong>Pym</strong>, <strong>Lang</strong>, <strong>Hope</strong>, and <strong>Janet</strong> plan to return to the <strong>quantum realm</strong><strong></strong>.
              While <strong>Lang</strong> is in it, the other three <strong>vanishes</strong>, leaving <strong>Lang stuck</strong>.
              </p>
          {:else if sort == 10}
            <p class="paragraph">The <strong>ninth</strong> movie of <strong>Phase Three</strong> introduces a new <strong>hero</strong>, <strong>Carol Danvers </strong><em>(Brie Larson)</em>, aka <strong>Captain Marvel</strong>.
              <br><br>In <strong>1995</strong>, during a mission, the <strong>shapeshifter</strong> Skrulls <strong>Talos </strong><em>(Ben Mendelsohn)</em> captures <strong>Vers</strong>, an <strong>amnesic </strong>Starforce member.
              She <strong>escapes</strong> and arrives on <strong>Earth</strong>, where she meets <strong>Nick Fury</strong>.
              <br><br><strong>Vers</strong> discovers her name is <strong>Carol Danvers</strong> and that she <strong>presumably died</strong> while testing an <strong>engine</strong> designed by <strong>Dr.
              Lawson</strong>.
              <strong>Yon-Rogg </strong><em>(Jude Law)</em>, Carol&#x27;s <strong>mentor</strong>, <strong>killed </strong><strong>Dr.
              Lawson</strong>, and by <strong>destroying</strong> the <strong>engine</strong>, <strong>Danvers</strong> gained <strong>powers</strong> but <strong>lost her memory</strong>.
              <br><br>Later, she learns that the <strong>Tesseract</strong> is the <strong>power source</strong> of Lawson&#x27;s engine.
              <strong>Danvers beats Yon-Rogg</strong> and gives <strong>Fury</strong> a <strong>pager</strong> to <strong>contact</strong> her in an <strong>emergency</strong>.
              She leaves Earth to help the <strong>Skrulls</strong> find a new <strong>home</strong>.
              <br><br>After the event of <strong>Infinity War</strong>, the remaining <strong>Avengers</strong> are <strong>monitoring</strong> Fury&#x27;s <strong>pager</strong>.
              <strong>Denver</strong> appears, asking for <strong>Fury</strong>.
              </p>
          {:else if sort == 11}
            <p class="paragraph"><strong>Avengers: Endgame</strong> is the <strong>penultimate</strong> movie of the <strong>Infinity Saga</strong>.
              No other MCU movie has that many <strong>main characters</strong> and <strong>essential arc endings</strong>.
              <br><br><strong>Danvers</strong> rescues <strong>Stark</strong> and <strong>Nebula</strong>.
              They reunite with the  survivors: <strong>Banner</strong>, <strong>Rogers</strong>, <strong>Thor</strong>, <strong>Romanoff</strong>, <strong>Rhodes</strong>, and <strong>Rocket</strong>.
              <br><br>They locate <strong>Thanos</strong> and plan to use the <strong>Infinity Stones</strong> to bring <strong>everyone </strong><strong>back</strong>.
              Unfortunately, he has already <strong>destroyed</strong> them.
              <strong>Thor</strong> aims for the head and <strong>kills </strong><strong>him</strong>.
              <br><br><strong>Five years later</strong>, <strong> Lang</strong> escapes from the <strong>Quantum Realm</strong> and <strong>theorizes</strong> that <strong>time travel is possible</strong>.
              <strong>Stark</strong> agrees to help build a <strong>time machine</strong> to find the <strong>Stones</strong> in the <strong>past</strong> and <strong>revert Thanos</strong>&#x27; actions.
              <strong>Banner</strong> recruits a <strong> Thor</strong>, and <strong>Romanoff</strong> recruits <strong>Barton</strong>.
              <br><br><strong>Banner</strong>, <strong>Lang</strong>, <strong>Rogers</strong>, and <strong>Stark </strong><strong>time-travel</strong> to <strong>2012</strong>.
              <strong>Banner</strong> gets the <strong>Time Stone</strong>, and <strong>Rogers</strong> the <strong>Mind Stone</strong>.
              <strong>Stark</strong> and <strong>Lang fail</strong> to get the <strong>Space Stone</strong> and allow<strong> 2012-Loki</strong> to <strong>escape</strong> with it, creating a <strong>Variant</strong>.
              </p>
          {:else if sort == 12}
            <p class="paragraph"><br><strong>Rogers</strong> and <strong>Stark</strong> travel to <strong>1970</strong>, where <br>they find an earlier version of <strong>Space Stone</strong>.
              <strong>Rocket</strong> and <strong>Thor</strong> travel to <strong>Asgard</strong> in <strong>2013</strong>, where they get the <strong>Reality Stone</strong> and retrieve Thor&#x27;s hammer, <strong>Mjolnir</strong>.
                <span class="text-span"><strong class="bold-text-2">Romanoff</strong></span> <strong>sacrifices herself</strong> to allow <strong>Clint</strong> to get the <strong>Soul Stone</strong>.
              <br><br><strong>Nebula</strong> and <strong>Rhodes</strong> travel to <strong>2014</strong>, where they steal the <strong>Power Stone</strong>.
              <strong>2014-Thanos</strong> captures <strong>Nebula</strong> and learns of his <strong>success</strong> and the <strong>Avengers&#x27; plan</strong>.
              He sends <strong>2014-Nebula</strong> to the <strong>present</strong>.
              <br><br>In the <strong>present, Banner </strong>uses the six <strong>Stones</strong> to <strong>bring </strong><strong>everyone back</strong>.
              At the same time, <strong>2014-Nebula</strong> brings <strong>Thanos</strong> and his <strong>army</strong> into the <strong>present</strong> and <strong>kills her older self</strong>.
              <br><br><strong>Thanos</strong> overpowers <strong>Stark</strong>, <strong>Thor</strong>, and <strong>Rogers</strong>, now worthy of holding <strong>Mjolnir</strong>.
              <strong>Strange</strong>, and the <strong>sorcerers</strong> arrive and open <strong>portals</strong> allowing <strong>everyone</strong> to <strong>come back</strong> and <strong>fight</strong>.
              <br><br><strong>Thanos</strong> manages to get the <strong>Stones</strong> again, but at the last moment,  <span class="text-span"><strong class="bold-text-2">Stark</strong></span> <strong>steals them</strong> and, <strong>at the cost of his life</strong>, uses them to <strong>stop Thanos</strong>.
              <br><br><strong>Thor</strong> joins the <strong>Guardians</strong>, and <strong>Rogers</strong> returns to the <strong>past</strong> to get the <strong>Stones</strong> to their <strong>proper timeline</strong>.
              He <strong>returns</strong> to the <strong>present</strong> as an <strong>older man</strong> and passes his <strong>shield</strong> to <strong>Sam Wilson</strong>.
              Steve decided to <strong>spend his life</strong> with his <strong>love</strong>, <strong>Peggy Carter</strong>.
              </p>
          {:else if sort == 13}
            <p class="paragraph"><strong>Concluding</strong> the <strong>Infinity Saga</strong> <em>(and this project for now)</em>, <strong>Spider-Man: Far From Home</strong> explores <strong>Parker&#x27;s future</strong> without <strong>Tony Stark</strong>.
              <br><br>Parker&#x27;s school organizes a <strong>trip</strong> to <strong>Europe</strong>.
              In <strong>Venice</strong>, <strong>Parker</strong> fights an <strong>Elemental</strong> alongside <strong>Quentin Beck</strong> <em>(Jake Gyllenhaal)</em>, a  <strong>powerful </strong><strong>hero</strong> from <strong>another universe</strong>.
              <br><br><strong>Fury</strong> gives <strong>Parker Stark&#x27;s glasses</strong>, containing <strong>EDITH</strong>, an <strong>AI</strong> with access to <strong>orbital weapons</strong>.
              Eventually, <strong>Parker </strong>gives the <strong>glasses</strong> to <strong>Beck</strong>.
              <br><br><strong>Beck</strong> was using <strong>drones </strong>to <strong>simulate</strong> his <strong>powers</strong> and the <strong>Elementals</strong>.
              He plans to use <strong>EDITH</strong> to become an <strong>Avenger</strong>.
              <strong>MJ</strong> <em>(Zendaya)</em> discovers that <strong>Parker</strong> is <strong>Spider-Man</strong>.
              <br><br>In <strong>London</strong>, <strong>Peter</strong> regains <strong>control</strong> of <strong>EDITH</strong> and <strong>defeats Beck</strong>.
              In the end, <strong>Jameson</strong> <em>(J. K. Simmons)</em> reveals <strong>Spider-Man&#x27;s secret identity</strong> to the world and <strong>accuses</strong> him of killing <strong>Beck</strong>.
              <strong>Fury</strong> and <strong>Hill</strong> were, in fact, <strong>Talos</strong> and <strong>Soren</strong> in <strong>disguise</strong>.
              </p>
          {/if}
        {/if}
      </div>
    </div>
  </div>
</div>