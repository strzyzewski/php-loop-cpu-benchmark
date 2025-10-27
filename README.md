# PHP Single Core CPU Benchmark (»Billion Loop Benchmark«)

This is a oneliner script which measures the duration of a for-loop in PHP. 
It is set to **1.000.000.000** iterations by default.

**Always remember:** This script runs only on one CPU core. It has **no effect on the benchmark** how many CPU cores your computer has. 

## Benchmarks

Here's a comparison table for several ennvironments:

| Computer Type | Avg. duration in seconds |
| --- | --- |
| Lenovo Thinkpad T15 Gen2 2021 (Intel i7) | 5.4 |
| Macbook Pro 2020 (Intel i7) | 17.6 |
| Mac Mini 2021 (M1) | 4.8 |
| Mac Mini 2017 (Intel i7) | 15.7 |
| Macbook Pro 2024 (M4 Pro) | 3.6 |
| All-Inkl Server L6 (Intel i3 dedicated) | 2.5 |
| All-Inkl Server XL6 (Intel Xeon dedicated) | 13.5
| All-Inkl Premium Shared Hosting | 14.5 |
| Ionos Premium Shared Hosting | 24.8 |
| Hetzner Dedicated Server MA80 (Ryzen 7 dedicated) | 7.2 |
| Hetzner Virtual Server MC60 (EPYC shared vCores) | 21.5 | 
| Hetzner Cloud CCX23 (dedicated AMD) | 12.1 |
| Hetzner Cloud CPX31 (shared AMD) | 14.3 |
| Hetzner Cloud CAX11 (shared Ampere) | 12.0 |
| Hetzner Cloud CX22 (shared Intel, cost optimized) | 25.2 |
| Hetzner Cloud CX23 (shared Intel/AMD, cost opmized) | 25.4 | 

## The script

Run this in the shell:

```php
php -r '$loop=1_000_000_000; $t=microtime(true); $s=0; for($i=0;$i<$loop;$i++){ $s+=($i%7); } echo "Benchmark for " . $loop . " Iterations = " . microtime(true)-$t . " secs \n";'
```

At least PHP 7.4 is required. 

**Note:**
Some PHP CLIs don't allow the -r parameter. 
In this case put the script in a file an run it from the shell or open it in the browser.
