# IPv6 Introduction

## What is IPv6?
IPv6 (Internet Protocol version 6) is the successor to IPv4, designed to solve the problem of IPv4 address exhaustion. It uses a **128-bit** address space, which provides a massive number of unique addresses.

## IPv6 Address Structure
- An IPv6 address is 128 bits long and written in hexadecimal format, separated by colons every 16 bits.
- **Example:** `2001:0db8:85a3:0000:0000:8a2e:0370:7334`

## Address Simplification Rules
1.  **Omit leading zeros:** `0db8` becomes `db8`.
2.  **Compress consecutive zeros:** A single double-colon `::` can replace one or more consecutive groups of all zeros.
    - `2001:db8:85a3:0000:0000:8a2e:0370:7334` can be shortened to `2001:db8:85a3::8a2e:0370:7334`.
    - You can only use `::` once in an address.

## Key IPv6 Address Types
- **Unicast:** A unique address that identifies a single interface.
    - **Global Unicast:** Globally unique, similar to public IPv4. Starts with `2000::/3`.
    - **Link-Local:** Used for communication on a single local network segment. Starts with `fe80::/10`.
- **Multicast:** A single address that identifies a group of interfaces. Starts with `ff00::/8`.
- **Anycast:** A single address assigned to multiple interfaces. A packet sent to an Anycast address is delivered to the nearest interface.
