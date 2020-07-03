---
title: Asynchrones Aufrufen von synchronen Methoden
description: Erfahren Sie, wie Sie synchrone Methoden in .NET über die Methoden BeginInvoke und EndInvoke asynchron aufrufen.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- asynchronous programming, delegates
- asynchronous delegates
- AsyncWaitHandle property
- callback methods
- calling synchronous methods in asynchronous manner
- WaitHandle class, code examples
- asynchronous programming, status polling
- polling asynchronous operation status
- delegates [.NET Framework], asynchronous
- synchronous calling in asynchronous manner
- waiting for asynchronous calls
- status information [.NET Framework], asynchronous operations
ms.assetid: 41972034-92ed-450a-9664-ab93fcc6f1fb
ms.openlocfilehash: ff2d30c00e7b6becb0c3ff910d825c2e9d6f78e3
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662640"
---
# <a name="calling-synchronous-methods-asynchronously"></a>Asynchrones Aufrufen von synchronen Methoden

.NET Framework ermöglicht es, jede Methode auch asynchron aufzurufen. Hierzu definieren Sie einen Delegaten mit der gleichen Signatur wie die Methode, die Sie aufrufen möchten. Die Common Language Runtime definiert für diesen Delegaten automatisch eine `BeginInvoke` -Methode und eine `EndInvoke` -Methode mit den entsprechenden Signaturen.

> [!NOTE]
> Asynchrone Delegatenaufrufe, insbesondere der `BeginInvoke` -Methode und der `EndInvoke` -Methode, werden im .NET Compact Framework nicht unterstützt.

Die `BeginInvoke` -Methode initiiert den asynchronen Aufruf. Diese Methode hat die gleichen Parameter wie die Methode, die Sie asynchron ausführen möchten, inklusive zweier zusätzlicher Parameter, die optional sind. Der erste Parameter ist ein <xref:System.AsyncCallback> -Delegat, der auf eine Methode verweist, die bei Beendigung des asynchronen Aufrufs aufzurufen ist. Der zweite Parameter ist ein benutzerdefiniertes Objekt, das Informationen an die Rückrufmethode übergibt. `BeginInvoke` wird immer sofort zurückgegeben und wartet nicht, bis der asynchrone Aufruf abgeschlossen wurde. `BeginInvoke` gibt ein <xref:System.IAsyncResult>zurück, mit dem der Status des asynchronen Aufrufs überwacht werden kann.

Die Ergebnisse dieses asynchronen Aufrufs werden dann mithilfe der `EndInvoke` -Methode abgerufen. Diese kann jederzeit nach der `BeginInvoke`-Methode aufgerufen werden. Wenn der asynchrone Aufruf nicht abgeschlossen wurde, blockiert `EndInvoke` den aufrufenden Thread, bis er abgeschlossen ist. Zu den Parametern von `EndInvoke` gehören die Parameter `out` und `ref` (`<Out>`, `ByRef` und `ByRef` in Visual Basic) der Methode, die Sie asynchron ausführen möchten, und die <xref:System.IAsyncResult>-Schnittstelle, die von `BeginInvoke` zurückgegeben wird.

> [!NOTE]
> Das IntelliSense-Feature in Visual Studio zeigt die Parameter von `BeginInvoke` und `EndInvoke` an. Sofern Sie nicht Visual Studio oder ein vergleichbares Tool verwenden, oder wenn Sie C# zusammen mit Visual Studio nutzen, finden Sie unter [Asynchrones Programmiermodell (APM)](asynchronous-programming-model-apm.md) (Asynchrones Programmiermodell (APM)) eine Beschreibung der für diese Methoden festgelegten Parameter.

Die in diesem Abschnitt verwendeten Codebeispiele veranschaulichen die vier gebräuchlichen Arten der Verwendung von `BeginInvoke` und `EndInvoke` bei asynchronen Aufrufen. Nach dem Aufrufen von `BeginInvoke` können Sie Folgendes tun:

- Sie können etwas Arbeit erledigen und dann `EndInvoke` aufrufen, um eine Blockierung bis zum Abschluss des Aufrufs zu erreichen.

- Rufen Sie ein <xref:System.Threading.WaitHandle> mithilfe der <xref:System.IAsyncResult.AsyncWaitHandle%2A?displayProperty=nameWithType> -Eigenschaft ab. Verwenden Sie deren <xref:System.Threading.WaitHandle.WaitOne%2A> -Methode, um die Ausführung zu blockieren, bis das <xref:System.Threading.WaitHandle> signalisiert wurde, und rufen Sie dann `EndInvoke`auf.

- Sie können das von <xref:System.IAsyncResult> zurückgegebene `BeginInvoke` abrufen, um zu ermitteln, wann der asynchrone Aufruf beendet wurde, und dann `EndInvoke`abrufen.

- Sie können einen Delegaten für eine Rückrufmethode an `BeginInvoke`übergeben. Die Methode wird bei Beendigung des asynchronen Aufrufs für einen <xref:System.Threading.ThreadPool> -Thread ausgeführt. Die Rückrufmethode ruft die `EndInvoke`-Methode auf.

> [!IMPORTANT]
> Unabhängig von der Vorgehensweise wird immer `EndInvoke` aufgerufen, um den asynchronen Aufruf abzuschließen.

## <a name="defining-the-test-method-and-asynchronous-delegate"></a>Definieren der Testmethode und des asynchronen Delegaten
 In den folgenden Codebeispielen werden verschiedene Möglichkeiten veranschaulicht, wie die gleiche zeitintensive Methode, `TestMethod`, asynchron aufgerufen werden kann. Die `TestMethod` -Methode zeigt eine Konsolenmeldung an, um zu zeigen, dass mit der Verarbeitung begonnen wurde, wechselt für einige Sekunden in den Ruhezustand und wird dann beendet. `TestMethod` verfügt über einen `out` -Parameter, um zu zeigen, wie solche Parameter zu den Signaturen von `BeginInvoke` und `EndInvoke`hinzugefügt werden. Sie können `ref` -Parameter auf ähnliche Weise behandeln.

 Im folgenden Codebeispiel werden die Definitionen von `TestMethod` und des Delegaten mit dem Namen `AsyncMethodCaller` veranschaulicht, die beide zum asynchronen Aufrufen von `TestMethod` verwendet werden können. Beim Kompilieren der Codebeispiele müssen Sie die Definitionen für `TestMethod` und für den `AsyncMethodCaller` -Delegaten hinzufügen.

 [!code-cpp[AsyncDelegateExamples#1](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/TestMethod.cpp#1)]
 [!code-csharp[AsyncDelegateExamples#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/TestMethod.cs#1)]
 [!code-vb[AsyncDelegateExamples#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/TestMethod.vb#1)]

## <a name="waiting-for-an-asynchronous-call-with-endinvoke"></a>Warten auf einen asynchronen Aufruf mit "EndInvoke"
 Die einfachste Möglichkeit zum asynchronen Ausführen einer Methode besteht darin, das Ausführen der Methode durch Aufrufen der `BeginInvoke` -Methode des Delegaten zu starten, einige Aufgaben im Hauptthread auszuführen und dann die `EndInvoke` -Methode des Delegaten aufzurufen. `EndInvoke` kann den aufrufenden Thread blockieren, da dies erst zurückgegeben wird, wenn der asynchrone Aufruf abgeschlossen wurde. Dies ist ein gutes Verfahren für Datei- oder Netzwerkvorgänge.

> [!IMPORTANT]
> Da `EndInvoke` blockieren kann, sollte sie nicht aus Threads für die Benutzeroberfläche aufgerufen werden.

 [!code-cpp[AsyncDelegateExamples#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/EndInvoke.cpp#2)]
 [!code-csharp[AsyncDelegateExamples#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/EndInvoke.cs#2)]
 [!code-vb[AsyncDelegateExamples#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/EndInvoke.vb#2)]

## <a name="waiting-for-an-asynchronous-call-with-waithandle"></a>Warten auf einen asynchronen Aufruf mit "WaitHandle"
 Sie können ein <xref:System.Threading.WaitHandle> mithilfe der <xref:System.IAsyncResult.AsyncWaitHandle%2A> -Eigenschaft vom <xref:System.IAsyncResult> abrufen, das von `BeginInvoke`zurückgegeben wird. Das <xref:System.Threading.WaitHandle> wird bei Beendigung des asynchronen Aufrufs signalisiert, und durch Aufrufen der <xref:System.Threading.WaitHandle.WaitOne%2A> -Methode kann darauf gewartet werden.

 Bei Verwendung eines <xref:System.Threading.WaitHandle>kann vor oder nach Abschluss des asynchronen Aufrufs eine weitere Verarbeitung erfolgen. Dies ist jedoch nur vor dem Abrufen der Ergebnisse über den Aufruf von `EndInvoke` möglich.

> [!NOTE]
> Das Wait-Handle wird nicht automatisch geschlossen, wenn Sie `EndInvoke`aufrufen. Wenn Sie alle Verweise auf das Wait-Handle freigeben, werden Systemressourcen frei, sobald das Wait-Handle von der Garbage Collection zurückgefordert wird. Um die Systemressourcen unmittelbar nach der Verwendung des Wait-Handles freizugeben, löschen Sie es, indem Sie die <xref:System.Threading.WaitHandle.Close%2A?displayProperty=nameWithType> -Methode aufrufen. Garbage Collection arbeitet effizienter, wenn verwerfbare Objekte explizit entfernt werden.

 [!code-cpp[AsyncDelegateExamples#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/waithandle.cpp#3)]
 [!code-csharp[AsyncDelegateExamples#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/waithandle.cs#3)]
 [!code-vb[AsyncDelegateExamples#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/WaitHandle.vb#3)]

## <a name="polling-for-asynchronous-call-completion"></a>Abrufen der asynchronen Aufrufbeendigung
 Mit der <xref:System.IAsyncResult.IsCompleted%2A> -Eigenschaft des von <xref:System.IAsyncResult> zurückgegebenen `BeginInvoke` können Sie feststellen, wann der asynchrone Aufruf abgeschlossen wird. Dieses Verfahren ist empfehlenswert, wenn der asynchrone Aufruf aus einem Thread für die Benutzeroberfläche erfolgt. Durch das Abrufen der Beendigung kann die Verarbeitung vom aufrufenden Thread fortgesetzt werden, während der asynchrone Aufruf für einen <xref:System.Threading.ThreadPool> -Thread ausgeführt wird.

 [!code-cpp[AsyncDelegateExamples#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/polling.cpp#4)]
 [!code-csharp[AsyncDelegateExamples#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/polling.cs#4)]
 [!code-vb[AsyncDelegateExamples#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/polling.vb#4)]

## <a name="executing-a-callback-method-when-an-asynchronous-call-completes"></a>Ausführen einer Rückrufmethode bei Beendigung eines asynchronen Aufrufs
 Wenn der Thread, der den asynchronen Aufruf gestartet hat, die Ergebnisse nicht verarbeiten muss, können Sie bei Beendigung des Aufrufs eine Rückrufmethode ausführen. Die Rückrufmethode wird auf einem <xref:System.Threading.ThreadPool> -Thread ausgeführt.

 Um eine Rückrufmethode verwenden zu können, müssen Sie `BeginInvoke` an einen <xref:System.AsyncCallback> -Delegaten übergeben, der die Rückrufmethode darstellt. Sie können auch ein Objekt übergeben, das die von der Rückrufmethode zu verwendenden Informationen enthält. Mit der Rückrufmethode können Sie das <xref:System.IAsyncResult>, das den einzigen Parameter der Rückrufmethode darstellt, in ein <xref:System.Runtime.Remoting.Messaging.AsyncResult> -Objekt umwandeln. Mithilfe der <xref:System.Runtime.Remoting.Messaging.AsyncResult.AsyncDelegate%2A?displayProperty=nameWithType> -Eigenschaft erhalten Sie dann den Delegaten, der zur Initiierung des Aufrufs verwendet wurde, sodass Sie `EndInvoke`aufrufen können.

 Hinweise zum Beispiel:

- Der `threadId`-Parameter von `TestMethod` ist ein `out`-Parameter (`<Out>` `ByRef` in Visual Basic). Deshalb wird sein Eingabewert niemals von `TestMethod` verwendet. Eine Dummyvariable wird an den `BeginInvoke` -Aufruf übergeben. Wenn der `threadId` -Parameter ein `ref` -Parameter wäre (`ByRef` in Visual Basic), müsste die Variable ein Feld auf Klassenebene darstellen, damit sie sowohl an `BeginInvoke` als auch an `EndInvoke`übergeben werden könnte.

- Die an `BeginInvoke` übergebenen Zustandsinformationen bestehen aus einer Formatzeichenfolge, die von der Rückrufmethode zum Formatieren einer Ausgabemeldung verwendet wird. Da sie als <xref:System.Object>-Typ übergeben werden, müssen die Zustandsinformationen vor der Verwendung in den geeigneten Typ umgewandelt werden.

- Der Rückruf erfolgt in einem <xref:System.Threading.ThreadPool> -Thread. <xref:System.Threading.ThreadPool> -Threads sind Hintergrundthreads, die nicht dafür sorgen, dass die Anwendung weiter ausgeführt wird, wenn der Hauptthread beendet wird. Aus diesem Grund muss der Hauptthread des Beispiels im Ruhezustand verbleiben, bis der Rückruf abgeschlossen ist.

 [!code-cpp[AsyncDelegateExamples#5](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/callback.cpp#5)]
 [!code-csharp[AsyncDelegateExamples#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/callback.cs#5)]
 [!code-vb[AsyncDelegateExamples#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/callback.vb#5)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Delegate>
- [Ereignisbasiertes asynchrones Muster (EAP)](event-based-asynchronous-pattern-eap.md)
