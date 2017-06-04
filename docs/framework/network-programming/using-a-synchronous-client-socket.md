---
title: "Verwenden eines synchronen Clientsockets | Microsoft Docs"
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
  - "Anfordern von Daten aus dem Internet, Sockets"
  - "Synchrone Clientsockets"
  - "Socketklasse, Synchrone Clientsockets"
  - "Empfangen von Daten, Sockets"
  - "Sockets, Synchrone Clientsockets"
  - "Protokolle, Sockets"
  - "Internet, Sockets"
  - "Clientsockets"
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Verwenden eines synchronen Clientsockets
Ein synchroner Clientsocket enthält die Anwendung an, während der Netzwerkvorgang abgeschlossen hat.  Synchrone Sockets sind nicht für Anwendungen geeignet, die umfangreichen Gebrauch von Netzwerk für den Vorgang ausführen, aber sie können einfachen Zugriff auf Netzwerkdiensten für andere Anwendungen ermöglichen.  
  
 Um Daten zu senden, übergeben Sie ein Bytearray in eine der Methoden der <xref:System.Net.Sockets.Socket> die SENDDaten Klasse \(<xref:System.Net.Sockets.Socket.Send%2A> und <xref:System.Net.Sockets.Socket.SendTo%2A>\).  Im folgenden Beispiel wird eine Zeichenfolge in einen Bytearraypuffer mithilfe der <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName>\-Eigenschaft und sendet dann den Puffer dem Netzwerkgerät mithilfe der **Send**\-Methode zu.  Die **Send**\-Methode gibt die Anzahl der Bytes zurück, die dem Netzwerkgerät gesendet werden.  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 Die **Send**\-Methode entfernt die Bytes aus dem Puffer und stellt sie mit der in die Warteschlange zum Netzwerkgerät gesendet werden Netzwerkschnittstelle.  Die Netzwerkschnittstelle kann die Daten nicht direkt, sondern sendet sie schließlich, solange die Verbindung normalerweise der <xref:System.Net.Sockets.Socket.Shutdown%2A>\-Methode geschlossen wird.  
  
 Um Daten aus einem Netzwerkgerät zu empfangen, führen Sie einen Puffer an eine der Methoden der **Socket** die RECEIVEDaten Klasse \(<xref:System.Net.Sockets.Socket.Receive%2A> und <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>\).  Synchrone Sockets halten die Anwendung an, bis Bytes vom Netzwerk empfangen sind, oder bis der Socket geschlossen wird.  Im folgenden Beispiel empfängt Daten vom Netzwerk und dann von den angezeigt wird auf der Konsole.  Im Beispiel wird davon ausgegangen, dass die Daten, die vom Netzwerk stammen, ASCII\-codierter Text sind.  Die **Receive**\-Methode gibt die Anzahl von Bytes zurück, die vom Netzwerk empfangen werden.  
  
```vb  
Dim bytes(1024) As Byte  
Dim bytesRec = s.Receive(bytes)  
Console.WriteLine("Echoed text = {0}", _  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec))  
  
```  
  
```csharp  
byte[] bytes = new byte[1024];  
int bytesRec = s.Receive(bytes);  
Console.WriteLine("Echoed text = {0}",  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec));  
```  
  
 Wenn der Socket nicht mehr benötigt wird, müssen Sie ihn freigeben, indem Sie die <xref:System.Net.Sockets.Socket.Shutdown%2A>\-Methode aufrufen und dann die **Schließen**\-Methode aufrufen.  Im folgenden Beispiel wird **Socket** frei.  Die <xref:System.Net.Sockets.SocketShutdown>\-Enumeration definiert Konstanten, die angeben, ob der Socket zum Senden, zum Empfangen oder für beides geschlossen werden soll.  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## Siehe auch  
 [Verwenden von asynchronen Clientsockets](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [Überwachen mit Sockets](../../../docs/framework/network-programming/listening-with-sockets.md)   
 [Synchrone Clientsockets \- Beispiel](../../../docs/framework/network-programming/synchronous-client-socket-example.md)