# Verkkokaavio

## Internet / WAN
| Provider | WAN | UXG Max Port |
|----------|-----|--------------|
| DNA | WAN 1 | Port 1 |
| Elisa | WAN 2 | Port 2 |
| Telia | WAN 3 | Port 3 |
| Starlink | WAN 4 | Port 4 |

---

## UXG Max
| Port | Connection |
|------|------------|
| 1 | WAN 1 (DNA) 2.5GbE  |
| 2 | WAN 2 (Elisa) 2.5GbE |
| 3 | WAN 3 (Telia) 2.5GbE  |
[ 4 | WAN 4 (Starlink TBD |
| 5 | Trunk → Vintti-8 2.5GbE  |

---

## Vintti-8
| Port | Connection | Type |
|------|------------|------|
| 1 | UXG Max LAN Trunk | Trunk 2.5GbE |
| 2 | CloudKey | Trunk GbE |
| 3 | AP-Vintti | Trunk GbE |
| 4 | SW-Olo | Trunk GbE |
| 5 | SW-Tyo | Trunk GbE |
| 6 | SW-Vintti-52 | Trunk 2.5GbE |
| 7 | AP-Mera-P | Trunk GbE  |
| 8 | AP-Mera-E | Trunk GbE  |
| 10G | SW-Rack | Trunk 10GbE |

---

## SW-Vintti-52
| Ports | Device |
|------|--------|
| 1-12 | Reolink |
| 13-24 | Unifi Protect |
| 25-26 | Lennostin |
| 27-28 | Linnustin |
| 29-30 | Axis |
| 52 | Trunk → Vintti-8 2.5GbE |

---

## SW-Rack-16
| Port | Device |
|------|--------|
| 1 | R350 10GbE |
| 2 | R350 10GbE |
| 3 | R630 10GbE |
| 4 | R630 10GbE |
| 5 | R730 10GbE |
| 6 | R730 10GbE |
| 9 | Kaapisto-60 10GbE |
| 10 | Kaapisto-120 10GbE |
| 11 | Lancache 10GbE |
| 12 | Trunk → Vintti-8 (10G) |
| 15 | SW-Rack-8 (Trunk) GbE |
| 16 | UPS GbE |

---

## SW-Olo
| Port | Device |
|------|--------|
| 1 | RuuviGW |
| 6 | AP-Olohuone (Trunk) GbE|
| 7 | SW-Olohuone-AV (Trunk) GbE |
| 8 | Trunk → Vintti-8 GbE |

---

## SW-Olohuone-AV
| Port | Device |
|------|--------|
| 1 | SW-Olo-8 (Trunk) GbE|
| 2 | PS3 GbE|
| 3 | Samsung |
| 4 | Strong Streamer |
| 5 | Onkyo |

---

## SW-Tyo
| Port | Device |
|------|--------|
| 1 | UPS |
| 2 | Hamy-Work |
| 3 | Gisu-Work |
| 4 | Levypurkki 60 GbE |
| 5 | Levypurkki 120 GbE |
| 6 | Pelikone |
| 7 | AP-Tyohuone (Trunk) GbE |
| 8 | Trunk → Vintti-8 GbE |

---

## Topologia

```
Internet
   │
   └── UXG Max
        │
        └── Flex 2.5 PoE (Vintti-8)
             ├── SW-Vintti-52
             ├── SW-Rack-16 (10G)
             ├── SW-Olo
             │    └── SW-Olohuone-AV
             ├── SW-Tyo
             ├── AP-Vintti
             ├── AP-Mera-P
             ├── AP-Mera-E
             └── CloudKey
