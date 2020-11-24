---
title: TPL und herkömmliche asynchrone .NET-Programmierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, with other asynchronous models
ms.assetid: e7b31170-a156-433f-9f26-b1fc7cd1776f
ms.openlocfilehash: bd6f32f8e77161007f4cfe49fa808167a17a3ec6
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829985"
---
# <a name="tpl-and-traditional-net-asynchronous-programming"></a>TPL und herkömmliche asynchrone .NET-Programmierung

.NET stellt die folgenden zwei Standardmuster zum Ausführen von E/A-gebundenen und computegebundenen asynchronen Vorgängen bereit:  
  
- Das asynchrone Programmiermodell (APM), bei dem asynchrone Vorgänge durch ein Paar von Begin/End-Methoden dargestellt werden. Beispiel: <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> und <xref:System.IO.Stream.EndRead%2A?displayProperty=nameWithType>.  
  
- Das ereignisbasierte asynchrone Muster (EAP), bei dem asynchrone Vorgänge durch ein Methoden-/Ereignispaar mit den Namen `<OperationName>Async` und `<OperationName>Completed` dargestellt werden. Beispiel: <xref:System.Net.WebClient.DownloadStringAsync%2A?displayProperty=nameWithType> und <xref:System.Net.WebClient.DownloadStringCompleted?displayProperty=nameWithType>.
  
Die Task Parallel Library (TPL) kann mit beiden asynchronen Mustern auf unterschiedlichste Weise verwendet werden. Sie können sowohl APM- als auch EAP-Vorgänge als `Task`-Objekte für Bibliotheksbenutzer verfügbar machen, oder Sie machen die APM-Muster verfügbar, implementieren diese aber intern mithilfe von `Task`-Objekten. In beiden Szenarios können Sie den Code mithilfe von `Task`-Objekten vereinfachen und von den folgenden nützlichen Funktionen profitieren:  
  
- Sie können jederzeit nach dem Start der Aufgabe Rückrufe in der Form von Aufgabenfortsetzungen registrieren.  
  
- Sie können mehrere Vorgänge, die als Reaktion auf eine `Begin_`-Methode ausgeführt werden, mit den Methoden <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A> und <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A> oder <xref:System.Threading.Tasks.Task.WaitAll%2A> und <xref:System.Threading.Tasks.Task.WaitAny%2A> koordinieren.  
  
- Sie können asynchrone E/A-gebundene und computegebundene Vorgänge im gleichen `Task`-Objekt kapseln.  
  
- Sie können den Status des `Task`-Objekts überwachen.  
  
- Sie können den Status eines Vorgangs mittels <xref:System.Threading.Tasks.TaskCompletionSource%601> an ein `Task`-Objekt marshallen.  
  
## <a name="wrap-apm-operations-in-a-task"></a>Einschließen von APM-Vorgängen in eine Task  

 Sowohl die <xref:System.Threading.Tasks.TaskFactory?displayProperty=nameWithType>-Klasse als auch die <xref:System.Threading.Tasks.TaskFactory%601?displayProperty=nameWithType>-Klasse stellen mehrere Überladungen der <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A?displayProperty=nameWithType>-Methode und der <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType>-Methode bereit, mit denen Sie ein APM-Begin/End-Methodenpaar in einer <xref:System.Threading.Tasks.Task>- oder <xref:System.Threading.Tasks.Task%601>-Instanz kapseln können. Die verschiedenen Überladungen unterstützen beliebige Begin/End-Methodenpaare mit null (0) bis drei Eingabeparametern.  
  
 Verwenden Sie für Paare mit `End`-Methoden, die einen Wert (`Function` in Visual Basic) zurückgeben, die Methoden in <xref:System.Threading.Tasks.TaskFactory%601>, die eine <xref:System.Threading.Tasks.Task%601>-Klasse erstellen. Verwenden Sie für `End`-Methoden, die „void“ (`Sub` in Visual Basic) zurückgeben, die Methoden in <xref:System.Threading.Tasks.TaskFactory>, die eine <xref:System.Threading.Tasks.Task>-Klasse erstellen.  
  
 In den wenigen Fälle, in denen die `Begin`-Methode über mehr als drei Parameter verfügt oder `ref`-Parameter bzw. `out`-Parameter enthält, werden zusätzliche `FromAsync`-Überladungen bereitgestellt, die nur die `End`-Methode kapseln.  
  
 Im folgenden Beispiel wird die Signatur für die `FromAsync`-Überladung dargestellt, die den Methoden <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> und <xref:System.IO.FileStream.EndRead%2A?displayProperty=nameWithType> entspricht.
  
 [!code-csharp[FromAsync#01](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#01)]
 [!code-vb[FromAsync#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#01)]  
  
Diese Überladung lässt drei Eingabeparameter zu. Der erste Parameter ist ein <xref:System.Func%606>-Delegat, der mit der Signatur der <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType>-Methode übereinstimmt. Der zweite Parameter ist ein <xref:System.Func%602>-Delegat, der <xref:System.IAsyncResult> als Eingabe verwendet und `TResult` zurückgibt. Da <xref:System.IO.FileStream.EndRead%2A> eine ganze Zahl zurückgibt, leitet der Compiler den Typ von `TResult` als <xref:System.Int32> und den Typ der Aufgabe als <xref:System.Threading.Tasks.Task> ab. Die letzten vier Parameter sind mit denen in der <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType>-Methode identisch:  
  
- Der Puffer, in dem die Dateidaten gespeichert werden sollen.  
  
- Der Offset im Puffer, ab dem die Daten geschrieben werden sollen.  
  
- Die maximale Datenmenge, die aus der Datei gelesen werden soll.  
  
- Ein optionales Objekt, in dem benutzerdefinierte Zustandsdaten speichert werden, die an den Rückruf übergeben werden sollen.  
  
### <a name="use-continuewith-for-the-callback-functionality"></a>Verwenden von ContinueWith für die Rückruffunktionalität

 Wenn Sie nicht nur die Anzahl der Byte in der Datei ermitteln möchten, sondern Zugriff auf die Daten in der Datei benötigen, reicht die <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A>-Methode nicht aus. Verwenden Sie stattdessen <xref:System.Threading.Tasks.Task>, deren `Result`-Eigenschaft die Dateidaten enthält. Fügen Sie hierzu eine Fortsetzung zu der ursprünglichen Aufgabe hinzu. Die Fortsetzung führt die Aufgaben aus, die normalerweise vom <xref:System.AsyncCallback>-Delegaten ausgeführt würde. Sie wird aufgerufen, wenn der Vorgänger abgeschlossen und der Datenpuffer gefüllt wurde. (Das <xref:System.IO.FileStream>-Objekt sollte vor der Rückkehr geschlossen werden.)  
  
 Im folgenden Beispiel wird gezeigt, wie Sie eine <xref:System.Threading.Tasks.Task>-Klasse zurückgeben, die das `BeginRead`/`EndRead`-Paar der <xref:System.IO.FileStream>-Klasse kapselt.  
  
 [!code-csharp[FromAsync#03](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#03)]
 [!code-vb[FromAsync#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#03)]  
  
 Die Methode kann anschließend wie folgt aufgerufen werden.  
  
 [!code-csharp[FromAsync#04](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#04)]
 [!code-vb[FromAsync#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#04)]  
  
### <a name="provide-custom-state-data"></a>Bereitstellen von benutzerdefinierten Zustandsdaten

 Wenn in typischen <xref:System.IAsyncResult>-Vorgängen der <xref:System.AsyncCallback>-Delegat bestimmte benutzerdefinierte Zustandsdaten erfordert, müssen Sie diese mit dem letzten Parameter in der `Begin`-Methode übergeben, damit die Daten in das <xref:System.IAsyncResult>-Objekt eingebunden werden können, das schließlich an die Rückrufmethode übergeben wird. Dies ist in der Regel nicht erforderlich, wenn die `FromAsync`-Methoden verwendet werden. Wenn die benutzerdefinierten Daten in der Fortsetzung bekannt sind, können diese direkt im Fortsetzungsdelegaten erfasst werden. Das folgende Beispiel ähnelt dem vorherigen Beispiel, anstatt die `Result`-Eigenschaft des Vorgängers zu analysieren, ermittelt die Fortsetzung jedoch die benutzerdefinierten Zustandsdaten, auf die der Benutzerdelegat der Fortsetzung direkt zugreifen kann.  
  
 [!code-csharp[FromAsync#05](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#05)]
 [!code-vb[FromAsync#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#05)]  
  
### <a name="synchronize-multiple-fromasync-tasks"></a>Synchronisieren mehrerer FromAsync-Tasks

 Die statischen Methoden <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A> und <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A> bieten bei Verwendung mit den `FromAsync`-Methoden eine höhere Flexibilität. Im folgenden Beispiel wird gezeigt, wie Sie mehrere asynchrone E/A-Vorgänge initiieren und anschließend auf den Abschluss all dieser Vorgänge warten, bevor die Fortsetzung ausgeführt wird.  
  
 [!code-csharp[FromAsync#06](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#06)]
 [!code-vb[FromAsync#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#06)]  
  
### <a name="fromasync-tasks-for-only-the-end-method"></a>FromAsync-Tasks nur für die End-Methode

 In den wenigen Fällen, in denen die `Begin`-Methode mehr als drei Eingabeparameter erfordert oder über `ref`- oder `out`-Parameter verfügt, können Sie die `FromAsync`-Überladungen verwenden (z. B. <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%600%7D%29?displayProperty=nameWithType>), die nur die `End`-Methode darstellen. Diese Methoden können zudem in jedem Szenario verwendet werden, in dem eine <xref:System.IAsyncResult>-Schnittstelle übergeben wurde, die in einer Task gekapselt werden soll.  
  
 [!code-csharp[FromAsync#07](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#07)]
 [!code-vb[FromAsync#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#07)]  
  
### <a name="start-and-cancel-fromasync-tasks"></a>Starten und Abbrechen von FromAsync-Tasks

 Die von einer `FromAsync`-Methode zurückgegebene Task weist den Status `WaitingForActivation` auf und wird vom System gestartet, nachdem die Task erstellt wurde. Wenn Sie versuchen, eine solche Aufgabe zu starten, wird eine Ausnahme ausgelöst.  
  
 Sie können eine `FromAsync`-Task nicht abbrechen, da die zugrunde liegenden .NET-APIs keinen Abbruch von laufenden Datei- oder Netzwerk-E/A -Vorgängen unterstützen. Sie können Abbruchfunktionalität zu einer Methode hinzufügen, die einen `FromAsync`-Aufruf kapselt, Sie können jedoch nur vor dem Aufruf oder nach dem Abschluss von `FromAsync` (z. B. in einer Fortsetzungsaufgabe) auf den Abbruch reagieren.  
  
 Einige Klassen mit EAP-Unterstützung, z. B. <xref:System.Net.WebClient>, unterstützen einen Abbruch. Diese systemeigene Abbruchfunktionalität können Sie mithilfe von Abbruchtokens integrieren.  
  
## <a name="expose-complex-eap-operations-as-tasks"></a>Bereitstellen komplexer EAP-Vorgänge als Tasks

 Der TPL stellt keine Methoden bereit, die speziell zum Kapseln ereignisbasierter asynchroner Vorgänge geeignet sind, wie dies bei der `FromAsync`-Methodenfamilie und dem <xref:System.IAsyncResult>-Muster der Fall ist. Die TPL bietet jedoch die <xref:System.Threading.Tasks.TaskCompletionSource%601?displayProperty=nameWithType>-Klasse, mit der ein beliebiger Satz von Vorgängen als <xref:System.Threading.Tasks.Task%601> dargestellt werden kann. Die Vorgänge können sowohl synchron als auch asynchron sein und sind entweder E/A-gebunden und/oder rechnergebunden.  
  
 Im folgenden Beispiel wird gezeigt, wie Sie <xref:System.Threading.Tasks.TaskCompletionSource%601> verwenden, um einen Satz asynchroner <xref:System.Net.WebClient>-Vorgänge für Clientcode als grundlegende <xref:System.Threading.Tasks.Task%601> verfügbar zu machen. Die Methode ermöglichen die Eingabe eines Arrays von Web-URLs und eines zu suchenden Begriffs oder Namens und geben dann an, wie oft der Suchbegriff in jeder Site vorkommt.  
  
 [!code-csharp[FromAsync#10](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/snippet10.cs#10)]
 [!code-vb[FromAsync#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/snippet10.vb#10)]  
  
 Ein umfassenderes Beispiel, in dem auch die Ausnahmebehandlung und das Aufrufen der Methode im Clientcode beschrieben wird, finden Sie unter [Vorgehensweise: Umschließen von EAP-Mustern in einer Aufgabe](how-to-wrap-eap-patterns-in-a-task.md).  
  
 Beachten Sie, dass alle durch <xref:System.Threading.Tasks.TaskCompletionSource%601> erstellten Tasks von dieser `TaskCompletionSource`-Klasse gestartet werden. Der Benutzercode sollte daher nicht die `Start`-Methode für diese Tasks aufrufen.  
  
## <a name="implement-the-apm-pattern-by-using-tasks"></a>Implementieren des APM-Musters mithilfe von Tasks

 In einigen Szenarios ist es möglicherweise wünschenswert, das <xref:System.IAsyncResult>-Muster durch Verwendung von Begin/End-Methodenpaaren in einer API direkt verfügbar zu machen. Dies kann beispielsweise erforderlich sein, wenn Sie die Konsistenz mit vorhandenen APIs aufrecht erhalten möchten oder wenn Sie über automatisierte Tools verfügen, die dieses Muster voraussetzen. In diesen Fällen können Sie mithilfe von `Task`-Objekten die interne Implementierung des APM-Musters vereinfachen.  
  
 Im folgenden Beispiel wird gezeigt, wie Sie mithilfe von Tasks ein APM-Begin/End-Methodenpaar für eine computegebundene Methode mit langer Laufzeit implementieren.  
  
 [!code-csharp[FromAsync#09](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#09)]
 [!code-vb[FromAsync#09](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#09)]  
  
## <a name="use-the-streamextensions-sample-code"></a>Verwenden des StreamExtensions-Beispielcodes

 Die Datei *Streamextensions.cs* im Repository [Parallele Erweiterungsextras für .NET Standard](/samples/dotnet/samples/parallel-programming-extensions-extras-cs/) enthält mehrere Referenzimplementierungen, in denen `Task`-Objekte für asynchrone Datei- und Netzwerk-E/A verwendet werden.
  
## <a name="see-also"></a>Siehe auch

- [Task Parallel Library (TPL)](task-parallel-library-tpl.md)
