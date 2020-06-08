---
title: Aufrufen von asynchronen Methoden unter Verwendung von IAsyncResult
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
ms.openlocfilehash: 88ca1b5bfbb8bfbdfef01dea8af07c5d56784c5c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289914"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a>Aufrufen von asynchronen Methoden unter Verwendung von IAsyncResult
Typen in .NET Framework- und Klassenbibliotheken von Drittanbietern können Methoden bereitstellen, die einer Anwendung während der Durchführung asynchroner Vorgänge die weitere Ausführung in anderen Threads als dem Hauptanwendungsthread ermöglichen. In den folgenden Abschnitten werden Codebeispiele beschrieben und angegeben, die die verschiedenen Möglichkeiten für den Aufruf asynchroner Methoden mit dem Entwurfsmuster <xref:System.IAsyncResult> veranschaulichen.  
  
- [Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs](blocking-application-execution-by-ending-an-async-operation.md)  
  
- [Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md)  
  
- [Abrufen des Status eines asynchronen Vorgangs](polling-for-the-status-of-an-asynchronous-operation.md)  
  
- [Verwenden eines AsyncCallback-Delegaten zum Beenden eines asynchronen Vorgangs](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))](event-based-asynchronous-pattern-eap.md)
- [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](event-based-asynchronous-pattern-overview.md)
