---
title: Asynchrones Programmiermodell (APM)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- starting asynchronous operations
- beginning asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming
- stopping asynchronous operations
- asynchronous programming, beginning operations
ms.assetid: c9b3501e-6bc6-40f9-8efd-4b6d9e39ccf0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 992cc1f60ee3f08131b478d2336321bf87d7ef89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573788"
---
# <a name="asynchronous-programming-model-apm"></a>Asynchrones Programmiermodell (APM)
Ein asynchroner Vorgang, der das <xref:System.IAsyncResult>-Entwurfsmuster verwendet, wird als zwei Methoden mit den Namen **Begin***OperationName* und **End***OperationName* implementiert, die den asynchronen Vorgang *OperationName* jeweils starten bzw. beenden. Die <xref:System.IO.FileStream> -Klasse stellt z. B. die Methoden <xref:System.IO.FileStream.BeginRead%2A> und <xref:System.IO.FileStream.EndRead%2A> zum asynchronen Lesen von Bytes aus einer Datei bereit. Diese Methoden implementieren die asynchrone Version der <xref:System.IO.FileStream.Read%2A> -Methode.  
  
> [!NOTE]
>  Ab .NET Framework 4 stellt die Task Parallel Library ein neues Modell für die asynchrone und parallele Programmierung bereit. Weitere Informationen finden Sie unter [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md) und [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).  
  
 Nach dem Aufruf von **Begin***OperationName* kann eine Anwendung das Ausführen von Anweisungen für den aufrufenden Thread fortsetzen, während der asynchrone Vorgang in einem anderen Thread ausgeführt wird. Für jeden Aufruf von **Begin***OperationName* sollte die Anwendung auch **End***OperationName* aufrufen, um die Ergebnisse des Vorgangs zu erhalten.  
  
## <a name="beginning-an-asynchronous-operation"></a>Starten eines asynchronen Vorgangs  
 Die Methode **Begin***OperationName* startet den asynchronen Vorgang *OperationName* und gibt ein Objekt zurück, das die <xref:System.IAsyncResult>-Schnittstelle implementiert. <xref:System.IAsyncResult> -Objekte speichern Informationen zu einem asynchronen Vorgang. In der folgenden Tabelle werden Informationen zu einem asynchronen Vorgang angezeigt.  
  
|Member|description|  
|------------|-----------------|  
|<xref:System.IAsyncResult.AsyncState%2A>|Ein optionales, anwendungsspezifisches Objekt, das Informationen über die asynchrone Operation enthält.|  
|<xref:System.IAsyncResult.AsyncWaitHandle%2A>|Ein <xref:System.Threading.WaitHandle> , mit dem die Ausführung der Anwendung blockiert werden kann, bis der asynchrone Vorgang abgeschlossen ist.|  
|<xref:System.IAsyncResult.CompletedSynchronously%2A>|Ein Wert, der angibt, ob der asynchrone Vorgang in dem zum Aufrufen von **Begin***OperationName* verwendeten Thread oder in einem separaten <xref:System.Threading.ThreadPool>-Thread abgeschlossen wurde.|  
|<xref:System.IAsyncResult.IsCompleted%2A>|Ein Wert, der angibt, ob der asynchrone Vorgang abgeschlossen wurde.|  
  
 Eine **Begin***OperationName*-Methode übernimmt jeden in der Signatur der synchronen Version der Methode deklarierten Parameter, der als Wert oder Verweis übergeben wird. Out-Parameter sind nicht Teil der **Begin***OperationName*-Methodensignatur. Die **Begin***OperationName*-Methodensignatur umfasst auch zwei weitere Parameter. Der erste dieser Parameter definiert einen <xref:System.AsyncCallback> -Delegat, der auf eine Methode verweist, die bei Beendigung des asynchronen Aufrufs aufgerufen wird. Der Aufrufer kann `null` angeben (`Nothing` in Visual Basic), wenn nach Abschluss des Vorgangs keine Methode aufgerufen werden soll. Der zweite zusätzliche Parameter ist ein benutzerdefiniertes Objekt. Dieses Objekt kann verwendet werden, um anwendungsspezifische Informationen an die Methode zu übergeben, die aufgerufen wird, wenn der asynchrone Vorgang abgeschlossen ist. Wenn eine **Begin***OperationName*-Methode zusätzliche vorgangsabhängige Parameter übernimmt, z.B. ein Bytearray, um die aus einer Datei gelesenen Bytes zu speichern, sind <xref:System.AsyncCallback> und das Anwendungszustandsobjekt die letzten Parameter in der **Begin***OperationName*-Methodensignatur.  
  
 **Begin***OperationName* gibt die Kontrolle sofort an den aufrufenden Thread zurück. Wenn die **Begin***OperationName*-Methode Ausnahmen auslöst, werden die Ausnahmen ausgelöst, bevor der asynchrone Vorgang gestartet wird. Wenn die **Begin***OperationName*-Methode Ausnahmen auslöst, wird die Rückrufmethode nicht aufgerufen.  
  
## <a name="ending-an-asynchronous-operation"></a>Beenden eines asynchronen Vorgangs  
 Die **End***OperationName*-Methode beendet den asynchronen Vorgang *OperationName*. Der Rückgabewert der **End***OperationName*-Methode besitzt denselben Typ, der von seiner synchronen Entsprechung zurückgegeben wird, und ist spezifisch für den asynchronen Vorgang. Die <xref:System.IO.FileStream.EndRead%2A> -Methode gibt die Anzahl der aus <xref:System.IO.FileStream> gelesen Bytes zurück, während die <xref:System.Net.Dns.EndGetHostByName%2A> -Methode ein <xref:System.Net.IPHostEntry> -Objekt zurückgibt, das Informationen zu einem Hostcomputer enthält. Die **End***OperationName*-Methode übernimmt jeden in der Signatur der synchronen Version der Methode deklarierten out- oder ref-Parameter. Zusätzlich zu den Parametern der synchronen Methode umfasst die **End***OperationName*-Methode auch einen <xref:System.IAsyncResult>-Parameter. Aufrufer müssen die vom entsprechenden Aufruf zurückgegebene Instanz an **Begin***OperationName* übergeben.  
  
 Wenn der durch das <xref:System.IAsyncResult>-Objekt dargestellte asynchrone Vorgang nicht abgeschlossen ist, wenn **End***OperationName* aufgerufen wird, blockiert **End***OperationName* den aufrufenden Thread, bis der asynchrone Vorgang abgeschlossen ist. Vom asynchronen Vorgang ausgelöste Ausnahmen werden von der **End***OperationName*-Methode ausgelöst. Die Auswirkung des mehrmaligen Aufrufs der **End***OperationName*-Methode mit demselben <xref:System.IAsyncResult> ist nicht definiert. Ebenso ist der Aufruf der **End***OperationName*-Methode mit einem <xref:System.IAsyncResult>, das nicht von der zugehörigen Begin-Methode zurückgegeben wurde, ebenfalls nicht definiert.  
  
> [!NOTE]
>  Für beide nicht definierten Szenarien sollten die für die Implementierung zuständigen Personen das Auslösen von <xref:System.InvalidOperationException>erwägen.  
  
> [!NOTE]
>  Implementierer dieses Entwurfsmusters sollten den Aufrufer benachrichtigen, dass der asynchrone Vorgang abgeschlossen ist, indem <xref:System.IAsyncResult.IsCompleted%2A> auf „True“ festgelegt, die asynchrone Rückrufmethode aufgerufen (sofern diese angegeben wurde) und <xref:System.IAsyncResult.AsyncWaitHandle%2A>signalisiert wird.  
  
 Anwendungsentwickler verfügen über mehrere Entwurfsoptionen für den Zugriff auf die Ergebnisse des asynchronen Vorgangs. Die richtige Wahl hängt davon ab, ob die Anwendung über Anweisungen verfügt, die ausgeführt werden können, während der Vorgang abgeschlossen wird. Wenn eine Anwendung keine zusätzlichen Aufgaben erledigen kann, bis sie die Ergebnisse des asynchronen Vorgangs erhält, muss die Anwendung blockiert werden, bis die Ergebnisse verfügbar sind. Sie können einen der folgenden Ansätze zum Blockieren verwenden, bis der asynchrone Vorgang abgeschlossen ist:  
  
-   Rufen Sie **End***OperationName* im Hauptthread der Anwendung auf, wodurch die Ausführung der Anwendung blockiert wird, bis der Vorgang abgeschlossen ist. Ein Beispiel zur Veranschaulichung dieses Verfahrens finden Sie unter [Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
-   Verwenden Sie den <xref:System.IAsyncResult.AsyncWaitHandle%2A> zum Blockieren der Ausführung der Anwendung, bis mindestens ein Vorgang abgeschlossen ist. Ein Beispiel zur Veranschaulichung dieses Verfahrens finden Sie unter [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Anwendungen, die nicht blockiert werden müssen, während der asynchrone Vorgang abgeschlossen wird, können einen der folgenden Ansätze verwenden:  
  
-   Fragen Sie den Abschlussstatus des Vorgangs durch Überprüfen der <xref:System.IAsyncResult.IsCompleted%2A>-Eigenschaft in regelmäßigen Abständen ab, und rufen Sie **End***OperationName* auf, wenn der Vorgang abgeschlossen ist. Ein Beispiel zur Veranschaulichung dieses Verfahrens finden Sie unter [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
-   Verwenden Sie einen <xref:System.AsyncCallback> -Delegat, um eine Methode aufzurufen, wenn der Vorgang abgeschlossen ist. Ein Beispiel zur Veranschaulichung dieses Verfahrens finden Sie unter [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Asynchrones Aufrufen von synchronen Methoden](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 [Verwenden von AsyncCallback-Delegat und Zustandsobjekt](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
