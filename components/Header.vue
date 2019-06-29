<template>
 <nav class="navbar">
     <div class="container">
         <div class="navbar-menu">
             <nuxt-link to="/" class="navbar-item">MET-Viewer</nuxt-link>
             <div class="navbar-item has-dropdown is-hoverable">
                 <nuxt-link to="/" class="navbar-link">departments</nuxt-link>
                 <div class="navbar-dropdown">
                     <nuxt-link to="/departments/asia" class="navbar-item">
                       <span>
                           <strong>Asian Art</strong>
                       </span>
                     </nuxt-link>
                     <nuxt-link to="/departments/egypt" class="navbar-item">
                       <span>
                           <strong>Egyptian Art</strong>
                       </span>
                     </nuxt-link>
                 </div>
             </div>
         </div>
     </div>
 </nav>
</template>
