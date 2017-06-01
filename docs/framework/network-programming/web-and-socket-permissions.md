---
title: "Web- und Socketberechtigungen | Microsoft Docs"
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
  - "Netzwerk"
  - "Positionen [.NET Framework], Akzeptieren"
  - "Sockets, Berechtigungen"
  - "Netzwerk, Berechtigungen"
  - "Internet, Berechtigungen"
  - "Netzwerkressourcen"
  - "SocketPermission-Klasse, Informationen zur SocketPermission-Klasse"
  - "Positionen [.NET Framework], Verbinden"
  - "WebPermission-Klasse, Informationen zur WebPermission-Klasse"
  - "Berechtigungen [.NET Framework], Sockets"
  - "Sicherheit [.NET Framework], Internet"
  - "Positionen [.NET Framework], Gewähren"
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Web- und Socketberechtigungen
die für Anwendungen mithilfe des <xref:System.Net>\-Namespace wird von den <xref:System.Net.WebPermission> und <xref:System.Net.SocketPermission>\-Klassen bereitgestellt.  Die **WebPermission**\-Klasse steuert das Recht einer Anwendung, Daten von einem URI anzufordern oder ein URI das Internet zu dienen.  Die **SocketPermission**\-Klasse steuert das Recht einer Anwendung, <xref:System.Net.Sockets.Socket> verwenden, um Daten auf einem lokalen Port akzeptiert oder mit Remotegeräten mithilfe eines Ende\-zu\-Ende\-Transportprotokolls an einer anderen Adresse, basierend auf dem Host, die Portnummer und das Ende\-zu\-Ende\-Transportprotokoll des Sockets zu wenden.  
  
 Welche Berechtigungsklasse Sie verwenden, hängt von Ihrem Anwendungstyp.  Anwendungen, die <xref:System.Net.WebRequest> und seine Nachfolger verwenden, sollten die **WebPermission**\-Klasse verwenden, um Berechtigungen zu verwalten.  Anwendungen, die SocketEbene Zugriff verwenden, sollten die **SocketPermission**\-Klasse verwenden, um Berechtigungen zu verwalten.  
  
 **WebPermission** und **SocketPermission** definieren zwei Berechtigungen: akzeptieren und Verbindungsmodus.  Übernehmen Sie erhält die Anwendung das Recht, eine eingehende Verbindung von einer anderen Seite zu beantworten.  Schließen Sie erhält die Anwendung das Recht, eine Verbindung zu einer anderen Seite zu initiieren an.  
  
 Für **SocketPermission**\-Instanzen akzeptieren Sie bedeutet, dass eine Anwendung eingehende Verbindungen auf einer lokalen Transportadresse akzeptieren kann, Schließen Sie bedeutet, dass eine Anwendung mit einer Remotedatenquelle \(oder lokal\) Transportadresse herstellen kann.  
  
 Für **WebPermission**\-Instanzen akzeptieren Sie bedeutet, dass eine Anwendung den URI exportieren kann, das von **WebPermission** zur Welt gesteuert wird, Schließen Sie bedeutet, dass eine Anwendung auf dieser URI zugreifen kann \(ob sie lokal oder remote ist\).  
  
## Siehe auch  
 [Security](../../../docs/standard/security/index.md)   
 [Sicherheit in der Netzwerkprogrammierung](../../../docs/framework/network-programming/security-in-network-programming.md)