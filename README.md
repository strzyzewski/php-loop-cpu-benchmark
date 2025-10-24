# PHP Single Core CPU Benchmark

This is a oneliner script which measures the duration of a for-loop in PHP. 
It is set to **1.000.000.000** iterations by default.

**Always remember:** This script runs only on one CPU core. It has **no effect on the benchmark** how many CPU cores your computer has. 

## Benchmarks

Here's a comparison table for several ennvironments:

| Computer Type | Avg. Duration |
| --- | --- |
| All-Inkl L6 (intel i3 dedicated) | 2,5s |
| Lenovo Thinkpad T15 Gen2 with Intel i7 | 5,4s |
| Hetzner Server MA80 (Ryzen 7 dedicated) | 7,2s |
| Hetzner Virtual Server MC60 (EPYC shared vCores) | 21,5s | 
| Hetzner Cloud CCX23 (dedicated AMD) | 12,1s |
| Hetzner Cloud CPX31 (shared AMD) | 14,3s |
| Hetzner Cloud CAX11 (shared Ampere) | 12,0s | 
| Hetzner Cloud CX22 (shared Intel, cost optmized) | 25,2s |

## The script

```php
php -r '$loop=1_000_000_000; $t=microtime(true); $s=0; for($i=0;$i<$loop;$i++){ $s+=($i%7); } echo "Benchmark for " . $loop . " Iterations = " . microtime(true)-$t . " secs \n";'
```
