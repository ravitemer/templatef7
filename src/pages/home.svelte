<Page name="home">
  <!-- Top Navbar -->
  <Navbar large sliding={false}>
    <NavLeft>
      <Link iconIos="f7:menu" iconAurora="f7:menu" iconMd="material:menu" panelOpen="left" />
    </NavLeft>
    <NavTitle sliding>Test</NavTitle>
    <NavRight>
      <Link iconIos="f7:menu" iconAurora="f7:menu" iconMd="material:menu" panelOpen="right" />
    </NavRight>
    <NavTitleLarge>Test</NavTitleLarge>
  </Navbar>
  <!-- Toolbar -->
  <Toolbar bottom>
    <Link>Left link</Link>
    <Link>Right Link</Link>
  </Toolbar>
  <div class="bg-green-200 w-full overflow-scroll flex ">
    {#each items as item}
      <div class="flex-auto flex-shrink-0">
        <Post {...item}>

        </Post>
        
      </div>
    {:else}
      No items
    {/each}
  </div>
</Page>
<script>
  import {
    Page,
    Navbar,
    NavLeft,
    NavTitle,
    NavTitleLarge,
    NavRight,
    Link,
    Toolbar,
    Block,
    BlockTitle,
    List,
    ListItem,
    Row,
    Col,
    Button
  } from 'framework7-svelte';
  import Post from '../components/post.svelte';

  let items = [
    {
      App : "Twitter",
      Text : "this  ish  isdi  his  ishdfh jshjdh jhdjh sd shjfh  sdjhfjh jhjhfjs hjdhjdh fad jfhjshd "
    },
    {
      App : "Twitter",
      Text : "this  ish  isdi  his  ishdfh jshjdh jhdjh sd shjfh  sdjhfjh jhjhfjs hjdhjdh fad jfhjshd "
    },
    {
      App : "Twitter",
      Text : "this  ish  isdi  his  ishdfh jshjdh jhdjh sd shjfh  sdjhfjh jhjhfjs hjdhjdh fad jfhjshd "
    }
  ]
</script>