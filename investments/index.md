---
label: Investments
icon: graph
order: 99
---
!!!warning Warning
The information provided is for educational purposes only and does not constitute financial or legal advice.
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
{.list-icon}
- :icon-number: Rank: S
- :icon-north-star: Current Strategy: DCA Buy
- :icon-hourglass: Target Duration: 15 Years, Jan 2025 - Jan 2040
- :icon-goal: Target Return: 16x-50x
==- <div id="eth-container"><pre id="eth">Ethereum: [ethUSD] USD</pre><pre id="bar-2" class="bar">Loading...</pre></div>
{.list-icon}
- :icon-number: Rank: B
- :icon-north-star: Current Strategy: DCA Buy wstETH + LP
- :icon-hourglass: Target Duration: 15 Years, Jan 2025 - Jan 2040
- :icon-goal: Target Return: 5x-16x
==- <div id="sol-container"><pre id="sol">Solana: [solUSD] USD</pre><pre id="bar-3" class="bar">Loading...</pre></div>
{.list-icon}
- :icon-number: Rank: B
- :icon-north-star: Current Strategy: DCA Buy & Stake
- :icon-hourglass: Target Duration: 15 Years, Jan 2025 - Jan 2040
- :icon-goal: Target Return: 5x-16x
==-

{.compact}
Action   | Assets | USD |  Value | Date
:---   | :--- | :---  | :--- | :---
Item 1 | Blue  | This is `Item 1`. | value | date
Item 2 | Green | This is `Item 2`. | value | date



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
