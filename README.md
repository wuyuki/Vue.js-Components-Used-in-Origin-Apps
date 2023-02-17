## Vue.js Component Used in Origin Apps

### Introduction
Vue.js components allow us to split the HTML dialog into independent and reusable pieces, but Vue provides few built-in components that cannot cover various UI designs. Although we can introduce other MIT-licensed UI component frameworks into apps, this will also increase the file size. It seems unacceptable that we use only one component but end up with a large-size opx file.

In general, we implement our own component model that allows us to encapsulate custom content and logic, but luckily we can reuse these components in different Apps.

I am collecting some commonly used components that I created. Hope this can help us to build HTML dialog for apps easily.

### Components

1. <b>[Drag and Drop Text Box](./demo/Drag%20and%20Drop%20Text%20Box)</b>
   
   Used in 3D Windrose App, Graph Maker App and etc.

   <img src="./src/images/demo/Drag and Drop Text Box.gif" width="600">

2. <b>[Multi-Select](./demo/Multi-Select)</b>
   
   Used in Correlation Plot App.

   <img src="./src/images/demo/Multi-Select.gif" width="600">

3. <b>[Sortable and Searchable Tables](./demo/Sortable%20and%20Searchable%20Tables)</b>
   
   Used in X-Ray Diffraction Analysis App and Extract Graph Data App.

   <img src="./src/images/demo/Sortable and Searchable Tables.gif" width="600">

4. <b>[Textbox with Dropdown](./demo/Textbox%20with%20Dropdown)</b>
   
   Used in Common Bar Width App.

   <img src="./src/images/demo/Textbox with Dropdown.gif" width="600">

5. <b>[Pagination](./demo/Pagination)</b>
   
   Used in Matrix Analysis App.

   <img src="./src/images/demo/Pagination.gif" width="600"> 

6. <b>[Tabs](./demo/Tabs)</b>

    Used in Matrix Analysis App.

    <img src="./src/images/demo/Tabs.gif" width="600">  

7. <b>[Dropdown Menu](./demo/Dropdown%20Menu)</b>

    Used in NMR Tools App.

    <img src="./src/images/demo/Dropdown Menu.gif" width="600"> 

### How to Use
#### 1. Defining a Component
We can define a vue component as a plain javascript object, like:

```js
<script type="text/x-template" id="navbar-template">
…
</script>

<script>
Vue.component("navbar", {
template: "#navbar-template",
…
});
</script>
```

#### 2. Decorating a Component
Use CSS to decorate a component:

```html
<style>
/* Navbar */
	…
/* END Navbar */
</style>
```

#### 3. Using a Component
Components can be reused as many times as you want in the DOM:

```html
<navbar></navbar>
```

To render the component on our dialog, we need to pass data to a custom attribute:

```html
<navbar :menu="menu_data" :selected_menu="selected_menu"></navbar>
```
Also, some features of the component may require communicating back up to the dialog. We can use v-on or @ to listen to any event on the component instance:
```html
<navbar :menu="menu_data" 
    :selected_menu="selected_menu"
    @update_selected_menu="onSelectMenu">
</navbar>
```

