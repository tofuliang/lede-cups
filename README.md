# Latest Apple CUPS Openwrt make file

## Intro
- Fork from [TheMMcOfficial/lede-cups](https://github.com/TheMMcOfficial/lede-cups)
- Source from [CUPS](https://github.com/apple/cups)
- Latest CUPS version 2.3.3

## How to compile with complete openwrt firmware

This code will compile a complete openwrt firmware that include CUPS
```
git clone (your openwrt source)

cd source

echo "src-git cups https://github.com/SoPudge/lede-cups" >> feeds.conf.default

./scripts/feeds update -a

./scripts/feeds install -a

make menuconfig (set Network->Printing->cups as "M",include other cups related packages)

make V=s -j1
```

## How to compile only CUPS packages

This code will compile only CUPS packages, not complete openwrt firmware.
```
git clone (your openwrt source)

cd source

echo "src-git cups https://github.com/SoPudge/lede-cups" >> feeds.conf.default

./scripts/feeds update -a

./scripts/feeds install -a

make menuconfig (set Network->Printing->cups as "M",include other cups related packages)

make -j8 download V=s

make tools/install V=s -j1

make toolchain/install V=s -j1

make package/feeds/cups/cups/compile V=s -j1
```

## Version of CUPS
2.3.3
