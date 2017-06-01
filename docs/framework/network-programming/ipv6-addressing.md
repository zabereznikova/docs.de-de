---
title: "IPv6-Adressierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Internetprotokoll, Version 6, Adressen in"
  - "Nachbarsuche"
  - "IPv6, aktivieren"
  - "IPv6, Mobilität und"
  - "Internetprotokoll, Version 6, Anycastadressen"
  - "IPv6, Nachbarsuche"
  - "Internetprotokoll, Version 6, automatisches Konfigurieren"
  - "Internetprotokoll, Version 6, aktivieren"
  - "IPv6, Unicastadressen"
  - "IPv6, automatisches Konfigurieren"
  - "Internetprotokoll, Version 6, Routing"
  - "IPv6, RFC-Dokumente"
  - "IPv6, Routing"
  - "Internetprotokoll, Version 6, deaktivieren"
  - "Internetprotokoll, Version 6, Unicastadressen"
  - "IPv6, Multicastadressen"
  - "Internetprotokoll, Version 6, Mobilität und"
  - "Internetprotokoll, Version 6, RFC-Dokumente"
  - "Internetprotokoll, Version 6, Nachbarsuche"
  - "IPv6, Anycastadressen"
  - "Internetprotokoll, Version 6, Multicastadressen"
  - "IPv6, Adressen in"
  - "IPv6, deaktivieren"
ms.assetid: 20a104ae-1649-4649-a005-531a5cf74c93
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# IPv6-Adressierung
Im Internetprotokoll, Version 6 \(IPv6\), Adressen sind 128 Bits lang.  Ein Grund für einen solchen großen Adressbereich ist, die verfügbaren Adressen in eine Hierarchie von Routingdomänen zu unterteilen, die die Topologie Web entsprechen.  Ein anderer Grund besteht darin, die Adressen der Netzwerkadapter \(oder Schnittstellen\) zuzuordnen die Geräte mit dem Netzwerk herstellen.  IPv6 kennzeichnet eine integrierte Funktion, Adressen an der niedrigsten Ebene zu beheben, die auf der Netzwerkschnittstellenebene ist, und die auch Funktionen der automatischen Konfiguration.  
  
## Textdarstellung  
 Im Folgenden sind die drei konventionellen Formulare, die verwendet werden, um die Adressen IPv6 als Textzeichenfolgen darzustellen:  
  
-   **Durch Doppelpunkt getrenntes Format**.  Dies ist das bevorzugte Format n:n:n:n:n:n:n:n.  Jedes n stellt den Hexadezimalwert von einem der acht 16\-Bit\-Elemente der Adresse dar.  Beispiel: `3FFE:FFFF:7654:FEDA:1245:BA98:3210:4562`.  
  
-   **Komprimiertes Format**.  Aufgrund der Adresslänge ist es häufig, die Adressen zu haben, die eine lange Zeichenfolge aus null enthalten.  Um das Schreiben dieser Adressen zu vereinfachen, verwenden Sie das komprimierte Formular, das eine einzelne aufeinander folgende Sequenz von 0 Blöcken durch ein Symbol zwei Doppelpunkten \(::\) dargestellt werden.  Dieses Symbol kann in einer Adresse nur einmal angezeigt werden.  Beispielsweise ist die Multicastadresse `FFED:0:0:0:0:BA98:3210:4562` in komprimiertem Format `FFED::BA98:3210:4562`.  Die Unicastadresse `3FFE:FFFF:0:0:8:800:20C4:0` in komprimiertem Format ist `3FFE:FFFF::8:800:20C4:0`.  Die Loopbackadresse `0:0:0:0:0:0:0:1` in komprimiertem Format ist 1. `::`.  Die nicht angegebene Adresse `0:0:0:0:0:0:0:0` in komprimiertem Format ist `::`.  
  
-   **Gemischtes Format**.  Dieses Format kombiniert Adressen IPv4 und IPv6.  In diesem Fall ist das Adressenformat n:n:n:n:n:n:d.d.d.d, in dem jedes n die Hexadezimalwerte der sechs höherwertigen 16\-Bit\-Elemente der Adresse IPv6 darstellt, und jedes d stellt den Dezimalwert einer IPv4\-Adresse dar.  
  
## Adresstypen  
 Die führenden Bits in der Adresse definieren den bestimmten IPv6\-Adresstyp.  Das Datenfeld variabler Länge, das diese führenden Bits enthält, wird ein Format\-Präfix \(FP\) aufgerufen.  
  
 Eine IPv6\-Unicastadresse ist in zwei Bereiche unterteilt.  Der erste Teil enthält das Adressenpräfix, der zweite Teil enthält den Schnittstellenbezeichner.  Eine kurze Methode, eine IPv6\-Adresse\/eine Präfixkombination auszudrücken ist, wie folgt: ipv6\-address\/PräfixLänge.  
  
 Im folgenden Beispiel einer Adresse mit einem 64\-Bit\-Präfix.  
  
 `3FFE:FFFF:0:CD30:0:0:0:0/64`.  
  
 Das Präfix in diesem Beispiel ist `3FFE:FFFF:0:CD30`.  Die Adresse kann in eine komprimierte Form, als auch `3FFE:FFFF:0:CD30::/64` geschrieben werden.  
  
 IPv6 definiert die folgenden Adresstypen:  
  
-   **Unicastadresse**.  Ein Bezeichner für eine einzelne Schnittstelle.  Ein Paket, das an diese Adresse gesendet wird, wird der identifizierten Schnittstelle übermittelt.  Die Unicastadressen werden von den Multicastadressen durch den Wert des höherwertigen Oktetts unterschieden.  Das höherwertige Oktett der Multicastadressen hat den Hexadezimalwert FF.  Jeder andere Wert für dieses Oktett identifiziert eine Unicastadresse.  Im Folgenden werden verschiedene Typen von Unicastadressen:  
  
    -   **Link\-Local\-Adressen**.  Diese Adressen werden auf einem einzelnen Link verwendet und das folgende Format haben: FE80::*InterfaceID*.  Link\-Local\-Adressen werden zwischen Knoten in einem Link für AUTOAdresse Konfiguration, Nachbarsuche verwendet oder, wenn keine Router vorhanden sind.  Eine Link\-Local\-Adresse wird hauptsächlich beim Starten verwendet und das System noch nicht Adressen des größeren Bereichs abgerufen hat.  
  
    -   **Site\-Local\-Adressen**.  Diese Adressen werden auf einer einzelnen Website verwendet und das folgende Format haben: FEC0::*SubnetID*:*InterfaceID*.  Die Site\-Local\-Adressen werden für das Behandeln innerhalb einer Website ohne die Anforderung ein globales Präfix verwendet.  
  
    -   **Globale IPv6\-Unicastadressen**.  Diese Adressen können über das Internet verwendet werden und das folgende Format haben: FP, \(3 Bits\) ID TLA\-010 \(13 Bits\) reservierte \(8 Bits\) ID NLA\-ID\-\(24 Bits\) SLA \(16 Bits\) *InterfaceID* \(64 Bits\).  
  
-   **Multicastadresse**.  Ein Bezeichner für einen Satz von Schnittstellen \(in der Regel zu verschiedenen Knoten\).  Ein Paket, das an diese Adresse gesendet wird, wird auf alle Schnittstellen zugestellt, die durch die Adresse identifiziert werden.  Die Multicastadressentypen lösen die Broadcastadressen IPv4 ab.  
  
-   **Anycastadresse**.  Ein Bezeichner für einen Satz von Schnittstellen \(in der Regel zu verschiedenen Knoten\).  Ein Paket, das an diese Adresse gesendet wird, wird nur eine Schnittstelle zugestellt, die durch die Adresse identifiziert wird.  Dies ist die nächste Schnittstelle, wie identifiziert, indem Metriken weiterleitet.  Anycastadressen werden vom Unicastadressbereich übernommen und sind nicht unterscheidbar syntaktisch.  Die adressierte Schnittstelle führt die Unterscheidung zwischen den Unicasten und Anycastadressen als Funktion der Konfiguration aus.  
  
 Im Allgemeinen hat ein Knoten immer eine Link\-Local\-Adresse.  Es liegt eine Site\-Local\-Adresse und eine oder mehrere globale Adressen.  
  
## Siehe auch  
 [Internetprotokoll Version 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)