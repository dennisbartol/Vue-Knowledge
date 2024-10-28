<h4>Typescript in Vue</h4>


Using TypeScript in Vue 3 is a powerful way to leverage type safety, better tooling, and a more robust development experience. Vue 3 has first-class support for TypeScript, making it easy to integrate.

Here's a step-by-step guide to get started using TypeScript in a Vue 3 project:

### 1. Setting Up a Vue 3 Project with TypeScript

You can create a new Vue 3 project with TypeScript using Vue CLI or Vite.

#### Using Vue CLI:
1. Install Vue CLI (if not already installed):
   ```bash
   npm install -g @vue/cli
   ```

2. Create a new project:
   ```bash
   vue create my-vue-ts-app
   ```

3. When prompted, select `Manually select features` and choose:
   - `TypeScript`
   - Optionally, you can also select `Router`, `Vuex`, or other features as per your needs.

4. Configure additional TypeScript options:
   - Class-style components or composition API (choose the one that suits your preference).

5. After this, Vue CLI will create the project and configure TypeScript automatically.

#### Using Vite:
Vite is a fast and modern build tool that's perfect for Vue 3 with TypeScript.

1. Install Vite:
   ```bash
   npm init vite@latest my-vue-ts-app
   ```

2. When prompted, select `Vue` or `Vue with TypeScript`.

3. Navigate to the project folder:
   ```bash
   cd my-vue-ts-app
   ```

4. Install dependencies:
   ```bash
   npm install
   ```

5. Run the development server:
   ```bash
   npm run dev
   ```

### 2. TypeScript Basics in Vue 3

#### Script Setup

In Vue 3, the `<script setup>` syntax is preferred for using TypeScript. It makes the code cleaner and more type-safe.

Here’s a simple example:

```vue
<template>
  <div>
    <p>{{ message }}</p>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const message = ref<string>('Hello, TypeScript with Vue 3!');
</script>
```

**Explanation:**
- `lang="ts"` in the `<script setup>` block tells Vue that this is a TypeScript file.
- The `ref<string>` defines `message` as a reactive reference with the type `string`.

#### Composition API with TypeScript

If you're using the Composition API without `<script setup>`, you can write components like this:

```vue
<template>
  <div>{{ count }}</div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const count = ref<number>(0);

    function increment(): void {
      count.value++;
    }

    return {
      count,
      increment,
    };
  },
});
</script>
```

#### Type Annotations

You can use TypeScript’s type annotations for props, emits, and other component options:

1. **Typing Props:**

   ```vue
   <template>
     <div>{{ name }}</div>
   </template>

   <script setup lang="ts">
   defineProps<{
     name: string;
     age: number;
   }>();
   </script>
   ```

2. **Typing Emits:**

   ```vue
   <template>
     <button @click="submit">Submit</button>
   </template>

   <script setup lang="ts">
   const emit = defineEmits<{
     (event: 'submit'): void;
   }>();

   function submit() {
     emit('submit');
   }
   </script>
   ```

3. **Typing Component Methods:**

   ```vue
   <script lang="ts">
   import { defineComponent } from 'vue';

   export default defineComponent({
     methods: {
       greet(name: string): string {
         return `Hello, ${name}`;
       }
     }
   });
   </script>
   ```

### 3. Vue 3 Typing Features

Vue 3 provides built-in types that you can leverage for better TypeScript integration:

- **`defineComponent`**: This helps Vue infer types for your component’s props, emits, and options.
- **`ref`, `reactive`, `computed`, `watch`**: All these Composition API methods are fully typed.
- **`defineProps` and `defineEmits`**: When using `<script setup>`, you can define props and emits with TypeScript type inference.

### 4. Configuring `tsconfig.json`

When setting up TypeScript with Vue, you'll get a default `tsconfig.json` file. Some common settings for Vue 3 projects are:

```json
{
  "compilerOptions": {
    "target": "esnext",
    "module": "esnext",
    "moduleResolution": "node",
    "strict": true,
    "jsx": "preserve",
    "esModuleInterop": true,
    "skipLibCheck": true,
    "allowSyntheticDefaultImports": true,
    "forceConsistentCasingInFileNames": true,
    "types": ["vite/client"],
    "baseUrl": ".",
    "paths": {
      "@/*": ["src/*"]
    }
  },
  "include": ["src/**/*.ts", "src/**/*.d.ts", "src/**/*.tsx", "src/**/*.vue"]
}
```

Ensure you have `"strict": true` to enforce strict type-checking in your Vue 3 TypeScript project.

### 5. Vue Devtools and TypeScript

Vue Devtools can also work smoothly with TypeScript. Just make sure you are using Vue Devtools 6+, which has better support for Vue 3 and Composition API components.

### 6. Using TypeScript Interfaces for Props

You can define complex props using TypeScript interfaces or types:

```vue
<template>
  <div>{{ user.name }}</div>
</template>

<script setup lang="ts">
interface User {
  name: string;
  age: number;
}

const props = defineProps<{ user: User }>();
</script>
```

### 7. Recommended Tools and Plugins

- **Vetur** (for Vue 2) or **Volar** (for Vue 3) in VSCode: Volar is highly recommended for better TypeScript support in Vue 3.
- **ESLint**: Configure ESLint with TypeScript to maintain consistent code quality.

### Conclusion

Through following these steps, you can easily integrate TypeScript into your Vue 3 project, gaining all the benefits of static typing and type checking. With the powerful Composition API and the `<script setup>` syntax, TypeScript in Vue 3 becomes even more seamless and intuitive.
