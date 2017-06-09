---
title: "Peer Name Resolution-Protokoll (PNRP) | Microsoft Docs"
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
ms.assetid: 11940511-c124-4d91-ae31-d4ed6e81ee58
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Peer Name Resolution-Protokoll (PNRP)
In der gleichberechtigt Umgebung, in bestimmten Namensauflösungssystemen der Peerverwendung, von der jeweils anderen Netzwerkspeicherorten \(Adressen, Protokolle und Ports\) von den Namen oder anderen Typen Bezeichner aufzulösen.  In der Vergangenheit ist Peernamensauflösung durch die grundsätzlich flüchtige Konnektivität sowie andere Stellen innerhalb des \(Domain Name System\) erschwert werden.  
  
 Die gleichberechtigt Netzwerkfunktionsplattform Microsoft® Windows® löst dieses Problem mit dem Peer Name Resolution\-Protokoll \(PNRP\), einer sicheren, skalierbarer und dynamischen Nameregistrierung und einem Namensauflösungsprotokoll, das zuerst für Windows XP entwickelt wird und anschließend in Windows Vista ™ aktualisiert wird.  PNRP\-Arbeiten sehr unterschiedlich zu herkömmlichen Namensauflösungssystemen, aufregende neue Möglichkeiten für Anwendungsentwickler erschließend.  
  
 Mit PNRP können Peernamen auf Computer\- oder einzelne Anwendungen oder Dienste auf dem Computer angewendet werden.  Eine Peernamensauflösung enthält eine Adresse, Port und möglicherweise eine erweiterte Nutzlast.  Vorteile dieser Systemeinschliessungsfehlertoleranz, keine Engpässe und der Namensauflösungen, die niemals veraltete Adressen zurückgeben; das Protokoll eine ausgezeichnete Lösung zum Lokalisieren mobiler Benutzer ausführen.  
  
 Im Hinblick auf Sicherheit können Peernamen veröffentlicht werden, wie gesichert wurde \(geschützt\) oder ungesichert \(nicht geschützt\).  PNRP verwendet Kryptografie mit öffentlichen Schlüsseln, um sichere Peernamen gegen Spoofing zu schützen, Computer können und Dienste mit PNRP benannt werden.  
  
-   Das Peer Name Resolution\-Protokoll werden die folgenden Eigenschaften:  
  
-   Verteilt und nahezu vollständig serverless.  Server sind für das Bootstrapverfahren nur erforderlich.  
  
-   Speichern Sie Nameveröffentlichung ohne die Beteiligung von Drittanbietern.  Anders als DNS\-Nameveröffentlichung ist PNRP\-Nameveröffentlichung und ohne Finanzkosten unmittelbar.  
  
-   PNRP\-Updates in Echtzeit, die die Auflösung von veralteten Adressen verhindert.  
  
-   Die Auflösung von Namen zu PNRP erstreckt sich über Computern hinaus, indem sie auch Namensauflösung Dienste zulässt.  
  
## Der System.Net.PeerToPeer\-Namespace  
  
-   PNRP\-Funktionalität wird durch den <xref:System.Net.PeerToPeer>\-Namespace in .NET Framework 3,5 definiert.  Sie stellt einen Satz von Typen, die verwendet werden können, um Peernamen mit einem verfügbaren PNRP\-Dienst einzutragen und beheben.  
  
-   \(PNRP und benutzerdefinierte Peerresolver können mithilfe von Typen erstellt und instanziiert werden, die im <xref:System.ServiceModel.PeerResolvers>\-Namespace bereitgestellt werden\).  
  
-   Die grundlegenden Typen, die verwendet werden, um Namen mit einem verfügbaren PNRP\-Dienst einzutragen und aufzulösen, sind, wie folgt:  
  
-   <xref:System.Net.PeerToPeer.Cloud>: Definiert die Informationen, die eine verfügbare PNRP\-Cloud, einschließlich des Bereich beschreiben.  
  
-   <xref:System.Net.PeerToPeer.PeerName>: Definiert einen Peernamen, der verwendet werden kann, um einen Peer innerhalb einer Cloud zu registrieren und nach aufzulösen.  
  
-   <xref:System.Net.PeerToPeer.PeerNameRecord>: Definiert den Datensatz in PNRP\-Cloud, die die Registrierungsinformationen für einen Peer enthält, der die Verbindungsendpunkte enthält, an denen mit den Peer Kontakt hergestellt werden kann.  
  
-   <xref:System.Net.PeerToPeer.PeerNameRegistration>: Definiert den Registrierungsvorgang für einen Peernamen, einschließlich Methoden, um Peernameregistrierung starten und beenden.  
  
-   <xref:System.Net.PeerToPeer.PeerNameResolver>: Definiert den Prozess zum Auflösen eines Peernamens den Verbindungsendpunkten, einschließlich der synchronen und asynchronen Methoden zur Lösung.  
  
## Siehe auch  
 <xref:System.ServiceModel.PeerResolvers>   
 <xref:System.Net.PeerToPeer>   
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)   
 [PeerToPeer Technologie\-Beispiel](http://go.microsoft.com/fwlink/?LinkID=179571)