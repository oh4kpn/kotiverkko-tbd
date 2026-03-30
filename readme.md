# Verkkokaavio

## Internet / WAN
| Provider | WAN | UXG Max Port |
|----------|-----|--------------|
| DNA | WAN 1 | Port 1 |
| Elisa | WAN 2 | Port 2 |
| Telia | WAN 3 | Port 3 |

---

## UXG Max
| Port | Connection |
|------|------------|
| 1 | WAN 1 (DNA) |
| 2 | WAN 2 (Elisa) |
| 3 | WAN 3 (Telia) |
| 5 | Trunk → Flex 2.5 PoE |

---

## Flex 2.5 PoE → Vintti-8
| Port | Connection | Type |
|------|------------|------|
| 1 | UXG Max LAN Trunk | Trunk |
| 2 | CloudKey | Trunk |
| 3 | AP-Vintti | Trunk |
| 4 | SW-Olo | Trunk |
| 5 | SW-Tyo | Trunk |
| 6 | SW-Vintti-52 | Trunk |
| 7 | AP-Mera-P | Trunk |
| 8 | AP-Mera-E | Trunk |
| 10G | SW-Rack | 10G Trunk |

---

## SW-Vintti-52
| Ports | Device |
|------|--------|
| 1-12 | Reolink |
| 13-24 | Unifi Protect |
| 25-26 | Lennostin |
| 27-28 | Linnustin |
| 29-30 | Axis |
| 52 | Trunk → Vintti-8 |

---

## SW-Rack-16
| Port | Device |
|------|--------|
| 1 | R350 |
| 2 | R350 |
| 3 | R630 |
| 4 | R630 |
| 5 | R730 |
| 6 | R730 |
| 9 | Kaapisto-60 |
| 10 | Kaapisto-120 |
| 11 | Lancache |
| 12 | Trunk → Vintti-8 (10G) |
| 15 | SW-Rack-8 (Trunk) |
| 16 | UPS |

---

## SW-Olo
| Port | Device |
|------|--------|
| 1 | RuuviGW |
| 6 | AP-Olohuone (Trunk) |
| 7 | SW-Olohuone-AV (Trunk) |
| 8 | Trunk → Vintti-8 |

---

## SW-Olohuone-AV
| Port | Device |
|------|--------|
| 1 | SW-Olo-8 (Trunk) |
| 2 | PS3 |
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
| 4 | Levypurkki 60 |
| 5 | Levypurkki 120 |
| 6 | Pelikone |
| 7 | AP-Tyohuone (Trunk) |
| 8 | Trunk → Vintti-8 |

---

## Trunk nopeudet
| Väri | Nopeus |
|------|--------|
| Vihreä | 1 GbE |
| Kirkas vihreä | 2.5 GbE |
| Turkoosi | 10 GbE |

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
