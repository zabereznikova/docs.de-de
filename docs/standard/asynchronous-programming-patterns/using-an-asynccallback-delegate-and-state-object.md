---
title: "Using an AsyncCallback Delegate and State Object | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "asynchronous programming, delegates"
  - "AsyncCallback delegate, samples"
  - "asynchronous programming, state objects"
  - "IAsyncResult interface, samples"
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Using an AsyncCallback Delegate and State Object
Wenn Sie mithilfe eines <xref:System.AsyncCallback>\-Delegaten die Ergebnisse des asynchronen Vorgangs in einem eigenen Thread verarbeiten, können Sie mit einem Zustandsobjekt Informationen zwischen den Rückrufen übergeben und ein Endergebnis abrufen.  In diesem Thema wird diese Vorgehensweise durch Erweitern des Beispiels in [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md) veranschaulicht.  
  
## Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie asynchrone Methoden in der <xref:System.Net.Dns>\-Klasse verwendet werden, um DNS\-Daten für Computer abzurufen, die vom Benutzer festgelegt wurden.  In diesem Beispiel wird die `HostRequest`\-Klasse definiert und verwendet, um Zustandsinformationen zu speichern.  Ein `HostRequest`\-Objekt wird für jeden vom Benutzer eingegebenen Computernamen erstellt.  Dieses Objekt wird an die <xref:System.Net.Dns.BeginGetHostByName%2A>\-Methode übergeben.  Die `ProcessDnsInformation`\-Methode wird immer dann aufgerufen, wenn eine Anforderung abgeschlossen wird.  Das `HostRequest`\-Objekt wird mit der <xref:System.IAsyncResult.AsyncState%2A>\-Eigenschaft abgerufen.  Die `ProcessDnsInformation`\-Methode verwendet das `HostRequest`\-Objekt, um den von der Anforderung zurückgegebenen <xref:System.Net.IPHostEntry> oder eine von der Anwendung ausgelöste <xref:System.Net.Sockets.SocketException> zu speichern.  Wenn alle Anforderungen vollständig ausgeführt wurden, durchläuft die Anwendung die `HostRequest`\-Objekte und zeigt entweder die DNS\-Daten oder eine <xref:System.Net.Sockets.SocketException>\-Fehlermeldung an.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## Siehe auch  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)