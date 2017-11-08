# May be a bug with Vuetify Drawers and Nuxt....

## Issue
<v-content> keeps padding-left style when navigating from a layout with a permanent left drawer to a layout with a temporary right drawer.

## Expected
<v-content> padding to be removed as the permanent left drawer is no longer there.

## To replicate
Clone this repo to local, then `npm i`, then `npm run dev`. Go to `http://localhost:3000`. On the drawer to the left, click on the 'Temp Right' list tile to take you to the temp-right page. This page has a different layout with no left drawer, but instead it has a temporary right drawer. You'll notice that the <v-layout> on this page still has the padding-left as if there is still a permanent left drawer. Refresh the page and it fixes, but go back to home (index ('/')) and repeat -> same issue.

If you remove the `right` prop from the temporary drawer, it fixes.


# Not sure if I'm missing something somewhere or if this is a bug!
