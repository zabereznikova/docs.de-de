---
title: "PNRP in der Anwendungsentwicklung | Microsoft Docs"
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
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# PNRP in der Anwendungsentwicklung
In Windows Vista kann das Netzwerk von Anwendungen auf Nameveröffentlichungs\- und \-Auflösungsfunktionen durch eine vereinfachte PNRP\-Anwendungsprogrammierschnittstelle \(APIs\) zugreifen.  
  
## Implementieren des Peer Name Resolution\-Protokoll  
 Mit dem abgeflachten PNRP APIs, werden Clouds nicht explizit angegeben, um den Namen und die Adressen zu registrieren, die PNRP\-Komponente bestimmt automatisch die entsprechenden Clouds, um innerhalb der Clouds zu verknüpfen und die Adressen zu veröffentlichen.  
  
 Für hoch vereinfachte PNRP\-Namensauflösung in Windows Vista, werden PNRP\-Namen jetzt in die getaddrinfo\(\) Windows Socket\-Funktion integriert.  Um PNRP mit einen Namen zu einer IPv6\-Adresse zu beheben, können Anwendungen die getaddrinfo\(\)\-Funktion um den vollqualifizierten Domänennamen \(FQDN\) name.prnp aufzulösen.  Netzwerk, in dem der Name Peername ist, der aufgelöst wird.  Das pnrp.  Nettodomäne ist eine reservierte Domäne in Windows Vista für PNRP\-Namensauflösung.  
  
 Meldungsübergabe zwischen PeerToPeer Anwendungen wird weiterhin über zugrunde liegende Architekturen wie PeerChannel und WCF [Große Daten und Streaming](http://go.microsoft.com/fwlink/?LinkID=179652) behandelt.  
  
## Siehe auch  
 <xref:System.Net.PeerToPeer>