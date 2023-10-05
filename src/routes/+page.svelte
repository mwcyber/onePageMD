<script>
  import { onMount, afterUpdate } from "svelte";
  import { marked } from "marked";

  const files = [
    { value: "page01.md", label: "Page one label" },
    { value: "page02.md", label: "Page two label" }
  ];

  let markdownContent = "";
  let selectedFile = files[0].value;

  async function loadMarkdownContent() {
    try {
      const response = await fetch(`/pages/${selectedFile}`);
      markdownContent = marked(await response.text());
    } catch (error) {
      console.error("Error loading md file:", error);
    }
  }

  onMount(() => {
    loadMarkdownContent();
  });

  afterUpdate(() => {
    loadMarkdownContent();
  });
</script>

{#if markdownContent}
  <div class="container">
    <div class="nav">
      <div class="container-fluid">
        <div class="row align-items-center">
          <div class="col">
            <h5>
              Hi, welcome to onePageMD!
            </h5>
          </div>
          <div class="col">
            <p>SELECT INDEX:</p>
            <p>
              <select bind:value={selectedFile} class="form-select">
                {#each files as file}
                  <option value={file.value}>{file.label}</option>
                {/each}
              </select>
            </p>
          </div>
        </div>
      </div>
    </div>

    <section>
      {@html markdownContent}
    </section>
  </div>

  <style>
    body {
      background-color: #0d1117;
      color: #ffffff;
      font-family: Arial, sans-serif;
      padding: 20px;
    }

    section {
      flex: 1;
      margin-top: 10px;
      padding: 20px;
      border: 4px solid transparent;
      border-color: white;
    }

    .nav {
      background-color: #db9030;
      border-radius: 10px;
    }

    .markdown-container {
      max-width: 800px;
      margin: 0 auto;
    }

    a {
      color: #2f81f7;
      text-decoration: none;
      transition: color 0.3s;
    }

    a:hover {
      color: #ff5722;
    }

    h1,
    h2,
    h3,
    h4,
    h5,
    h6 {
      color: #ffffff;
      margin-top: 10px;
      margin-bottom: 5px;
    }

    pre {
      background-color: #333;
      color: #ffffff;
      padding: 10px;
      border-radius: 5px;
      overflow-x: auto;
    }

    img {
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    blockquote {
      border-left: 4px solid #007bff;
      padding-left: 15px;
      margin-left: 10px;
      color: #ccc;
    }

    ul,
    ol {
      margin-left: 20px;
    }

    li {
      margin-bottom: 5px;
    }

    p {
      margin-top: 10px;
      margin-bottom: 10px;
    }

    q {
      color: #007bff;
    }

    code {
      background-color: #333;
      color: #ffffff;
      padding: 2px 5px;
      border-radius: 3px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-bottom: 20px;
    }

    th {
      width: 20%;
      background-color: #161b22;
      color: #fff;
      text-align: left;
      padding: 8px;
      border: 1px solid #30363d;
    }

    td {
      width: 20%;
      padding: 8px;
      border: 1px solid #30363d;
    }

    .table-responsive {
      overflow-x: auto;
    }
  </style>
{:else}
  <p>Caricamento in corso...</p>
{/if}
