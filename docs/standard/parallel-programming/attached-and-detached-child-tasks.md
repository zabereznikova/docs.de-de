---
title: Angefügte und getrennte untergeordnete Aufgaben
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, child tasks
ms.assetid: c95788bf-90a6-4e96-b7bc-58e36a228cc5
ms.openlocfilehash: 8f15ee4f136e3e2df1a4e1c7683467f2a4bc9bc0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123183"
---
# <a name="attached-and-detached-child-tasks"></a>Angefügte und getrennte untergeordnete Aufgaben
Eine *untergeordnete Aufgabe* (oder *geschachtelte Aufgabe*) ist eine <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Instanz, die im Benutzerdelegaten einer anderen Aufgabe erstellt wird, die als *übergeordnete Aufgabe* bezeichnet wird. Eine untergeordnete Aufgabe kann entweder getrennt oder angefügt werden. Eine *getrennte untergeordnete Aufgabe* ist eine Aufgabe, die unabhängig von der übergeordneten ausgeführt wird. Eine *angefügte ungeordnete Aufgabe* ist eine geschachtelte Aufgabe, die mit der Option <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> erstellt wird, deren übergeordnete Aufgabe nicht explizit oder standardmäßig verhindert, dass die Aufgabe angefügt wird. Eine Aufgabe kann beliebig viele angefügte oder getrennte untergeordnete Aufgaben erstellen. Die Anzahl wird lediglich durch die Systemressourcen beschränkt.  
  
 In der folgenden Tabelle sind die grundlegenden Unterschiede zwischen den zwei Arten von untergeordneten Aufgaben aufgeführt.  
  
|Kategorie|Getrennte untergeordnete Aufgaben|Angefügte untergeordnete Aufgaben|  
|--------------|--------------------------|--------------------------|  
|Das übergeordnete Element wartet auf den Abschluss der untergeordneten Aufgaben.|Nein|Ja|  
|Das übergeordnete Element gibt von untergeordneten Aufgaben ausgelöste Ausnahmen weiter.|Nein|Ja|  
|Der Status des übergeordneten Elements hängt vom Status des untergeordneten Elements ab.|Nein|Ja|  
  
 In den meisten Szenarios empfiehlt sich jedoch die Verwendung von getrennten untergeordneten Aufgabe, da die Beziehungen zu anderen Aufgaben weniger komplex sind. Aus diesem Grund werden in übergeordneten Aufgaben erstellte Aufgaben standardmäßig getrennt. Um die angefügte untergeordnete Aufgabe zu erstellen, müssen Sie die <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType>-Option explizit angeben.  
  
## <a name="detached-child-tasks"></a>Getrennte untergeordnete Aufgaben  
 Obwohl eine untergeordnete Aufgabe durch eine übergeordnete Aufgabe erstellt wird, hängt diese standardmäßig von der übergeordneten Aufgabe ab. Im folgenden Beispiel erstellt eine übergeordnete Aufgabe eine einfache untergeordnete Aufgabe: Wenn Sie den Beispielcode mehrmals ausführen, stellen Sie möglicherweise fest, dass sich die Ausgabe von der Ausgabe im Beispiel unterscheidet und dass die Ausgabe sich möglicherweise bei jeder Ausführung des Codes ändert. Dies liegt daran, dass die übergeordnete und die untergeordnete Aufgabe unabhängig voneinander ausgeführt werden; das untergeordnete Element ist eine getrennte Aufgabe. Im Beispiel wird nur auf den Abschluss der übergeordneten Aufgabe gewartet, und die untergeordnete Aufgabe wird möglicherweise nicht ausgeführt oder abgeschlossen, ehe die Konsolen-App beendet wird.  
  
 [!code-csharp[TPL_ChildTasks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_childtasks/cs/nested1.cs#1)]
 [!code-vb[TPL_ChildTasks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_childtasks/vb/nested1.vb#1)]  
  
 Wenn die untergeordnete Aufgabe durch ein <xref:System.Threading.Tasks.Task%601>-Objekt statt einem <xref:System.Threading.Tasks.Task>-Objekt dargestellt wird, können Sie sicherstellen, dass die übergeordnete Aufgabe auf das Abschließen der Aufgabe des untergeordneten Elements wartet, indem Sie auf die <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>-Eigenschaft des untergeordneten Elements zugreift, auch wenn es sich dabei um eine getrennte untergeordnete Aufgabe handelt. Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft blockiert, wie im folgenden Beispiel gezeigt, bis die Aufgabe abgeschlossen ist.  
  
 [!code-csharp[TPL_ChildTasks#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_childtasks/cs/childtasks.cs#4)]
 [!code-vb[TPL_ChildTasks#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_childtasks/vb/tpl_childtasks.vb#4)]  
  
## <a name="attached-child-tasks"></a>Angefügte untergeordnete Aufgaben  
 Anders als getrennte untergeordnete Aufgaben werden angefügte untergeordnete Aufgaben eng mit dem übergeordneten Element synchronisiert. Sie können die getrennte untergeordnete Aufgabe im vorherigen Beispiel in eine angefügte untergeordnete Aufgabe ändern, indem Sie wie im folgenden Beispiel gezeigt die <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType>-Option in der Aufgabenerstellungsanweisung verwenden. In diesem Code schließt die angefügte untergeordnete Aufgabe vor ihrem übergeordneten Element ab. Deshalb ist das Ergebnis im Beispiel bei jedem Ausführen des Codes gleich.  
  
 [!code-csharp[TPL_ChildTasks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_childtasks/cs/child1.cs#2)]
 [!code-vb[TPL_ChildTasks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_childtasks/vb/child1.vb#2)]  
  
 Mithilfe von angefügten untergeordneten Aufgaben können Sie synchronisierte Diagramme von asynchronen Vorgängen erstellen.  
  
 Die untergeordnete Aufgabe kann jedoch nur dann an die übergeordnete Aufgabe angefügt werden, wenn die übergeordnete Aufgabe das Anfügen von untergeordneten Aufgaben nicht verhindert. Übergeordnete Aufgaben können explizit verhindern, dass untergeordnete Aufgaben angefügt werden, indem die <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>-Option des Klassenkonstruktors der übergeordneten Aufgabe oder die <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>-Methode angegeben wird. Übergeordnete Aufgaben verhindern das Anfügen von untergeordneten Aufgaben explizit, wenn sie mithilfe des Aufrufs der <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType>-Methode erstellt werden. Dies wird anhand des folgenden Beispiels veranschaulicht. Es ist weitestgehend mit dem vorherigen Beispiel identisch, allerdings wurde die übergeordnete Aufgabe hier mit der <xref:System.Threading.Tasks.Task.Run%28System.Action%29?displayProperty=nameWithType>-Methode und nicht mit der <xref:System.Threading.Tasks.TaskFactory.StartNew%28System.Action%29?displayProperty=nameWithType>-Methode erstellt. Da die untergeordnete Aufgabe nicht an die übergeordnete Aufgabe angefügt werden kann, ist die Ausgabe dieses Beispiels nicht vorhersehbar. Da die standardmäßigen Aufgabenerstellungsoptionen für <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType>-Überladungen <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> einschließen, entspricht dieses Beispiel funktional dem ersten Beispiel im Abschnitt „Getrennte untergeordnete Aufgaben“.  
  
 [!code-csharp[TPL_ChildTasks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_childtasks/cs/child1a.cs#3)]
 [!code-vb[TPL_ChildTasks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_childtasks/vb/child1a.vb#3)]  
  
## <a name="exceptions-in-child-tasks"></a>Ausnahmen in untergeordneten Aufgaben  
 Wenn eine getrennte untergeordnete Aufgabe eine Ausnahme auslöst, muss diese direkt in der übergeordneten Aufgabe beachtet oder behandelt werden, ebenso wie dies bei nicht geschachtelten Aufgaben der Fall ist. Wenn eine angefügte untergeordnete Aufgabe eine Ausnahme auslöst, wird die Ausnahme automatisch an die übergeordnete Aufgabe weitergeleitet und an den Thread zurückgesendet, der wartet oder auf die <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>-Eigenschaft der Aufgabe zugreifen möchte. Daher können durch Verwendung angefügter untergeordneter Aufgaben alle Ausnahmen an nur einem Punkt, beim Aufruf von <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> im aufrufenden Thread, verarbeitet werden. Weitere Informationen finden Sie unter [Ausnahmebehandlung (Task Parallel Library)](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md).  
  
## <a name="cancellation-and-child-tasks"></a>Abbruch und untergeordnete Aufgaben  
 Das Abbrechen einer Aufgabe ist kooperativ. Um "abbrechbar" zu sein, muss jede angefügte oder getrennte untergeordnete Aufgabe den Status des Abbruchtokens überwachen. Wenn Sie mit einer Abbruchanforderung ein übergeordnetes Element und alle untergeordneten Elemente abbrechen möchten, übergeben Sie das gleiche Token als Argument an alle Aufgaben und stellen in jeder Aufgabe die Logik zum Reagieren auf die Anforderung in bereit. Weitere Informationen finden Sie unter [Aufgabenabbruch](../../../docs/standard/parallel-programming/task-cancellation.md) und [Vorgehensweise: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md).  
  
### <a name="when-the-parent-cancels"></a>Abbruch eines übergeordneten Elements  
 Wenn eine übergeordnete Aufgabe abgebrochen wird, bevor eine untergeordnete Aufgabe gestartet wurde, wird die untergeordnete Aufgabe nie gestartet. Wenn ein übergeordnetes Element nach dem Start einer untergeordneten Aufgabe abgebrochen wird, wird die untergeordnete bis zum Abschluss ausgeführt, sofern keine eigene Abbruchlogik vorhanden ist. Weitere Informationen finden Sie unter [Aufgabenabbruch](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
### <a name="when-a-detached-child-task-cancels"></a>Abbruch einer getrennten untergeordneten Aufgabe  
 Wenn eine getrennte untergeordnete Aufgabe mit dem gleichen Token abgebrochen wird, das an die übergeordnete Aufgabe übergeben wurde, und das übergeordnete Element nicht auf die untergeordnete Aufgabe wartet, wird keine Ausnahme weitergeleitet, da die Ausnahme als Kooperationsabbruch ohne Auswirkungen behandelt wird. Dieses Verhalten stimmt mit dem beliebiger Aufgaben der obersten Ebene überein.  
  
### <a name="when-an-attached-child-task-cancels"></a>Abbruch einer angefügten untergeordneten Aufgabe  
 Wenn eine angefügte untergeordnete Aufgabe mit dem gleichen Token abgebrochen wird, das an die übergeordnete Aufgabe übergeben wurde, wird eine <xref:System.Threading.Tasks.TaskCanceledException> an den Verbindungsthread in einer <xref:System.AggregateException> weitergeleitet. Sie müssen auf die übergeordnete Aufgabe warten, damit Sie die Ausnahmen ohne Auswirkung zusammen mit allen einen Fehler auslösenden Ausnahmen behandeln können, die durch ein Diagramm angefügter untergeordneter Aufgaben nach oben weitergeleitet werden.  
  
 Weitere Informationen finden Sie unter [Ausnahmebehandlung (Task Parallel Library)](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md).  
  
## <a name="preventing-a-child-task-from-attaching-to-its-parent"></a>Verhindern, dass sich eine untergeordnete Aufgabe mit ihrem übergeordneten Element verbindet  
 Ein Ausnahmefehler, der durch eine untergeordnete Aufgabe ausgelöst wird, wird an die übergeordnete Aufgabe weitergegeben. Sie können dieses Verhalten nutzen, um alle Ausnahmen von untergeordneten Aufgaben einer Stammaufgabe zu beobachten anstatt eine Aufgabenstruktur zu durchlaufen. Die Ausnahmeweitergabe kann jedoch problematisch werden, wenn eine übergeordnete Aufgabe einen Anhang aus einem anderen Code erwartet. Betrachten Sie beispielsweise eine Anwendung, die eine Bibliothekskomponente eines Drittanbietern aus einem <xref:System.Threading.Tasks.Task>-Objekt aufruft. Wenn die Bibliothekskomponente von Drittanbietern auch ein <xref:System.Threading.Tasks.Task>-Objekt erstellt und <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> angibt, um es zur übergeordneten Aufgabe anzufügen, werden alle Ausnahmefehler, die in der untergeordneten Aufgabe auftreten, an das übergeordnete Element weitergegeben. Dies kann zu unerwartetem Verhalten in der Haupt-App führen.  
  
 Wenn eine untergeordnete Aufgabe nicht an die übergeordnete Aufgabe angefügt werden soll, geben Sie die <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>-Option an, wenn Sie das übergeordnete <xref:System.Threading.Tasks.Task> oder das <xref:System.Threading.Tasks.Task%601>-Objekt erstellen. Wenn eine Aufgabe versucht, sich an ihre übergeordnete Aufgabe anzufügen und für die übergeordnete Aufgabe die <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>-Option festgelegt wurde, kann die untergeordnete Aufgabe nicht an die übergeordnete Aufgabe angefügt werden und wird so ausgeführt, als sei die <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType>-Option nicht festgelegt worden.  
  
 Sie können auch verhindern, dass sich eine untergeordnete Aufgabe an das übergeordnete Element anfügt, wenn die untergeordnete Aufgabe nicht rechtzeitig beendet wird. Da eine übergeordnete Aufgabe nicht beendet wird, ehe alle untergeordneten Aufgaben abgeschlossen sind, kann eine untergeordnete Aufgabe mit langer Laufzeit zu einer Verschlechterung der Leistung der gesamten App führen. Ein Beispiel zur Verbesserung der App-Leistung durch Verhindern des Anfügens einer Aufgabe an das übergeordnete Element finden Sie unter [Vorgehensweise: Verhindern des Anfügens einer untergeordneten Aufgabe an die übergeordnete Aufgabe](../../../docs/standard/parallel-programming/how-to-prevent-a-child-task-from-attaching-to-its-parent.md).  
  
## <a name="see-also"></a>Siehe auch

- [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)
- [Datenparallelität](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
