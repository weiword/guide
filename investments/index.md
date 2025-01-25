---
label: Investments
icon: graph
order: 99
---
!!!warning Warning
The information provided is for informational purposes only and does not constitute financial or legal advice.
!!!

<style>
  .bar {
    font-family: monospace;
    font-size: 18px;
    width: 100%;
    box-sizing: border-box;
    white-space: nowrap;  
    overflow: hidden;  
    word-break: break-all;
  }
</style>

==- <div id="btc-container"><pre id="btc">Bitcoin: [btcUSD] USD</pre><pre id="bar-1" class="bar">Loading...</pre></div>
Content 1
==- <div id="eth-container"><pre id="eth">Ethereum: [ethUSD] USD</pre><pre id="bar-2" class="bar">Loading...</pre></div>
Content 2
==- <div id="sol-container"><pre id="sol">Solana: [solUSD] USD</pre><pre id="bar-3" class="bar">Loading...</pre></div>
Content 3
==-

<script>
  // Function to create the bar string based on percentage and container width
  function createBar(percentage, containerWidth) {
    const clampedPercentage = Math.max(0, Math.min(100, percentage));
    const blockWidth = 10; // width of each block in pixels (adjust this value as needed)
    const totalBlocks = Math.floor(containerWidth / blockWidth); // total number of blocks that fit within the width
    const filledBlocks = Math.floor((clampedPercentage / 100) * totalBlocks);
    const emptyBlocks = totalBlocks - filledBlocks;
    const bar = '▓'.repeat(filledBlocks) + '░'.repeat(emptyBlocks);
    return bar;
  }

  // Function to update the bars with different percentages
  function updateBars(percentages) {
    percentages.forEach((percentage, index) => {
      const barId = `bar-${index + 1}`; // ID format: bar-1, bar-2, etc.
      const bar = document.getElementById(barId);
      if (bar) {
        const containerWidth = bar.offsetWidth;
        bar.textContent = createBar(percentage, containerWidth);
      }
    });
  }

  // Update bars with different percentages
  window.addEventListener('load', function() {
    updateBars([30, 50, 70]); // Update with real percentages as needed
  });

  // Recalculate and update bars when the window is resized
  window.addEventListener('resize', function() {
    updateBars([30, 50, 70]); // Recalculate with any desired percentages
  });
</script>
