---
title: "Sockets | Microsoft Docs"
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
  - "Anwendungsprotokolle, Sockets"
  - "Senden von Daten, Sockets"
  - "Datenanforderungen, Sockets"
  - "Windows-Sockets"
  - "Sockets, Informationen über Sockets"
  - "Socket-Klasse, Informationen über die Socket-Klasse"
  - "Sockets"
  - "Anfordern von Daten aus dem Internet, Sockets"
  - "Netzwerk, Sockets"
  - "Empfangen von Daten, Sockets"
  - "Protokolle, Sockets"
  - "Internet, Sockets"
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Sockets
Der <xref:System.Net.Sockets>\-Namespace enthält eine verwaltete Implementierung der Windows Socket\-Schnittstelle.  Alle anderen NetzwerkZugriff Klassen im <xref:System.Net>\-Namespace werden auf diese Implementierung von Sockets erstellt.  
  
 Die .NET Framework\-<xref:System.Net.Sockets.Socket>\-Klasse ist eine Version mit verwaltetem Code der Socketdienstleistungen, die vom Winsock32 API bereitgestellt werden.  In den meisten Fällen marshallen die **Socket**\-Klassenmethoden einfach Daten in ihre systemeigenen Win32\-Äquivalente behandeln und alle notwendigen Sicherheitsüberprüfungen.  
  
 Die **Socket**\-Klasse unterstützt zwei Grundmodi, synchron und asynchron.  Im synchronen Modus warten Aufrufe der Funktionen, die ausführen, Netzwerkoperationen \(z <xref:System.Net.Sockets.Socket.Send%2A> und <xref:System.Net.Sockets.Socket.Receive%2A>\), bis der Vorgang abgeschlossen ist, bevor er Steuerelement an das aufrufende Programm zurückgibt.  Im asynchronen Modus kehren diese Aufrufe sofort zurück.  
  
## Siehe auch  
 [Gewusst wie: Erstellen eines Sockets](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)   
 [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)