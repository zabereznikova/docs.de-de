---
title: "Gewusst wie: Erstellen eines Sockets | Microsoft Docs"
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
  - "Netzwerk"
  - "Senden von Daten, Sockets"
  - "Datenanforderungen, Sockets"
  - "Anfordern von Daten aus dem Internet, Sockets"
  - "Socket-Klasse, Erstellen von Sockets"
  - "Netzwerkressourcen"
  - "Empfangen von Daten, Sockets"
  - "Protokolle, Sockets"
  - "Internet, Sockets"
  - "Sockets erstellen"
ms.assetid: c64a049c-5981-43bc-a2dc-1851473589c7
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Gewusst wie: Erstellen eines Sockets
Bevor Sie einen Socket verwenden können, um mit Remotegeräten kommunizieren kann, muss der Socket mit Protokoll und Endsystemadresseinformationen initialisiert werden.  Der Konstruktor für die Klasse <xref:System.Net.Sockets.Socket> enthält Parameter, die die Adressenfamilie, den Sockettyp und den Protokolltyp angeben, den der Socket verwendet, um Verbindungen zu machen.  
  
## Beispiel  
 Das folgende Beispiel erstellt einen Socket, der verwendet werden kann, um auf einem TCP\/IP\-based Netzwerk zu kommunizieren, wie Internet.  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
  
```  
  
 Um UDP statt TCP zu verwenden, ändern Sie den Protokolltyp, wie im folgenden Beispiel gezeigt:  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
  
```  
  
 Die <xref:System.Net.Sockets.AddressFamily>\-Enumeration gibt die Standardadressenfamilien an, die von der **Socket**\-Klasse verwendet werden, um Endsystemadressen aufzulösen \(beispielsweise, gibt der **AddressFamily.InterNetwork**\-Member die Adressenfamilie IP\-Version 4\) an.  
  
 Die <xref:System.Net.Sockets.SocketType>\-Enumeration gibt den Typ des Sockets an \(beispielsweise, gibt der **SocketType.Stream**\-Member einen Standardsocket für das Senden und Empfangen von Daten mit Flusssteuerung an\).  
  
 Die <xref:System.Net.Sockets.ProtocolType>\-Enumeration gibt das Netzwerkprotokoll an, um zu verwenden, wenn, in Verbindung steht auf **Socket** \(beispielsweise, **ProtocolType.Tcp** gibt an, dass der Socket TCP verwendet; **ProtocolType.Udp** gibt an, dass der Socket UDP verwendet\).  
  
 Nachdem **Socket** erstellt wurde, kann sie entweder eine Verbindung zu einem Remoteberichtsserver Endpunkt initiieren oder Links von den Remotegeräten empfangen.  
  
## Siehe auch  
 [Verwenden von Clientsockets](../../../docs/framework/network-programming/using-client-sockets.md)   
 [Überwachen mit Sockets](../../../docs/framework/network-programming/listening-with-sockets.md)