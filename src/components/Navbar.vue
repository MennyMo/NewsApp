
<template>
  <div>
      <div class="nav-headline">
          <h1>Molly's News From Around The Globe</h1>
      </div>
      <header id="header">
	<nav class="links" style="--items: 7;">
        <router-link :to="{name: 'Category', params: {category: 'general'}}" class="a">General</router-link>
        <router-link :to="{name: 'Category', params: {category: 'business'}}" class="a">Business</router-link>
        <router-link :to="{name: 'Category', params: {category: 'entertainment'}}" class="a">Entertainment</router-link>
        <router-link :to="{name: 'Category', params: {category: 'health'}}" class="a">Health</router-link>
        <router-link :to="{name: 'Category', params: {category: 'science'}}" class="a">Science</router-link>
        <router-link :to="{name: 'Category', params: {category: 'sports'}}" class="a">Sports</router-link>
        <router-link :to="{name: 'Category', params: {category: 'technology'}}" class="a">Technology</router-link>      
		<span class="line"></span>
    <!-- <select v-model="currentSource" name="category" id="category" class="select-menu">
        <option :value="''">All</option> -->
        <!-- <option v-for="{ name, id} in getAllSources" :key="id" :value="id">{{name}} </option> -->
    <!-- </select> -->
	</nav>
   <router-view/>
</header>
 
  </div>
</template>

<script>

</script>

<style>
    .links {
	background-color: #123;
	background-image: linear-gradient(to bottom, #0003, transparent);
	border-bottom: 1px solid #0003;
	box-shadow: 0 0 32px #0003;
	font-size: 1em;
	font-weight: 300;
}
.links > .a {
	color: #9ab;
	padding: .50em;
	text-align: center;
	text-decoration: none;
	transition: all .5s;
}
.links > .a:hover {
	background: #ffffff06;
	color: #adf;
}
.links > .line {
	background: #68a;
	height: 1px;
	pointer-events: none;
}

/* The Magic */
/* #header {
	position: fixed;
	top: 0;
	left: 0;
	right: 0;
} */
.links {
	display: grid;
	grid-template-columns: repeat(var(--items), 1fr);
	position: relative;
}
.links > .line {
	opacity: 0;
	transition: all .5s;
	position: absolute;
	bottom: 0;
	left: var(--left, calc(100% / var(--items) * (var(--index) - 1)));
	width: var(--width, calc(100% / var(--items)));
	--index: 0;
}

.links > .a:hover ~ .line {
	opacity: 1;
}

.links > .a:nth-of-type(1):hover ~ .line { --index: 1; }
.links > .a:nth-of-type(2):hover ~ .line { --index: 2; }
.links > .a:nth-of-type(3):hover ~ .line { --index: 3; }
.links > .a:nth-of-type(4):hover ~ .line { --index: 4; }
.links > .a:nth-of-type(5):hover ~ .line { --index: 5; }
.links > .a:nth-of-type(6):hover ~ .line { --index: 6; }
.links > .a:nth-of-type(7):hover ~ .line { --index: 7; }
.links > .a:nth-of-type(8):hover ~ .line { --index: 8; }
.links > .a:nth-of-type(9):hover ~ .line { --index: 9; }
.links > .a:nth-of-type(10):hover ~ .line { --index: 10; }
.links > .a:last-of-type:hover ~ .line { --index: var(--items); }
</style>