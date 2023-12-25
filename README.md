# Learn Vue.JS in 2024

I am learning Vue.JS from different Video Courses, Books, and Websites

## Few Points

### Options API

> The Options API is the original API for defining components in Vue.js. It's called the Options API because you define a component by passing an options object to Vue's Vue.component method. This object can contain options like data, methods, computed, watch, props, components, and lifecycle hooks like created, mounted, etc.
> In this example, data, methods, and created are options that define the component's data, methods, and a lifecycle hook, respectively.

```javascript
Vue.component('my-component', {
  data: function() {
    return {
      message: 'Hello, Vue!'
    }
  },
  methods: {
    greet: function() {
      alert(this.message);
    }
  },
  created: function() {
    console.log('my-component is created');
  }
});
```

### Composition API

> The Composition API is a new way to define components in Vue.js, introduced in Vue 3. It provides a set of function-based APIs that allow flexible composition of component logic.
> The Composition API was introduced to address several limitations of the Options API, especially when dealing with large components and reusing logic between components.
> In this example, setup is a new lifecycle hook where we define the component's reactive data and functions. We use ref to create a reactive reference to a value. The setup function returns an object that exposes the public interface of the component.

```javascript
import { ref } from 'vue';

export default {
  setup() {
    const message = ref('Hello, Vue!');
    
    function greet() {
      alert(message.value);
    }

    // Lifecycle hooks are also available
    onMounted(() => {
      console.log('Component is mounted');
    });

    // Expose the public interface
    return {
      message,
      greet
    };
  }
};
```

### Local Component

> In Vue.js, a local component is a component that is registered within another component, and it's only available within the scope of that component where it's registered. This is in contrast to global components, which are registered on the Vue instance itself and are available throughout the entire application.
> In this example, ChildComponent is a local component that is only available within ParentComponent. It's registered in the components option of ParentComponent.

```javascript
// Define the child component
const ChildComponent = {
  template: '<p>This is a child component!</p>'
};

// Define the parent component
const ParentComponent = {
  components: {
    'child-component': ChildComponent
  },
  template: '<div><child-component></child-component></div>'
};
```

### Global Component

> In Vue.js, a global component is a component that is registered on the Vue instance itself, making it available throughout the entire application. This is in contrast to local components, which are registered within another component and are only available within the scope of that component.
> In this example, my-component is a global component that is registered using Vue.component. It's available to be used anywhere in the application.

```javascript
// Define the component
Vue.component('my-component', {
  template: '<p>This is a global component!</p>'
});

// Now 'my-component' can be used in any part of the application
new Vue({
  el: '#app',
  template: '<div><my-component></my-component></div>'
});
```
