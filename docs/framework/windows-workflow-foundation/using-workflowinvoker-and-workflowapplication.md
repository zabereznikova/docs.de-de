---
title: Verwenden von WorkflowInvoker und WorkflowApplication
description: Dieser Artikel beschreibt das Workflow Hosting mithilfe von WorkflowInvoker und WorkflowApplication in Windows Workflow Foundation.
ms.date: 03/30/2017
ms.assetid: cd0e583c-a3f9-4fa2-b247-c7b3368c48a7
ms.openlocfilehash: 1cc84afe002615c317309054179abd1af5800e9c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254609"
---
# <a name="using-workflowinvoker-and-workflowapplication"></a>Verwenden von WorkflowInvoker und WorkflowApplication

Windows Workflow Foundation (WF) bietet mehrere Methoden zum Hosting von Workflows. <xref:System.Activities.WorkflowInvoker> stellt eine einfache Möglichkeit zum Aufrufen eines Workflows bereit, so als handelte es sich um einen Methodenaufruf, und kann nur für Workflows verwendet werden, die keine Persistenz verwenden. <xref:System.Activities.WorkflowApplication> bietet ein umfangreicheres Modell zum Ausführen von Workflows, die Benachrichtigungen über Lebenszyklusereignisse, Ausführungssteuerung, Wiederaufnahme von Lesezeichen und Persistenz enthalten. <xref:System.ServiceModel.Activities.WorkflowServiceHost> umfasst die Unterstützung von Messagingaktivitäten und wird hauptsächlich in Verbindung mit Workflowdiensten verwendet. In diesem Thema wird das Workflowhosting mit <xref:System.Activities.WorkflowInvoker> und <xref:System.Activities.WorkflowApplication> erläutert. Weitere Informationen zum Hosting von Workflows mit <xref:System.ServiceModel.Activities.WorkflowServiceHost> finden Sie unter Übersicht über [Workflow Dienste](../wcf/feature-details/workflow-services.md) und [Hosting-Workflow Dienste](../wcf/feature-details/hosting-workflow-services-overview.md).  
  
## <a name="using-workflowinvoker"></a>Verwenden von WorkflowInvoker  

 <xref:System.Activities.WorkflowInvoker> bietet ein Modell zum Ausführen eines Workflows, als ob es sich dabei um einen Methodenaufruf handeln würde. Um einen Workflow mit <xref:System.Activities.WorkflowInvoker> aufzurufen, rufen Sie die <xref:System.Activities.WorkflowInvoker.Invoke%2A>-Methode auf, und übergeben Sie die Workflowdefinition des Workflows, der aufgerufen werden soll. In diesem Beispiel wird eine <xref:System.Activities.Statements.WriteLine>-Aktivität mit dem <xref:System.Activities.WorkflowInvoker>-Objekt aufgerufen.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#1)]  
  
 Beim Aufruf eines Workflow mit dem <xref:System.Activities.WorkflowInvoker>-Objekt wird der Workflow für den aufrufenden Thread ausgeführt, und die <xref:System.Activities.WorkflowInvoker.Invoke%2A>-Methode wird blockiert, bis der Workflow abgeschlossen ist, einschließlich der eventuell anfallenden Leerlaufzeit. Um ein anderes Timeoutintervall für den Abschluss des Workflows zu konfigurieren, verwenden Sie eine der <xref:System.Activities.WorkflowInvoker.Invoke%2A>-Überladungen, die einen <xref:System.TimeSpan>-Parameter annehmen. In diesem Beispiel wird ein Workflow mit zwei verschiedenen Timeoutintervallen zweimal aufgerufen. Der erste Workflow wird abgeschlossen, der zweite jedoch nicht.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#50](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#50)]  
  
> [!NOTE]
> Das <xref:System.TimeoutException>-Objekt wird nur ausgelöst, wenn das Timeoutintervall verstreicht und der Workflow während der Ausführung in den Leerlauf wechselt. Ein Workflow, der erst nach dem angegebenen Timeoutintervall abgeschlossen wird, wird dennoch erfolgreich beendet, wenn der Workflow nicht in den Leerlauf wechselt.  
  
 <xref:System.Activities.WorkflowInvoker> stellt auch asynchrone Versionen der Aufrufmethode bereit. Weitere Informationen finden Sie unter <xref:System.Activities.WorkflowInvoker.InvokeAsync%2A> und <xref:System.Activities.WorkflowInvoker.BeginInvoke%2A>.  
  
### <a name="setting-input-arguments-of-a-workflow"></a>Festlegen der Eingabeargumente eines Workflows  

 Daten können mit einem Wörterbuch von Eingabeparametern, die nach Argumentname sortiert sind und so den Eingabeargumenten des Workflows zugeordnet werden können, in einen Workflow übergeben werden. In diesem Beispiel wird ein <xref:System.Activities.Statements.WriteLine>-Objekt aufgerufen, und der Wert für das zugehörige <xref:System.Activities.Statements.WriteLine.Text%2A>-Argument wird mit dem Wörterbuch von Eingabeparametern angegeben.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#3)]  
  
### <a name="retrieving-output-arguments-of-a-workflow"></a>Abrufen der Ausgabeargumente eines Workflows  

 Die Ausgabeparameter eines Workflows können mit dem Ausgabewörterbuch abgerufen werden. Es wird über den Aufruf von <xref:System.Activities.WorkflowInvoker.Invoke%2A> zurückgegeben. Im folgenden Beispiel wird ein Workflow aufgerufen, der aus einer einzelnen `Divide`-Aktivität besteht, die über zwei Eingabeargumente und zwei Ausgabeargumente verfügt. Beim Aufrufen des Workflows wird das `arguments`-Wörterbuch übergeben, das die Werte für die einzelnen Eingabeargumente sortiert nach Argumentname enthält. Wenn der Aufruf von `Invoke` zurückgegeben wird, werden die einzelnen Ausgabeargumente nach Argumentname sortiert im `outputs`-Wörterbuch zurückgegeben.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#120](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#120)]  
  
 [!code-csharp[CFX_WorkflowInvokerExample#20](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#20)]  
  
 Wenn der Workflow von <xref:System.Activities.ActivityWithResult> abgeleitet wird, wie z. B. `CodeActivity<TResult>` oder `Activity<TResult>`, und Ausgabeargumente zusätzlich zum gut definierten <xref:System.Activities.Activity%601.Result%2A>-Ausgabeargument vorhanden sind, muss eine nicht generische Überladung von `Invoke` verwendet werden, um die zusätzlichen Argumente abzurufen. Hierzu muss die an `Invoke` übergebene Workflowdefinition den Typ <xref:System.Activities.Activity> aufweisen. In diesem Beispiel wird die `Divide`-Aktivität von `CodeActivity<int>` abgeleitet. Sie wird jedoch als <xref:System.Activities.Activity> deklariert, sodass eine nicht generische Überladung von `Invoke` verwendet wird, die ein Wörterbuch mit Argumenten anstelle eines einzelnen Rückgabewerts zurückgibt.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#121](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#121)]  
  
 [!code-csharp[CFX_WorkflowInvokerExample#21](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#21)]  
  
## <a name="using-workflowapplication"></a>Verwenden von WorkflowApplication  

 <xref:System.Activities.WorkflowApplication> stellt einen umfangreichen Satz von Funktionen für die Workflowinstanzverwaltung bereit. <xref:System.Activities.WorkflowApplication> agiert als threadsicherer Proxy des tatsächlichen <xref:System.Activities.Hosting.WorkflowInstance>-Objekts, der die Laufzeit kapselt und Methoden bereitstellt, mit denen Workflowinstanzen erstellt und geladen werden und Lebenszyklusereignisse angehalten, fortgesetzt oder beendet werden bzw. Benachrichtigungen dazu erfolgen können. Zum Ausführen eines Workflows mit <xref:System.Activities.WorkflowApplication> erstellen Sie das <xref:System.Activities.WorkflowApplication>-Objekt, abonnieren gewünschte Lebenszyklusereignisse, starten den Workflow und warten dann auf die Beendigung. In diesem Beispiel wird eine Workflowdefinition erstellt, die aus einer <xref:System.Activities.Statements.WriteLine>-Aktivität besteht, und es wird eine <xref:System.Activities.WorkflowApplication> unter Verwendung der angegebenen Workflowdefinition erstellt. <xref:System.Activities.WorkflowApplication.Completed%2A> wird so behandelt, dass der Host bei Abschluss des Workflows benachrichtigt wird, der Workflow mit einem Aufruf von <xref:System.Activities.WorkflowApplication.Run%2A> beginnt und der Host auf den Abschluss des Workflows wartet. Nach Abschluss des Workflows wird das <xref:System.Threading.AutoResetEvent>-Objekt festgelegt, und die Hostanwendung kann die Ausführung fortsetzen, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#31](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#31)]  
  
### <a name="workflowapplication-lifecycle-events"></a>WorkflowApplication-Lebenszyklusereignisse  

 Zusätzlich zum Fall <xref:System.Activities.WorkflowApplication.Completed%2A> können Hostautoren benachrichtigt werden, wenn ein Workflow entladen wird (<xref:System.Activities.WorkflowApplication.Unloaded%2A>), abgebrochen wurde (<xref:System.Activities.WorkflowApplication.Aborted%2A>), in den Leerlauf wechselt (<xref:System.Activities.WorkflowApplication.Idle%2A> und <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>) oder eine nicht behandelte Ausnahme auftritt (<xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>). Workflowanwendungsentwickler können diese Benachrichtigungen behandeln und entsprechend reagieren, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#32](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#32)]  
  
### <a name="setting-input-arguments-of-a-workflow"></a>Festlegen der Eingabeargumente eines Workflows  

 Daten können beim Start eines Workflows mithilfe eines Wörterbuchs mit Parametern in den Workflow übergeben werden. Diese Vorgehensweise ähnelt dem Übergeben von Daten bei der Verwendung des <xref:System.Activities.WorkflowInvoker>-Objekts. Jedes Element im Wörterbuch ist einem Eingabeargument des angegebenen Workflows zugeordnet. In diesem Beispiel wird ein Workflow aufgerufen, der aus einer <xref:System.Activities.Statements.WriteLine>-Aktivität besteht, und das zugehörige <xref:System.Activities.Statements.WriteLine.Text%2A>-Argument wird mit dem Wörterbuch von Eingabeparametern angegeben.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#30](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#30)]  
  
### <a name="retrieving-output-arguments-of-a-workflow"></a>Abrufen der Ausgabeargumente eines Workflows  

 Wenn ein Workflow abgeschlossen wird, können alle Ausgabeargumente in den <xref:System.Activities.WorkflowApplication.Completed%2A>-Handler abgerufen werden, indem auf das <xref:System.Activities.WorkflowApplicationCompletedEventArgs.Outputs%2A?displayProperty=nameWithType>-Wörterbuch zugegriffen wird. Im folgenden Beispiel wird ein Workflow mit <xref:System.Activities.WorkflowApplication> gehostet. Eine- <xref:System.Activities.WorkflowApplication> Instanz wird mithilfe einer Workflow Definition erstellt, die aus einer einzelnen- `DiceRoll` Aktivität besteht. Die `DiceRoll`-Aktivität verfügt über zwei Ausgabeargumente, die die Ergebnisse des Würfelvorgangs darstellen. Wenn der Workflow abgeschlossen ist, werden die Ausgaben im <xref:System.Activities.WorkflowApplication.Completed%2A>-Handler abgerufen.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#130](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#130)]  
  
 [!code-csharp[CFX_WorkflowApplicationExample#21](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#21)]  
  
> [!NOTE]
> Das <xref:System.Activities.WorkflowApplication>-Objekt und das <xref:System.Activities.WorkflowInvoker>-Objekt akzeptieren ein Wörterbuch mit Eingabeargumenten und geben ein Wörterbuch mit `out`-Argumenten zurück. Diese Wörterbuchparameter, Eigenschaften und Rückgabewerte haben den Typ `IDictionary<string, object>`. Die tatsächliche Instanz der Wörterbuchklasse, die übergeben wird, kann jede Klasse sein, die `IDictionary<string, object>` implementiert. In diesen Beispielen wird `Dictionary<string, object>` verwendet. Weitere Informationen zu Wörterbüchern finden Sie unter <xref:System.Collections.Generic.IDictionary%602> und <xref:System.Collections.Generic.Dictionary%602> .  
  
### <a name="passing-data-into-a-running-workflow-using-bookmarks"></a>Übergeben von Daten in einen ausgeführten Workflow mithilfe von Lesezeichen  

 Lesezeichen stellen den Mechanismus dar, mit dem eine Aktivität passiv abwarten kann, bis sie wieder aufgenommen wird. Sie sind außerdem ein Mechanismus für das Übergeben von Daten in eine ausgeführte Workflowinstanz. Wenn eine Aktivität auf Daten wartet, kann sie ein <xref:System.Activities.Bookmark>-Objekt erstellen und eine Rückrufmethode registrieren, die aufgerufen werden soll, wenn das <xref:System.Activities.Bookmark>-Objekt wieder aufgenommen wird, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
 Bei der Ausführung erstellt die `ReadLine`-Aktivität ein <xref:System.Activities.Bookmark>-Objekt, registriert einen Rückruf und wartet dann darauf, dass das <xref:System.Activities.Bookmark>-Objekt wieder aufgenommen wird. Bei der Wiederaufnahme weist die `ReadLine`-Aktivität die Daten zu, die mit dem <xref:System.Activities.Bookmark>-Objekt an das <xref:System.Activities.Activity%601.Result%2A>-Argument übergeben wurden. In diesem Beispiel wird ein Workflow erstellt, der mit der `ReadLine`-Aktivität den Namen des Benutzers erfasst und im Konsolenfenster anzeigt.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#22](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#22)]  
  
 Wenn die `ReadLine`-Aktivität ausgeführt wird, erstellt sie ein <xref:System.Activities.Bookmark>-Objekt mit dem Namen `UserName` und wartet dann darauf, dass das Lesezeichen wieder aufgenommen wird. Der Host sammelt die gewünschten Daten und nimmt das <xref:System.Activities.Bookmark>-Objekt dann wieder auf. Der Workflow wird fortgesetzt, zeigt den Namen an und wird dann abgeschlossen.  
  
 Die Hostanwendung kann den Workflow überprüfen, um zu bestimmen, ob aktive Lesezeichen vorhanden sind. Hierfür werden die <xref:System.Activities.WorkflowApplication.GetBookmarks%2A>-Methode einer <xref:System.Activities.WorkflowApplication>-Instanz aufgerufen oder die <xref:System.Activities.WorkflowApplicationIdleEventArgs> im <xref:System.Activities.WorkflowApplication.Idle%2A>-Handler überprüft.  
  
 Das folgende Codebeispiel ähnelt dem vorherigen Beispiel, bis auf die Tatsache, dass die aktiven Lesezeichen aufgelistet werden, bevor das Lesezeichen wieder aufgenommen wird. Der Workflow wird gestartet, und sobald das <xref:System.Activities.Bookmark> erstellt wurde und der Workflow in den Leerlauf übergeht, wird <xref:System.Activities.WorkflowApplication.GetBookmarks%2A> aufgerufen. Wenn der Workflow abgeschlossen ist, wird die folgende Ausgabe in der Konsole angezeigt.  
  
 **Wie heißen Sie?**  
**BookmarkName: username-Besitzer Display Name: read-line** 
 **Steve** 
 **Hallo, Steve**

[!code-csharp[CFX_WorkflowApplicationExample#14](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#14)]  
  
 Im folgenden Codebeispiel werden die in den <xref:System.Activities.WorkflowApplicationIdleEventArgs>-Handler einer <xref:System.Activities.WorkflowApplication.Idle%2A>-Instanz übergebenen <xref:System.Activities.WorkflowApplication> überprüft. In diesem Beispiel geht der Workflow in den Leerlauf über und verfügt über ein <xref:System.Activities.Bookmark> mit dem Namen `EnterGuess`, das sich im Besitz einer Aktivität mit dem Namen `ReadInt` befindet. Dieses Codebeispiel basiert auf der Vorgehens [Weise: Ausführen eines Workflows](how-to-run-a-workflow.md), der Teil des [Tutorials "Getting Started](getting-started-tutorial.md)" ist. Wenn der <xref:System.Activities.WorkflowApplication.Idle%2A>-Handler in diesem Schritt geändert wird, um den Code aus diesem Beispiel zu enthalten, wird die folgende Ausgabe angezeigt.  
  
 **BookmarkName: EnterGuess - OwnerDisplayName: ReadInt**

 [!code-csharp[CFX_WorkflowApplicationExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#2)]  
  
## <a name="summary"></a>Zusammenfassung  

 <xref:System.Activities.WorkflowInvoker> bietet eine einfache Möglichkeit für das Aufrufen von Workflows. Es stellt auch Methoden zum Übergeben von Daten zu Beginn eines Workflows und für das Extrahieren von Daten aus einem abgeschlossenen Workflow bereit, bietet jedoch keine komplexeren Szenarien, in denen <xref:System.Activities.WorkflowApplication> verwendet werden kann.
