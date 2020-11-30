---
title: Asynchrones Programmiermodell (APM)
description: Erfahren Sie mehr über das asynchrone Programmiermodell (APM) in .NET. In diesem Artikel wird gezeigt, wie Sie einen asynchronen Vorgang starten und beenden.
ms.date: 03/30/2017
helpviewer_keywords:
- ending asynchronous operations
- starting asynchronous operations
- beginning asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming
- stopping asynchronous operations
- asynchronous programming, beginning operations
ms.assetid: c9b3501e-6bc6-40f9-8efd-4b6d9e39ccf0
ms.openlocfilehash: a6e2ed06e92adffa6c8a61b27bbff994370e8b34
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722738"
---
# <a name="asynchronous-programming-model-apm"></a>Asynchrones Programmiermodell (APM)

Ein asynchroner Vorgang, der das <xref:System.IAsyncResult>-Entwurfsmuster verwendet, wird als zwei Methoden namens `BeginOperationName` und `EndOperationName` implementiert, die den asynchronen Vorgang *OperationName* starten bzw. beenden. Die <xref:System.IO.FileStream> -Klasse stellt z. B. die Methoden <xref:System.IO.FileStream.BeginRead%2A> und <xref:System.IO.FileStream.EndRead%2A> zum asynchronen Lesen von Bytes aus einer Datei bereit. Diese Methoden implementieren die asynchrone Version der <xref:System.IO.FileStream.Read%2A> -Methode.  
  
> [!NOTE]
> Ab .NET Framework 4 stellt die Task Parallel Library ein neues Modell für die asynchrone und parallele Programmierung bereit. Weitere Informationen finden Sie unter [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) und [Aufgabenbasiertes asynchrones Muster (TAP, Task-based Asynchronous Pattern)](task-based-asynchronous-pattern-tap.md).  
  
 Nach dem Aufruf von `BeginOperationName` kann eine Anwendung das Ausführen von Anweisungen für den aufrufenden Thread fortsetzen, während der asynchrone Vorgang in einem anderen Thread ausgeführt wird. Für jeden Aufruf von `BeginOperationName` sollte die Anwendung auch `EndOperationName` aufrufen, um die Ergebnisse des Vorgangs abzurufen.  
  
## <a name="beginning-an-asynchronous-operation"></a>Starten eines asynchronen Vorgangs  

 Die Methode `BeginOperationName` startet den asynchronen Vorgang *OperationName* und gibt ein Objekt zurück, das die <xref:System.IAsyncResult>-Schnittstelle implementiert. <xref:System.IAsyncResult> -Objekte speichern Informationen zu einem asynchronen Vorgang. In der folgenden Tabelle werden Informationen zu einem asynchronen Vorgang angezeigt.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.IAsyncResult.AsyncState%2A>|Ein optionales, anwendungsspezifisches Objekt, das Informationen über die asynchrone Operation enthält.|  
|<xref:System.IAsyncResult.AsyncWaitHandle%2A>|Ein <xref:System.Threading.WaitHandle> , mit dem die Ausführung der Anwendung blockiert werden kann, bis der asynchrone Vorgang abgeschlossen ist.|  
|<xref:System.IAsyncResult.CompletedSynchronously%2A>|Ein Wert, der angibt, ob der asynchrone Vorgang in dem zum Aufrufen von `BeginOperationName` verwendeten Thread anstatt in einem separaten <xref:System.Threading.ThreadPool>-Thread abgeschlossen wurde.|  
|<xref:System.IAsyncResult.IsCompleted%2A>|Ein Wert, der angibt, ob der asynchrone Vorgang abgeschlossen wurde.|  
  
 Eine `BeginOperationName`-Methode übernimmt jeden in der Signatur der synchronen Version der Methode deklarierten Parameter, der als Wert oder Verweis übergeben wird. out-Parameter sind nicht Teil der `BeginOperationName`-Methodensignatur. Die `BeginOperationName`-Methodensignatur umfasst auch zwei weitere Parameter. Der erste dieser Parameter definiert einen <xref:System.AsyncCallback> -Delegat, der auf eine Methode verweist, die bei Beendigung des asynchronen Aufrufs aufgerufen wird. Der Aufrufer kann `null` angeben (`Nothing` in Visual Basic), wenn nach Abschluss des Vorgangs keine Methode aufgerufen werden soll. Der zweite zusätzliche Parameter ist ein benutzerdefiniertes Objekt. Dieses Objekt kann verwendet werden, um anwendungsspezifische Informationen an die Methode zu übergeben, die aufgerufen wird, wenn der asynchrone Vorgang abgeschlossen ist. Wenn eine `BeginOperationName`-Methode zusätzliche vorgangsspezifische Parameter übernimmt, z.B. ein Bytearray zum Speichern der aus einer Datei gelesenen Bytes, sind <xref:System.AsyncCallback> und das Anwendungszustandsobjekt die letzten Parameter in der `BeginOperationName`-Methodensignatur.  
  
 `BeginOperationName` gibt die Kontrolle sofort an den aufrufenden Thread zurück. Wenn die `BeginOperationName`-Methode Ausnahmen auslöst, erfolgt die Auslösung, bevor der asynchrone Vorgang gestartet wird. Wenn die `BeginOperationName`-Methode Ausnahmen auslöst, wird die Rückrufmethode nicht aufgerufen.  
  
## <a name="ending-an-asynchronous-operation"></a>Beenden eines asynchronen Vorgangs  

 Die `EndOperationName`-Methode beendet den asynchronen Vorgang *OperationName*. Der Rückgabewert der `EndOperationName`-Methode weist denselben Typ auf, der von seiner synchronen Entsprechung zurückgegeben wird, und ist spezifisch für den asynchronen Vorgang. Die <xref:System.IO.FileStream.EndRead%2A> -Methode gibt die Anzahl der aus <xref:System.IO.FileStream> gelesen Bytes zurück, während die <xref:System.Net.Dns.EndGetHostByName%2A> -Methode ein <xref:System.Net.IPHostEntry> -Objekt zurückgibt, das Informationen zu einem Hostcomputer enthält. Die `EndOperationName`-Methode übernimmt jeden in der Signatur der synchronen Version der Methode deklarierten out- oder ref-Parameter. Zusätzlich zu den Parametern der synchronen Methode umfasst die `EndOperationName`-Methode auch einen <xref:System.IAsyncResult>-Parameter. Aufrufer müssen die vom entsprechenden Aufruf zurückgegebene Instanz an `BeginOperationName` übergeben.  
  
 Wenn der durch das <xref:System.IAsyncResult>-Objekt dargestellte asynchrone Vorgang nicht abgeschlossen ist, wenn `EndOperationName` aufgerufen wird, blockiert `EndOperationName` den aufrufenden Thread, bis der asynchrone Vorgang abgeschlossen ist. Vom asynchronen Vorgang ausgelöste Ausnahmen werden von der `EndOperationName`-Methode ausgelöst. Die Auswirkung eines mehrmaligen Aufrufs der `EndOperationName`-Methode mit demselben <xref:System.IAsyncResult> ist nicht definiert. Der Aufruf der `EndOperationName`-Methode mit einem <xref:System.IAsyncResult>, das nicht von der zugehörigen Begin-Methode zurückgegeben wurde, ist ebenfalls nicht definiert.  
  
> [!NOTE]
> Für beide nicht definierten Szenarien sollten die für die Implementierung zuständigen Personen das Auslösen von <xref:System.InvalidOperationException>erwägen.  
  
> [!NOTE]
> Implementierer dieses Entwurfsmusters sollten den Aufrufer benachrichtigen, dass der asynchrone Vorgang abgeschlossen ist, indem <xref:System.IAsyncResult.IsCompleted%2A> auf „True“ festgelegt, die asynchrone Rückrufmethode aufgerufen (sofern diese angegeben wurde) und <xref:System.IAsyncResult.AsyncWaitHandle%2A>signalisiert wird.  
  
 Anwendungsentwickler verfügen über mehrere Entwurfsoptionen für den Zugriff auf die Ergebnisse des asynchronen Vorgangs. Die richtige Wahl hängt davon ab, ob die Anwendung über Anweisungen verfügt, die ausgeführt werden können, während der Vorgang abgeschlossen wird. Wenn eine Anwendung keine zusätzlichen Aufgaben erledigen kann, bis sie die Ergebnisse des asynchronen Vorgangs erhält, muss die Anwendung blockiert werden, bis die Ergebnisse verfügbar sind. Sie können einen der folgenden Ansätze zum Blockieren verwenden, bis der asynchrone Vorgang abgeschlossen ist:  
  
- Rufen Sie `EndOperationName` im Hauptthread der Anwendung auf, wodurch die Ausführung der Anwendung blockiert wird, bis der Vorgang abgeschlossen ist. Ein Beispiel zur Veranschaulichung dieses Verfahrens finden Sie unter [Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs](blocking-application-execution-by-ending-an-async-operation.md).  
  
- Verwenden Sie den <xref:System.IAsyncResult.AsyncWaitHandle%2A> zum Blockieren der Ausführung der Anwendung, bis mindestens ein Vorgang abgeschlossen ist. Ein Beispiel zur Veranschaulichung dieses Verfahrens finden Sie unter [Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Anwendungen, die nicht blockiert werden müssen, während der asynchrone Vorgang abgeschlossen wird, können einen der folgenden Ansätze verwenden:  
  
- Fragen Sie den Abschlussstatus des Vorgangs durch Überprüfen der <xref:System.IAsyncResult.IsCompleted%2A>-Eigenschaft in regelmäßigen Abständen ab, und rufen Sie `EndOperationName` auf, wenn der Vorgang abgeschlossen ist. Ein Beispiel zur Veranschaulichung dieses Verfahrens finden Sie unter [Abrufen des Status einer asynchronen Operation](polling-for-the-status-of-an-asynchronous-operation.md).  
  
- Verwenden Sie einen <xref:System.AsyncCallback> -Delegat, um eine Methode aufzurufen, wenn der Vorgang abgeschlossen ist. Ein Beispiel zur Veranschaulichung dieses Verfahrens finden Sie unter [Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="see-also"></a>Siehe auch

- [Ereignisbasiertes asynchrones Muster (EAP)](event-based-asynchronous-pattern-eap.md)
- [Asynchrones Aufrufen von synchronen Methoden](calling-synchronous-methods-asynchronously.md)
- [Verwenden von AsyncCallback-Delegat und Zustandsobjekt](using-an-asynccallback-delegate-and-state-object.md)
