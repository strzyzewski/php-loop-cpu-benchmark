# PHP Single Core CPU Benchmark (»Billion Loop Benchmark«)

This is a oneliner script which measures the duration of a for-loop in PHP. 
It is set to **1.000.000.000** iterations by default.

**Always remember:** This script runs only on one CPU core. It has **no effect on the benchmark** how many CPU cores your computer has. 

## Benchmarks

Here's a comparison table for several ennvironments:

| Computer Type | Avg. Duration |
| --- | --- |
| Lenovo Thinkpad T15 Gen2 2021 (Intel i7) | 5,4s |
| Macbook Pro 2020 (Intel i7) | 17,6s |
| Mac Mini 2021 (M1) | 4,8s |
| Mac Mini 2017 (Intel i7) | tbd |
| Macbook Pro 2024 (M4 Pro) | 3,6s |
| All-Inkl Server L6 (intel i3 dedicated) | 2,5s |
| All-Inkl Premium Shared Hosting | 14,5s |
| Ionos Premium Shared Hosting | 24,8s |
| Hetzner Server MA80 (Ryzen 7 dedicated) | 7,2s |
| Hetzner Virtual Server MC60 (EPYC shared vCores) | 21,5s | 
| Hetzner Cloud CCX23 (dedicated AMD) | 12,1s |
| Hetzner Cloud CPX31 (shared AMD) | 14,3s |
| Hetzner Cloud CAX11 (shared Ampere) | 12,0s |
| Hetzner Cloud CX22 (shared Intel, cost optimized) | 25,2s |

## The script

Run this in the shell:

```php
php -r '$loop=1_000_000_000; $t=microtime(true); $s=0; for($i=0;$i<$loop;$i++){ $s+=($i%7); } echo "Benchmark for " . $loop . " Iterations = " . microtime(true)-$t . " secs \n";'
```

At least PHP 7.4 is required. 

**Note:**
Some PHP CLIs don't allow the -r parameter. 
In this case put the script in a file an run it from the shell or open it in the browser.
