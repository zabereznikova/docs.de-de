---
title: "PNRP-Clouds | Microsoft Docs"
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
ms.assetid: a82e2bf1-62ab-4c2d-83f3-3217a6aead2e
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# PNRP-Clouds
PNRP "Cloud" stellt einen Satz von Knoten dar, die miteinander über das Netzwerk sein können.  Der Begriff "Cloud" ist mit "Peergitter" und "gleichberechtigt Diagramm" synonym.  
  
 Die Kommunikation zwischen Knoten sollte niemals wolkenübergreifend erfolgen.  Eine <xref:System.Net.PeerToPeer.Cloud>\-Instanz wird durch ihren Namen eindeutig identifiziert, wobei die Groß\- und Kleinschreibung berücksichtigt wird.  Ein einzelner Peer oder Knoten kann mit mehreren Wolken verbunden sein.  
  
 Wolken sind sehr eng an Netzwerkschnittstellen gebunden.  Wenn ein Computer über mehrere IP\-Adressen verfügt und zwei Netzwerkkarten mit unterschiedlichen Teilnetzen verbunden sind, werden drei Wolken zurückgegeben: je eine Wolke pro Link\-Local\-Adresse der jeweiligen Schnittstelle und eine einzelne Wolke mit globalem Bereich.  
  
 Cloud "Bereiche" PNRP\-Verwendung drei, in der ein Bereich eine Gruppierung von Computer ist, die sind, sich zu suchen:  
  
-   Die globale Cloud entspricht dem globalen IPv6\-Adressbereich und zu den globalen Adressen und stellt alle Computer im gesamten Internet IPv6 dar.  Es gibt nur eine einzelne globale Cloud.  
  
-   Die Link\-Local\-Cloud entspricht dem Link\-Local\-IPv6\-Adressbereich und \-Link\-Local\-Adressen.  Eine Link\-Local\-Cloud ist für einen bestimmten Link, der normalerweise dem des lokal angefügte Subnetz ist.  Es kann Link\-Local\-Clouds der mehrere geben.  
  
 Eine dritte Cloud, die sitespezifische Cloud, entspricht dem Site IPv6\-Adressbereich und \-Site\-Local\-Adressen.  Diese Cloud ist veraltet, obwohl sie in PNRP unterstützt wird.  
  
## Clouds  
 PNRP\-Clouds werden durch Instanzen der <xref:System.Net.PeerToPeer.Cloud>\-Klasse dargestellt.  Gruppen von Clouds haben einen Peer sind mit Instanzen der <xref:System.Net.PeerToPeer.CloudCollection> aufzählbaren Klasse.  Auflistungen PNRP\-Clouds, die den aktuellen Peer bekannt sind, können abgerufen werden, indem Sie die statische <xref:System.Net.PeerToPeer.Cloud.GetAvailableClouds%2A>\-Methode aufruft.  
  
 Einzelne Clouds haben die eindeutigen Namen, dargestellt als 256 Zeichen Unicode\-Zeichenfolge.  Diese Namen, zusammen mit dem oben genannten Bereich, werden verwendet, um eindeutige Instanzen der Cloudklasse zu erstellen.  Diese Instanzen können für dauerhafte Verwendung serialisiert und neu erstellt werden.  
  
 Sobald eine Cloudinstanz erstellt, oder abgerufen, können Peernamen mit ihr registriert werden, um ein Netz bekannter Peers zu erstellen.  
  
## Siehe auch  
 <xref:System.Net.PeerToPeer.Cloud>   
 [Peer Name Resolution\-Protokoll \(PNRP\)](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)