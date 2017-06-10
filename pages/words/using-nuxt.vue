<template>
  <section class="container long-text">
    <h1>Building a simple static site using <a href="https://nuxtjs.org/">Nuxt.js</a></h1>
    <p>
      I decided to build this site using Nuxt/Vue to familiarize myself with this next generation of client-side JS frameworks.  I chose Nuxt/Vue over Gatspy/React primarily it seemed more straight-forward and lightweight. I work mostly in Ruby/Rails with a little bit of Python, and hope that the following will be useful to anyone with a similar background who is interested in dabbling with the this framework.
    </p>
    <h2>What is Nuxt? Why use it?</h2>
    <p>
      Here's the party line: <b>"Nuxt is framework for generating Universal Applications in Vue"</b>. OK, so two questions then: what is Vue? and what why do we care about making a Universal Application in Vue?
    </p>
    <h3>Vue</h3>
    <p>
      Vue is a Progressive Javascript Framework that is more approachable than React and modestly more performant. Like React, it implements a Virtual DOM which at first glance seems like an overly-complicated way of manipulating the regular DOM, but apparently there are some payoffs if you just grin and bear it! 😬
    </p>
    <p>
      Unlike React, Vue is more focused on the the <i>view</i> layer.  The feature that most attracted me to this framework is a more natural approach to templating using straight HTML instead of rendering DOM components in JS or JSX.  It also scopes CSS to components which is an approach I simultaneously love and fear as a Rails developer.
    </p>
    <h3>What is a Universal Application?</h3>
    <p>
      A Universal Application (some people say "<i>Isomorphic</i> Application") has the special property of rendering itself on the client side or the server side.  One upshot here is that you only have one template and one templating language to consider for rendering views.  
    </p>
    <p>
      The dominant paradigm in Rails is to render a view on the server using embedded ruby, then pass it to the client, and then if you want to change the view without reloading the entire page, you will have to wrap a lot of logic around the view to either (1) get another updated view from the server, or (2) manipulate the view in the client using another batch of logic. Not so in a Universal App.  There is just one template at play and both the client and server are capable of rendering it.
    </p>
    <h3>
      Isn't a static website the <i>last</i> thing you'd need a universal application for?
    </h3>
    <p>
      I'm writing this very paragraph in HTML for godsakes... why on earth bother with a relatively large framework for serving straight HTML?  
    </p>
    <p>
      The main reason for me is developer productivity. It's easy to forget how much it sucks to make a site in straight HTML.  There are no partials, there are no layouts, there is no built-in routing logic, there is no server.  And if you <i>do</i> care about having a slick, modern-feeling web UX, you're going to have to build a fair amount of complexity anyway.  
    </p>
    <p>
      <b>The price:</b> a few more KBs of Javascript and a a 5 minute set-up.
    </p>
    <p>
      <b>The value:</b> templates, server, routing, modern UX, hot reloading, easy access to node modules.
    </p>

    <h2>Installing is really easy.</h2>
    <p>
      Installing Nuxt is easy. I'm assuming that you have <a href="https://www.npmjs.com/get-npm">npm</a> already.
    </p>
    <p>      
      First you need to install the Vue client.
      <code>
        $ npm install -g vue-cli
      </code>
    </p>
    <p>
      Then install the Nuxt.js starter template:
      <code>
        $ vue init nuxt/starter [project-name]
      </code>
    </p>      
    <p>
      Next run <code>npm install</code> to install dependencies for Nuxt.js that are located in <b>package.json</b>.
    </p>
    <p>
      Finally boot up the development server using:
      <code>
        $ npm run dev
      </code>
    </p>
    <h2>Configuring Stylesheets</h2>
    <p>
      After years of working in SASS, I deeply loathe the thought of using anything else for styling. Similarly, I can't really begin to look at template without thinking about a grid. So let's configure Nuxt to take compile SASS and use Bootstrap 3.
    </p>
    <p>
      Unfortunately, stylesheet preprocessors do not come out of the box. In order to get those working you'll need the following modules:
      <code>
        npm install --save-dev node-sass sass-loader
      </code>
    </p>

    <p>
      Now in your on your pages, such as "pages/index.vue" you can specify which language you'd like for your stylesheet:
    </p>
    <pre>
      <code>      
        &ltstyle lang="sass"&gt
          .container
            min-height: 100vh
            display: flex
            justify-content: center
            align-items: center
            text-align: center
            border: 3px solid black
            .
            .
            .
        &lt/style&gt
      </code>  
    </pre>

    <p>
      While I really like how stylesheets are segmented in Vue, it's always helpful to have global styles as well and I find it more useful to have those contained in an actual stylesheet rather than the default layout vue. To create a global stylesheet add a new file "assets/css/main.sass" and move whatever global styling you like in there.  To hook this up to the server go to 'nuxt.config.js' and add a new line to the exports object:
    </p>
    <pre>    
      <code>
        .
        .
        .
        css: [
          { src: '~assets/css/main.sass', lang: 'sass' }
        ],
        .
        .
        .
      </code>
    </pre>
  </section>
</template>

<script>
  export default {}
</script>
