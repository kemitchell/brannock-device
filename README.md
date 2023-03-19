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
