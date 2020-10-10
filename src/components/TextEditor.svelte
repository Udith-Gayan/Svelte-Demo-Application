<script>
    import marked from 'marked';

    export let headingText;

    let sourceText = `
# H1 heading

## H2 heading

### H3 heading

---

**bold text**

*italicized text*

---

1. First item
2. Second item
3. Third item

- First item
- Second item
- Third item

[Svelte](https://svelte.dev/)
`;
$: markdownText = marked(sourceText);

function clearText() {
    sourceText = '';
}
</script>


    <header class="header">
        <h1 class="header-title">{headingText}</h1>
    </header>

    <div class="buttonRow">
        <button on:click={clearText}>Clear All</button>
    </div>
    
    <div class="markdown-editor">
        <div class="left-panel">
            <textarea bind:value={sourceText} class="source"></textarea>
        </div>
    
        <div class="right-panel">
            <div class="output">{@html markdownText}</div>
        </div>
    </div>



<style>
    .header {
        height: 10vh;
        display: flex;
        align-items: center;
        justify-content: center;
    
    }
    .header-title {
        margin: 0;
        color:#fff;
    }

    .buttonRow {
        display: flex;
        flex-direction: row;
    }


    .markdown-editor {
        width: 100%;
        display: flex;
        align-items:flex-start;
        justify-content: space-evenly;
    }
    .left-panel, .right-panel {
        width: 50%;
        border: solid 1px black;
        height: 85vh;
        background: #ffffff;
    }
    .right-panel {
        overflow: auto;
    }
    .source {
        border: none;
        width: 100%;
        height: 100%;
        background: #001628;
        color: #83ba52;
    }
    .source:focus {
        outline: none;
    }
    .output {
        width: 100%;
        padding: 0 2em;
    }
</style>