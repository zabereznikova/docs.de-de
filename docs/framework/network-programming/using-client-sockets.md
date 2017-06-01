---
title: "Verwenden von Clientsockets | Microsoft Docs"
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
  - "Empfangen von Daten, Sockets"
  - "Socketklasse, Clientsockets"
  - "Protokolle, Sockets"
  - "Internet, Sockets"
  - "Sockets, Clientsockets"
  - "Clientsockets"
ms.assetid: 81de9f59-8177-4d98-b25d-43fc32a98383
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Verwenden von Clientsockets
Bevor Sie eine Konversation durch <xref:System.Net.Sockets.Socket> initiieren können, müssen Sie eine Datenpipe zwischen der Anwendung und dem Remotegerät erstellen.  Obwohl andere Endsystemadressefamilien und protokolliert vorhanden sind, zeigt dieses Beispiel, wie eine TCP\/IP\-Verbindung zu einem Remotedienst erstellt.  
  
 TCP\/IP verwendet eine Netzwerkadresse und eine Dienstportnummer, um einen Dienst eindeutig zu identifizieren.  Die Netzwerkadresse identifiziert ein bestimmtes Gerät im Netzwerk; die Portnummer identifiziert den spezifischen Dienst auf diesem Gerät, um eine Verbindung herzustellen.  Die Kombination der Netzwerkadresse und des Dienstanschlusses wird ein Endpunkt aufgerufen, der in .NET Framework durch die <xref:System.Net.EndPoint>\-Klasse dargestellt wird.  Ein Nachfolger von **EndPoint** wird für jede unterstützte Adressenfamilie definiert; für die IP\-Adressen\-Familie ist die <xref:System.Net.IPEndPoint>\-Klasse.  
  
 Die <xref:System.Net.Dns>\-Klasse stellt Domain\-Name\-Dienste für Anwendungen bereit, die TCP\/IP\-Internetdienste verwenden.  Die <xref:System.Net.Dns.Resolve%2A>\-Methode fragt ein DNS\-Server ab, um einen benutzerfreundlichen Domänennamen \(wie "host.contoso.com"\) zu einer numerischen Internetadresse zuzuordnen \(wie 192.168.1.1\).  **Resolve** gibt [IPHostEnty](frlrfsystemnetiphostentryclasstopic) zurück, das eine Liste von Adressen und der Aliase für den angeforderten Namen enthält.  In den meisten Fällen können Sie die erste Adresse verwenden, die im <xref:System.Net.IPHostEntry.AddressList%2A> Array zurückgegeben wird.  Im folgenden Code wird <xref:System.Net.IPAddress> ab, das die IP\-Adresse für den Server host.contoso.com enthält.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 Die Internet Assigned Numbers Authority \(Iana\) definiert Portnummern für gemeinsame Dienste \(weitere Informationen, finden Sie unter www.iana.org\/assignments\/port\-numbers\).  Andere Dienste können Portnummern im Bereich 1.024 bis 65.535 registriert haben.  Der folgende Code kombiniert die IP\-Adresse für host.contoso.com mit einer Portnummer, um einen Remoteendpunkt für eine Verbindung zu erstellen.  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 Nachdem die Adresse des Remotegeräts festgestellt wurde und einen Port ausgewählt hat, um für die Verbindung zu verwenden, kann die Anwendung versuchen, eine Verbindung mit dem Remotegerät herzustellen.  Im folgenden Beispiel wird vorhandenes **IPEndPoint**, um mit einem Remotegerät herzustellen und fängt alle Ausnahmen ab, die ausgelöst werden.  
  
```vb  
Try  
    s.Connect(ipe)  
Catch ae As ArgumentNullException  
    Console.WriteLine("ArgumentNullException : {0}", _  
        ae.ToString())  
Catch se As SocketException  
    Console.WriteLine("SocketException : {0}", se.ToString())  
Catch e As Exception  
    Console.WriteLine("Unexpected exception : {0}", e.ToString())  
End Try  
  
```  
  
```csharp  
try {  
    s.Connect(ipe);  
} catch(ArgumentNullException ae) {  
    Console.WriteLine("ArgumentNullException : {0}", ae.ToString());  
} catch(SocketException se) {  
    Console.WriteLine("SocketException : {0}", se.ToString());  
} catch(Exception e) {  
    Console.WriteLine("Unexpected exception : {0}", e.ToString());  
}  
```  
  
## Siehe auch  
 [Verwenden eines synchronen Clientsockets](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)   
 [Verwenden von asynchronen Clientsockets](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [Gewusst wie: Erstellen eines Sockets](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)