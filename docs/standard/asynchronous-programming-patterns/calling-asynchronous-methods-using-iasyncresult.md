---
title: "Calling Asynchronous Methods Using IAsyncResult | Microsoft Docs"
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
  - "ending asynchronous operations"
  - "waiting for asynchronous operations"
  - "asynchronous method calling"
  - "calling asynchronous methods"
  - "asynchronous programming, calling asynchronous methods"
  - "IAsyncResult interface, calling asynchronous methods"
  - "stopping asynchronous operations"
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Calling Asynchronous Methods Using IAsyncResult
Typen in .NET Framework und Klassenbibliotheken Dritter können Methoden bereitstellen, die eine weitere Ausführung der Anwendung bei gleichzeitiger Ausführung von asynchronen Operationen in anderen Threads, also nicht im Haupthread, erlauben.  Die folgenden Abschnitte enthalten und beschreiben Codebeispiele, mit denen die verschiedenen Aufrufmöglichkeiten von asynchronen Methoden veranschaulicht werden, die das <xref:System.IAsyncResult>\-Entwurfsmuster verwenden.  
  
-   [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
-   [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
-   [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
-   [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## Siehe auch  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)