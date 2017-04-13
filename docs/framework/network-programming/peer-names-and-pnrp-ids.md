---
title: "Peernamen und PNRP-IDs | Microsoft Docs"
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
ms.assetid: afa538e8-948f-4a98-aa9f-305134004115
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# Peernamen und PNRP-IDs
Ein Peer\-Name stellt einen Endpunkt für Kommunikationsarten dar, die ein Computer, ein Benutzer, eine Gruppe, ein Dienst oder aller sein, der kann mit einem Peer zugeordnet ist, der einer IPv6\-Adresse aufgelöst werden kann.  Das Peer Name Resolution\-Protokoll \(PNRP\) akzeptiert den statistisch eindeutigen Peer\-Namen für die Erstellung einer PNRP\-ID, die verwendet wird, um Cloudmember zu identifizieren.  
  
## Peer\-Namen  
 Peernamen können als ungesichertes registriert werden oder gesichert werden.  Ungesicherte Namen sind nur Textzeichenfolgen, die abhängig von Spoofing sind, da jeder einen doppelten Namen ungesicherten anmelden kann.  Ungesicherte Namen werden am besten in privaten oder andernfalls geschützten Netzwerken verwendet.  Gesicherte Namen werden mit einem Zertifikat und einer digitalen Signatur geschützt.  Nur der ursprüngliche Herausgeber ist in der Lage, den Besitz einer gesicherten Namens zu überprüfen.  
  
 Die Kombination der Cloud und des Bereichs stellt eine relativ sichere Umgebung für Peers bereit, die an PNRP\-Aktivität teilnehmen.  jedoch mit einem sicheren Peernamens stellt nicht die gesamte Sicherheit der Netzwerkfunktionens\-Anwendung sicher.  Die Sicherheit der Anwendung hängt von der Implementierung ab.  
  
 Gesicherte Peernamen kann nur von seinem Besitzer registriert und werden in Kryptografie des öffentlichen Schlüssels geschützt.  Ein gesichertes Peernamen wird als Besitzer durch die Partnerinstanz, die den entsprechenden privaten Schlüssel verfügt.  Besitz kann über die zertifizierte Peeradresse \(CPA\) nachgewiesen werden, die mit dem privaten Schlüssel signiert wird.  Ein böswilliger Benutzer kann den Besitz einer Peernamens nicht ohne den entsprechenden privaten Schlüssel schmieden.  
  
## PNRP\-IDs  
 ![PNRP&#45;ID](../../../docs/framework/network-programming/media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.png "fdc9e8a0\-4a1c\-488d\-a019\-bc3a1973220c")  
  
 PNRP\-IDs werden vom folgenden zusammengesetzt:  
  
-   Die höherwertigen 128 Bits, ist die gleichberechtigt ID \(P2P\), sind ein Hash eines Peernamens, der dem Endpunkt zugewiesen wird.  Der Peername hat das folgende Format: *Authority.Classifier*.  Für gesicherte Namen ist der *Autorität* Hash des SHA\-Algorithmen 1 \(SHA1\) des öffentlichen Schlüssels des Peernamens in den Hexadezimalzeichen.  Für ungesicherte Namen ist die *Autorität* das einzelne Zeichen "0 ".  *Klassifizierung* ist eine Zeichenfolge, die die Anwendung identifiziert.  Kein Peernameklassifizierer kann als 149 Zeichen, einschließlich `null` Abschlusszeichen größer lang sein.  
  
-   Die niederwertigen 128 Bits werden für den Dienst\-Speicherort verwendet, der eine generierte Zahl ist, die verschiedene Instanzen derselben P2P\-ID in derselben Cloud identifiziert.  
  
 Diese Kombination OF P2P\-ID und von Dienst\-Speicherort können mehrere von einem einzelnen Computer registriert werden PNRP\-IDs.  
  
## Siehe auch  
 <xref:System.Net.PeerToPeer.PeerName>   
 <xref:System.Net.PeerToPeer>