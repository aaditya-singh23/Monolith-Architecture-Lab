# Lab 2: Monolithic Architecture
**Student Name:** Aaditya Singh  
**SRN:** PES1UG23AM002

## Explanations of Optimizations
### 1. Checkout Route (/checkout)
- **Bottleneck:** A manual `while` loop was used to increment the total fee, causing high CPU usage.
- **Optimization:** Replaced with a direct `for` loop to sum the fees.
- **Result:** Response time decreased significantly under load.

### 2. Events Route (/events)
- **Bottleneck:** A 3-million iteration "waste" loop was artificially slowing down the page.
- **Optimization:** Removed the waste loop from `main.py`.
- **Result:** Average response time dropped from ~200ms to <50ms.

### 3. My Events Route (/my-events)
- **Bottleneck:** A 1.5-million iteration "dummy" loop was present in the logic.
- **Optimization:** Removed the dummy loop.
- **Result:** Performance improved, leading to a faster and more stable UI.
