---
title: "Asynchronous Programming Using Delegates | Microsoft Docs"
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
  - "BeginInvoke method"
  - "asynchronous programming, delegates"
  - "asynchronous delegates"
  - "calling synchronous methods in asynchronous manner"
  - "EndInvoke method"
  - "calling asynchronous methods"
  - "delegates [.NET Framework], asynchronous"
  - "synchronous calling in asynchronous manner"
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Asynchronous Programming Using Delegates
Asynchrone Delegaten bieten die Möglichkeit, synchrone Methoden asynchron aufzurufen.  Wenn ein Delegat synchron aufgerufen wird, ruft die `Invoke`\-Methode die Zielmethode direkt im aktuellen Thread auf.  Sobald die `BeginInvoke`\-Methode aufgerufen wurde, fügt die Common Language Runtime \(CLR\) die Anforderung in die Warteschlange ein und kehrt sofort zum Aufrufer zurück.  Die Zielmethode wird für einen Thread asynchron aus dem Threadpool aufgerufen.  Der ursprüngliche Thread, der die Anforderung übergeben hat, kann weiterhin auf parallele Weise für die Zielmethode ausgeführt werden.  Wenn im Aufruf der `BeginInvoke`\-Methode eine Rückrufmethode angegeben wurde, wird diese beim Zurückgeben der Zielmethode aufgerufen.  Die `EndInvoke`\-Methode wird bei der Rückrufmethode dazu verwendet, den Rückgabewert und die Input\/Output\- oder nur Output\-Parameter abzurufen.  Wenn beim Aufrufen von `BeginInvoke` keine Rückrufmethode angegeben ist, kann `EndInvoke` von dem Thread aufgerufen werden, der `BeginInvoke` aufgerufen hat.  
  
> [!IMPORTANT]
>  Compiler sollten Delegatklassen mit den Methoden `Invoke`, `BeginInvoke` und `EndInvoke` ausgeben und dabei die vom Benutzer angegebene Delegatsignatur verwenden.  Die `BeginInvoke`\-Methode und die `EndInvoke`\-Methode sollten als systemeigen ergänzt werden.  Da diese Methoden als systemeigene Methoden gekennzeichnet sind, stellt die Common Language Runtime die Implementierung beim Laden der Klasse automatisch bereit.  Das Lademodul stellt dabei sicher, dass die Methoden nicht überschrieben werden.  
  
## In diesem Abschnitt  
 [Calling Synchronous Methods Asynchronously](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Erläutert die Verwendung von Delegaten zum asynchronen Aufrufen normaler Methoden und bietet einfache Codebeispiele, in denen die vier Methoden zum Warten auf die Rückgabe asynchroner Aufrufe gezeigt wird.  
  
 [Beispiel für die Programmierung von asynchronen Delegaten](../Topic/Asynchronous%20Delegates%20Programming%20Sample.md)  
 Demonstriert die Verwendung von Delegaten für asynchrone Aufrufe anhand eines schwierigeren Codebeispiels, in dem Zahlen in Faktoren zerlegt werden.  
  
## Verwandte Abschnitte  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 Beschreibt die asynchrone Programmierung mit .NET Framework.  
  
## Siehe auch  
 <xref:System.Delegate>