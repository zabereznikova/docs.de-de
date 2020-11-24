---
title: Aufrufen von asynchronen Methoden unter Verwendung von IAsyncResult
ms.date: 03/30/2017
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
ms.openlocfilehash: 20aafd45c323a609b3cc7fb5a1a6378d43548fcb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830453"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a>Aufrufen von asynchronen Methoden unter Verwendung von IAsyncResult

Typen in .NET-Bibliotheken und Klassenbibliotheken von Drittanbietern können Methoden bereitstellen, mit denen eine Anwendung weiterhin ausgeführt werden kann, während diese asynchrone Vorgänge in anderen Threads als dem Hauptanwendungsthread ausführt. In den folgenden Abschnitten werden Codebeispiele beschrieben und angegeben, die die verschiedenen Möglichkeiten für den Aufruf asynchroner Methoden mit dem Entwurfsmuster <xref:System.IAsyncResult> veranschaulichen.  
  
- [Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs](blocking-application-execution-by-ending-an-async-operation.md)  
  
- [Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md)  
  
- [Abrufen des Status eines asynchronen Vorgangs](polling-for-the-status-of-an-asynchronous-operation.md)  
  
- [Verwenden eines AsyncCallback-Delegaten zum Beenden eines asynchronen Vorgangs](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))](event-based-asynchronous-pattern-eap.md)
- [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](event-based-asynchronous-pattern-overview.md)
