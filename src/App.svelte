<svelte:head>
  <title>ScratchTester v2</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,400;0,700;1,400;1,700&display=swap" rel="stylesheet">
  <style>
    #app, input, button {
        font-family: "Noto Sans", system-ui, sans-serif;  
      }
    input {
        font-size: 14px;
        font-weight: bold;
        border-style: solid;
        border-radius: 2px;
        border-width: 0.2em;
      }
    a {
      text-decoration: none;
      font-weight: bold;
    }
    button {
      border-radius: 3px;
      border-style: solid;
      cursor: pointer;
      font-size: 14px;
    }
  </style>
</svelte:head>
<script>
	let projectId = '414716080';
  let darkMode = false;
  function toggle() {
    darkMode = !darkMode;
  }
</script>
{#if !darkMode}
<link href="src/light-mode.css" rel="stylesheet">
{:else}
<link href="src/dark-mode.css" rel="stylesheet">
{/if}
<span>Project ID (<strong>NOT</strong> the Project link): </span><input bind:value={projectId} placeholder="Enter a project ID here">
<br/><br/>
<h3>Scratch Player</h3>
<iframe title="Scratch Project" src="{"https://scratch.mit.edu/projects/" + projectId + "/embed"}" allowtransparency="true" width="425" height="360" frameborder="0" scrolling="no" allowfullscreen></iframe>
<br/><br/>
<h3>TurboWarp Player</h3>
<iframe title="TurboWarp" src="{"https://turbowarp.org/" + projectId + "/embed"}" width="425" height="360" allowtransparency="true" frameborder="0" scrolling="no" allowfullscreen></iframe>
<br/><br/>
<h3>Forkphorus Player</h3>
<iframe src="{"https://forkphorus.github.io/embed.html?id=" + projectId + "&auto-start=false&light-content=" + darkMode}" width="425" height="360" allowfullscreen="true" allowtransparency="true" style="border:none;"></iframe>
<h2>Credits</h2>
<div><a href=https://scratch.mit.edu/users/garbomuffin>GarboMuffin</a> for the example project, the TurboWarp player, and the Forkphorus player.</div>
<div><a href=https://fonts.google.com/noto/specimen/Noto+Sans>Noto Sans Font</a> by Google.</div>
<br/>
<button on:click={toggle}><strong>Turn Dark Mode {#if darkMode}Off{:else}On{/if}</strong></button>