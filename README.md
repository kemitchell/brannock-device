# Brannock Device

scripts to generate tables of [Brannock device](https://en.wikipedia.org/wiki/Brannock_Device) footwear sizing lengths and widths

To generate a table:

```shell
cd brannock-device
# Need Ruby and Bundler.
bundler install
./markdown | less -S
```

The `tsv` script performs the calculations from constants in `constants.yml`.  The other scripts run `tsv`, parse its output, and reformat.

## Motivation

I wrote these scripts as I was reverse engineering the length and width sizing systems of the Brannock device, to help confirm hypotheses against measurements taken from a physical device.  They ended up producing a table that I [contributed to the Wikipedia page on the Brannock Device](https://en.wikipedia.org/w/index.php?title=Brannock_Device&oldid=1147047285) in March of 2023.
