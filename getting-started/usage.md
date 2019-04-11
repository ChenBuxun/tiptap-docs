# Basic Usage

You can create a working editor with very little code. The basic building blocks you need are the 
[`Editor` class][@editor-class] and the [`EditorContent` component][@editor-content-component]

```vue
<template>
  <editor-content :editor="editor" />
</template>

<script>
// Import the basic building blocks
import { Editor, EditorContent } from 'tiptap'

export default {
  components: {
    EditorContent,
  },
  data() {
    return {
      editor: null,
    }
  },
  mounted() {
    // Create an `Editor` instance with some default content. The editor is 
    // then passed to the `EditorContent` component as a `prop`
    this.editor = new Editor({
      content: '<p>This is just a boring paragraph</p>',
    })
  },
  beforeDestroy() {
    // Always destroy your editor instance when it's no longer needed
    this.editor.destroy()
  },
}
</script>
```

[@editor-class]: ../api/classes.md#editor
[@editor-content-component]: https://github.com/scrumpy/tiptap/blob/master/packages/tiptap/src/Components/EditorContent.js