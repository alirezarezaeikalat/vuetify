Check this site:
  https://vuetifyjs.com/

1. We can add vuetify by:
    vue add vuetify


[ATTENTION]
3. in vuetify we can have props for vuetify components
  for example: <v-toolbar app dark height="150">
  it has three props, one with value
  app props make it fixed at the top

  class="pink" is same as color="pink"

4. we also like materialize we have lots of classes.

5. we have classes for text and background colors:

  <p class="red white--text"></p>
  we also can use lighten-4 or darken-4 or
   text--darken-4 text--lighten-4

6. We have classes for Typography:
                      These classes are based on sp size
  .display-{1 to 4}
  .headline
  .title
  .subtitle-{1 to 2}
  .body
  .font-weight-{}
  .text-{lowercase or uppercase capitalize}

7. we have button and icon components in vuetify:
    
  <v-btn class="pink white--text">Click me</v-btn>
  <v-btn color="pink">Click me</v-btn>
  <v-btn depressed color="pink">Click me</v-btn> :  depressed takes away the
                                                    shadow around button
  <v-btn text color="pink">Click me</v-btn> : makes the button transparent
                                              and when you hover there is pink
                                              bg
  <v-btn depressed class="pink white-text">
    <v-icon left>email</v-icon>
    <span>Email me</span>
  </v-btn>

[ATTENTION] : with Vue CLI 3 we has no index.html in
the src folder so alternatively you can:
      npm install  material-design-icons-iconfont
and import it in the main.js file:
    import 'material-design-icons-iconfont/dist/material-design-icons.css'
or add config to vuetify instance in plugin/vuetify.js
    


  we have small or large prop for v-btn and for v-icon
  we have fab prop to make the buttons circle                              
    
8. Breakpoints in Vuetify:

    xs  < 600px
    sm   600px> <960px
    md   960px> <1264px
    lg   1264px> <1904px
    xl   > 1904px

  <v-row>
      <v-col
        cols="12"
        md="8"
      >
  </v-row>

9. we can hide elements on certain sizes:

    <v-btn class="hidden-md-and-down">Click</v-btn>
    <v-btn class="hidden-md-only">Click</v-btn>
    <v-btn class="hidden-md-and-up">Click</v-btn>
    
//// Menus /////

10. We can have toolbar in vuetify:

  <v-toolbar flat class="grey lighten-4">
    <v-app-bar-nav-icon v-on:click="drawer = !drawer">
    </v-app-bar-nav-icon>
    <v-toolbar-title class="text-uppercase grey--text">
      <span class="font-weight-light">Todo</span>
      <span>Ninja</span>
    </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn text color="grey">
      <span left>Sign Out</span>
      <v-icon right>exit_to_app</v-icon>
    </v-btn>  
  </v-toolbar>
  <v-navigation-drawer v-model="drawer" app class="indigo">
      <p>Test</p>
  </v-navigation-drawer>

11. We also have <v-app-bar></v-app-bar> that we can use
    instead of <v-toolbar>

///// End of menu //////

[ATTENTION]
12. Under the hood vuetify uses flex for organizing elements
    there is <v-spacer></v-spacer> component that takes
    all the space that available for it, it is like
    space-between in flex

13. We can override materialize themes like primary, sucess
  and other themes in vuetify.js file:

    export default new Vuetify({
      icons: {
        iconfont: 'md'
      },
      // this is the spot to modify
      theme: {
        themes: {
          light: {
            primary: '#9652ff'
          }
        }
      }
    });

14. There are tons of list model in vuetify,
    lists are like ul tags you can choose different model
    from vuetify site: (an example)
    <v-list class="primary">
        <v-list-item
          v-for="(link, i) in links"
          :key="i"
          router v-bind:to="link.route"
        >
          <v-list-item-icon>
            <v-icon class="white--text">{{ link.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title class="white--text">{{ link.text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>

15. If we want to change something to a tag we can add
  router and to="" prop to that element:

    <v-list-item router to="/">
    </v-list-item>
      
    