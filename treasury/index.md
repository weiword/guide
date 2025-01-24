---
label: Treasury
icon: fiscal-host
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

==- <pre id="btc">Bitcoin: [btcUSD] USD </pre> <pre id="bar-1" class="bar"></pre>
Content 1
==- <pre id="eth">Ethereum: [ethUSD] USD </pre> <pre id="bar-2" class="bar"></pre>
Content 2
==- <pre id="sol">Solana: [solUSD] USD </pre> <pre id="bar-3" class="bar"></pre>
Content 3
==-

<script>
    // Function to create the bar string based on percentage and container width
    function createBar(percentage, containerWidth) {
      // Ensure percentage is between 0 and 100
      const clampedPercentage = Math.max(0, Math.min(100, percentage));

      // Calculate the number of blocks that fit in the available width
      const blockWidth = 10; // width of each block in pixels (adjust this value as needed)
      const totalBlocks = Math.floor(containerWidth / blockWidth); // total number of blocks that fit within the width

      // Calculate the number of "▓" (filled) and "░" (empty) blocks
      const filledBlocks = Math.floor((clampedPercentage / 100) * totalBlocks);
      const emptyBlocks = totalBlocks - filledBlocks;

      // Create the bar string using the blocks
      const bar = '▓'.repeat(filledBlocks) + '░'.repeat(emptyBlocks);

      return bar;
    }

    // Function to update the bars with different percentages
    function updateBars(percentages) {
      // Loop through the percentages and update each bar
      percentages.forEach((percentage, index) => {
        const barId = `bar-${index + 1}`; // ID format: bar-1, bar-2, etc.
        const bar = document.getElementById(barId);

        if (bar) {
          // Get the container width for each bar
          const containerWidth = bar.offsetWidth;
          
          // Update the bar's text content with the generated bar
          bar.textContent = createBar(percentage, containerWidth);
        }
      });
    }

    // Example usage: Update bars with different percentages
    updateBars([30, 50, 70, 90]); // Array of different percentages for each bar

    // Optional: Recalculate and update bars when the window is resized
    window.addEventListener('resize', () => {
      updateBars([30, 50, 70, 90]); // You can adjust these percentages as needed
    });
  </script>
