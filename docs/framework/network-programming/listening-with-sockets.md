---
title: "&#220;berwachen mit Sockets | Microsoft Docs"
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
  - "Sockets, Überwachen mit Sockets"
  - "Datenanforderungen, Sockets"
  - "Anfordern von Daten aus dem Internet, Sockets"
  - "Empfangen von Daten, Sockets"
  - "Protokolle, Sockets"
  - "Überwachen mit Sockets"
  - "Internet, Sockets"
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &#220;berwachen mit Sockets
Listener\- oder Serversockets öffnen einen Port im Netzwerk und warten dann auf einen Client, um an diesen Port herzustellen.  Obwohl andere Endsystemadressefamilien und protokolliert vorhanden sind, zeigt dieses Beispiel, wie Remotedienst für ein TCP\/IP\-Netzwerk erstellt.  
  
 Die eindeutige Adresse eines TCP\/IP\-Diensts wird definiert, indem die IP\-Adresse des Hosts mit der Portnummer des Diensts kombiniert, um einen Endpunkt für den Dienst zu erstellen.  Die <xref:System.Net.Dns>\-Klasse stellt Methoden bereit, die Informationen über die Endsystemadressen durch das Gerät des lokalen Netzwerks unterstützte.  Wenn das Gerät des lokalen Netzwerks mehr als eine Netzwerkadresse hat oder wenn die lokale Systemunterstützung mehr als ein Netzwerkgerät, gibt die **Dns**\-Klasse Informationen über alle Endsystemadressen zurück, und die Anwendung muss die richtige Adresse für den Dienst auswählen.  Die Internet Assigned Numbers Authority \(Iana\) definiert Portnummern für gemeinsame Dienste \(weitere Informationen, finden Sie unter www.iana.org\/assignments\/port\-numbers\).  Andere Dienste können Portnummern im Bereich 1.024 bis 65.535 registriert haben.  
  
 Im folgenden Beispiel wird <xref:System.Net.IPEndPoint> für einen Server, indem sie die erste IP\-Adresse kombiniert, die von **Dns** für den Hostcomputer mit einer Portnummer zurückgegeben wird, die von den registrierten Portnummern ausgewählt ist, werden.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 Nachdem der lokale Endpunkt bestimmt ist, muss <xref:System.Net.Sockets.Socket> mit diesem Endpunkt mithilfe der <xref:System.Net.Sockets.Socket.Bind%2A>\-Methode zugeordnet und festgelegt werden, um auf dem Endpunkt mithilfe der <xref:System.Net.Sockets.Socket.Listen%2A>\-Methode überwacht.  **Bind** löst eine Ausnahme aus, wenn die bestimmte Elementen Address und Anschlusskombination bereits in Gebrauch ist.  Im folgenden Beispiel wird das Zuordnen von **Socket** mit **IPEndPoint**.  
  
```vb  
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 Die **Listen**\-Methode nimmt einen einzelnen Parameter, der angibt, wie viele ausstehenden Verbindungen zu **Socket** zulässig sind, bevor ein Fehler ausgelasteter des Servers zum verbundene Clients zurückgegeben wird.  In diesem Fall werden bis 100 Client in die Verbindungswarteschlange platziert, bevor eine ausgelastete Antwort des Servers an den Client Zahl. 101 zurückgegeben wird.  
  
## Siehe auch  
 [Verwenden eines synchronen Serversockets](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)   
 [Verwenden eines asynchronen Serversockets](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Verwenden von Clientsockets](../../../docs/framework/network-programming/using-client-sockets.md)   
 [Gewusst wie: Erstellen eines Sockets](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)