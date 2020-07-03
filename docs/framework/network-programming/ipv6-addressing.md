---
title: IPv6-Adressierung
description: Erfahren Sie mehr über IPv6-Adressen (Internetprotokoll, Version 6), einschließlich Textdarstellung und Adresstypen.
ms.date: 03/30/2017
helpviewer_keywords:
- Internet Protocol version 6, addresses in
- Neighbor Discovery
- IPv6, enabling
- IPv6, mobility and
- Internet Protocol version 6, anycast addresses
- IPv6, Neighbor Discovery
- Internet Protocol version 6, auto-configuring
- Internet Protocol version 6, enabling
- IPv6, unicast addresses
- IPv6, auto-configuring
- Internet Protocol version 6, routing
- IPv6, RFC documents
- IPv6, routing
- Internet Protocol version 6, disabling
- Internet Protocol version 6, unicast addresses
- IPv6, multicast addresses
- Internet Protocol version 6, mobility and
- Internet Protocol version 6, RFC documents
- Internet Protocol version 6, Neighbor Discovery
- IPv6, anycast addresses
- Internet Protocol version 6, multicast addresses
- IPv6, addresses in
- IPv6, disabling
ms.assetid: 20a104ae-1649-4649-a005-531a5cf74c93
ms.openlocfilehash: fbf68cb5f40450c2f9ecf4900801ee55e326fcb4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502339"
---
# <a name="ipv6-addressing"></a>IPv6-Adressierung

Im Internetprotokoll Version 6 (IPv6) sind die Adressen 128 Bits lang. Ein Grund für solch einen großen Adressbereich ist das Unterteilen der verfügbaren Adressen in eine Hierarchie von Routingdomänen, die die Topologie des Internets widerspiegeln. Ein weiterer Grund ist das Zuordnen der Adressen des Netzwerkadapters (oder der Netzwerkschnittstellen), die Geräte mit dem Netzwerk verbinden. IPv6 verfügt über die inhärente Funktion, Adressen auf ihrer niedrigsten Ebene aufzulösen, bei der es sich um die Ebene der Netzwerkschnittstelle handelt. Weiterhin verfügt es über Funktionen zur automatischen Konfiguration.

## <a name="text-representation"></a>Textdarstellung

Die folgenden drei konventionellen Formate werden verwendet, um die IPv6-Adressen als Textzeichenfolgen darzustellen:

- **Hexadezimalformat mit Doppelpunkt**. Das bevorzugte Format ist „n:n:n:n:n:n:n:n“. Jedes „n“ stellt den hexadezimalen Wert von einem der acht 16-Bit-Elemente der Adresse dar. Beispiel: `3FFE:FFFF:7654:FEDA:1245:BA98:3210:4562`.

- **Komprimiertes Format**. Aufgrund der Adresslänge ist es üblich, dass die Adressen lange Zeichenfolgen enthalten, die aus Nullen (0) bestehen. Verwenden Sie das komprimierte Format, um das Schreiben dieser Adressen zu vereinfachen. In diesem wird eine einzelne zusammenhängende Folge von 0-Blöcken durch zwei Doppelpunkte (::) dargestellt. Dieses Symbol kann in einer Adresse nur einmal vorkommen. Die Multicastadresse `FFED:0:0:0:0:BA98:3210:4562` ist in komprimierter Form zum Beispiel `FFED::BA98:3210:4562`. Die Unicastadresse `3FFE:FFFF:0:0:8:800:20C4:0` ist in komprimierter Form `3FFE:FFFF::8:800:20C4:0`. Die Loopbackadresse `0:0:0:0:0:0:0:1` ist in komprimierter Form `::`1. Die nicht definierte Adresse `0:0:0:0:0:0:0:0` ist in komprimierter Form `::`.

- **Mixed form (Gemischtes Format)** . Dieses Format kombiniert IPv4- und IPv6-Adressen. In diesem Fall ist das Adressformat „n:n:n:n:n:n:d.d.d.d“, bei dem jedes „n“ den Hexadezimalwert der 6 oberen Elemente der IPv6-16-Bit-Adresse darstellt und jedes „d“ den Dezimalwert der IPv4-Adresse.

## <a name="address-types"></a>Adresstypen

Die führenden Werte in der Adresse definieren den spezifischen IPv6-Adresstyp. Das Feld mit variabler Länge, das diese führenden Bits enthält, wird als Formatpräfix (FP) bezeichnet.

Eine IPv6-Unicastadresse ist in zwei Teile unterteilt. Der erste Teil enthält das Adresspräfix, und der zweite Teil enthält den Schnittstellenbezeichner. Bei Folgendem handelt es sich um eine präzise Methode, um die Kombination aus einer IPv6-Adresse und einem Präfix auszudrücken: IPv6-Adresse/Präfixlänge.

Das folgende Beispiel enthält eine Adresse mit einem 64-Bit-Präfix.

`3FFE:FFFF:0:CD30:0:0:0:0/64`

Das Präfix in diesem Beispiel ist `3FFE:FFFF:0:CD30`. Die Adresse kann auch in einem komprimierten Format (`3FFE:FFFF:0:CD30::/64`) geschrieben werden.

IPv6 definiert die folgenden Adresstypen:

- **Unicast address (Unicastadressen)** . Ein Bezeichner für eine einzelne Schnittstelle. Ein Paket, das an diese Adresse gesendet wird, wird an die angegebene Schnittstelle übermittelt. Die Unicastadressen werden von den Multicastadressen durch den Wert des oberen Oktetts unterschieden. Das obere Oktett der Multicastadressen hat den Hexadezimalwert von FF. Jeder andere Wert für dieses Oktett bezeichnet eine Unicastadresse. Es gibt folgende verschiedene Typen von Unicastadressen:

  - **Link-local addresses (Verbindungslokale Adressen)** . Diese Adressen werden in einem einzigen Link verwendet und weisen folgendes Format auf: FE80::*InterfaceID*. Verbindungslokale Adressen werden zwischen Knoten auf einem Link zur automatischen Adresskonfiguration und Nachbarsuche verwendet oder wenn keine Router vorhanden sind. Eine verbindungslokale Adresse wird in erster Linie beim Start verwendet und wenn das System noch keine größeren Adressen abgerufen hat.

  - **Site-local addresses (Standortlokale Adressen)** . Diese Adressen werden in einem einzigen Standort verwendet und weisen folgendes Format auf: FEC0::*SubnetID*:*InterfaceID*. Die standortlokalen Adressen werden für die Adressierung innerhalb eines Standorts verwendet, wenn kein globales Präfix benötigt wird.

  - **Global IPv6 unicast addresses (Globale IPv6-Unicastadressen)** . Diese Adressen können über das Internet verwendet werden und weisen folgendes Format auf: 010(FP, 3 Bit) TLA ID (13 Bit) Reserved (8 Bit) NLA ID (24 Bit) SLA ID (16 Bit) *InterfaceID* (64 Bit).

- **Multicast address (Multicastadressen)** . Ein Bezeichner für eine Reihe von Schnittstellen, die normalerweise zu den unterschiedlichen Knoten gehören. Ein Paket, das an diese Adresse gesendet wird, wird an alle von der Adresse angegebenen Schnittstellen gesendet. Die Multicastadresstypen ersetzen die IPv4-Broadcastadressen.

- **Anycast address (Anycastadressen)** . Ein Bezeichner für eine Reihe von Schnittstellen, die normalerweise zu den unterschiedlichen Knoten gehören. Ein Paket, das an diese Adresse gesendet wird, wird nur an eine von der Adresse angegebenen Schnittstellen gesendet. Dabei handelt es sich um die Schnittstelle, die von den Routingmetriken als die nächstgelegene angegeben wird. Anycastadressen werden aus dem Unicastadressraum erstellt und sind syntaktisch nicht unterscheidbar. Die adressierte Schnittstelle nimmt die Unterscheidung zwischen Unicast- und Anycastadressen als Funktion ihrer Konfiguration vor.

Im Allgemeinen verfügt der Knoten immer über eine verbindungslokale Adresse. Er kann auch über eine standortlokale Adresse und eine oder mehrere globale Adressen verfügen.

## <a name="see-also"></a>Siehe auch

- [Internetprotokoll Version 6](internet-protocol-version-6.md)
- [Sockets](sockets.md)
