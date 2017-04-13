---
title: "Verwenden eines synchronen Serversockets | Microsoft Docs"
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
  - "Synchrone Serversockets"
  - "Senden von Daten, Sockets"
  - "Datenanforderungen, Sockets"
  - "Anfordern von Daten aus dem Internet, Sockets"
  - "Serversockets"
  - "Empfangen von Daten, Sockets"
  - "Socket-Klasse, synchrone Serversockets"
  - "Protokolle, Sockets"
  - "Sockets, synchrone Serversockets"
  - "Internet, Sockets"
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Verwenden eines synchronen Serversockets
Synchrone Serversockets halten die Ausführung der Anwendung an, bis eine Aufforderung zum Aufbau einer Verbindung auf dem Socket empfangen wird.  Synchrone Serversockets sind nicht für Anwendungen geeignet, die umfangreichen Gebrauch von Netzwerk in ihrem Vorgang ausführen, aber sie können für einfache Netzwerkanwendungen geeignet sein.  
  
 Nachdem <xref:System.Net.Sockets.Socket> festgelegt ist, um auf einem Endpunkt mithilfe der <xref:System.Net.Sockets.Socket.Bind%2A> und <xref:System.Net.Sockets.Socket.Listen%2A>\-Methoden überwacht, ist es bereit, eingehende Aufforderungen zum Aufbau einer Verbindung mithilfe der <xref:System.Net.Sockets.Socket.Accept%2A>\-Methode zu akzeptieren.  Die Anwendung wird angehalten, bis eine Aufforderung zum Aufbau einer Verbindung empfangen wird, wenn die **Accept**\-Methode aufgerufen wird.  
  
 Wenn eine Aufforderung zum Aufbau einer Verbindung empfangen wird, gibt **Accept** eine neue **Socket**\-Instanz zurück, die dem verbundene Clients zugeordnet ist.  Im folgenden Beispiel werden Daten vom Client, wird auf der Konsole an und gibt die Daten an den Client zurückgegeben aus.  **Socket** gibt kein Nachrichtenprotokoll, sodass die Zeichenfolge"\<EOF\>Markierungen das Ende der Meldungsdaten an.  Es wird davon ausgegangen, dass **Socket**, das `listener` genannt wird, zu einem Endpunkt initialisiert wurden und gebunden wurde.  
  
```vb  
Console.WriteLine("Waiting for a connection...")  
Dim handler As Socket = listener.Accept()  
Dim data As String = Nothing  
  
While True  
    bytes = New Byte(1024) {}  
    Dim bytesRec As Integer = handler.Receive(bytes)  
    data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
    If data.IndexOf("<EOF>") > - 1 Then  
        Exit While  
    End If  
End While  
  
Console.WriteLine("Text received : {0}", data)  
  
Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
handler.Send(msg)  
handler.Shutdown(SocketShutdown.Both)  
handler.Close()  
  
```  
  
```csharp  
Console.WriteLine("Waiting for a connection...");  
Socket handler = listener.Accept();  
String data = null;  
  
while (true) {  
    bytes = new byte[1024];  
    int bytesRec = handler.Receive(bytes);  
    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
    if (data.IndexOf("<EOF>") > -1) {  
        break;  
    }  
}  
  
Console.WriteLine( "Text received : {0}", data);  
  
byte[] msg = Encoding.ASCII.GetBytes(data);  
handler.Send(msg);  
handler.Shutdown(SocketShutdown.Both);  
handler.Close();  
```  
  
## Siehe auch  
 [Verwenden eines asynchronen Serversockets](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Synchroner Serversocket, Beispiel](../../../docs/framework/network-programming/synchronous-server-socket-example.md)   
 [Überwachen mit Sockets](../../../docs/framework/network-programming/listening-with-sockets.md)