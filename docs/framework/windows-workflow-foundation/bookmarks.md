---
title: Lesezeichen - WF
ms.date: 03/30/2017
ms.assetid: 9b51a346-09ae-455c-a70a-e2264ddeb9e2
ms.openlocfilehash: c5bd8130ee623599e80014777baf92986c3b6969
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183008"
---
# <a name="bookmarks"></a>Lesezeichen
Lesezeichen stellen für eine Aktivität eine Möglichkeit dar, passiv auf eine Eingabe zu warten, ohne einen Workflowthread weiter auszuführen. Wenn eine Aktivität signalisiert, dass sie auf eine Reaktion wartet, kann sie ein Lesezeichen erstellen. Damit wird der Laufzeit angezeigt, dass die Ausführung der Aktivität nicht als abgeschlossen betrachtet werden kann, auch wenn die momentan ausgeführte Methode (die das <xref:System.Activities.Bookmark> erstellt hat) zurückkehrt.  
  
## <a name="bookmark-basics"></a>Grundlegendes zu Lesezeichen  
 Ein <xref:System.Activities.Bookmark> stellt einen Punkt dar, an dem die Ausführung in einer Workflowinstanz wiederaufgenommen werden kann (und durch den Eingaben übermittelt werden können). In der Regel wird einem <xref:System.Activities.Bookmark> ein Name gegeben, und externer Code (Host oder Erweiterung) ist für das Fortsetzen des Lesezeichens mit relevanten Daten zuständig. Wenn ein <xref:System.Activities.Bookmark> fortgesetzt wird, plant die Workflowlaufzeit den <xref:System.Activities.BookmarkCallback>-Delegaten, der diesem <xref:System.Activities.Bookmark> bei seiner Erstellung zugeordnet war.  
  
## <a name="bookmark-options"></a>Lesezeichenoptionen  
 Die <xref:System.Activities.BookmarkOptions> -Klasse gibt den Typ des <xref:System.Activities.Bookmark> an, das erstellt wird. Die möglichen Werte, die sich nicht gegenseitig ausschließen, sind <xref:System.Activities.BookmarkOptions.None>, <xref:System.Activities.BookmarkOptions.MultipleResume> und <xref:System.Activities.BookmarkOptions.NonBlocking>. Verwenden Sie die Standardeinstellung <xref:System.Activities.BookmarkOptions.None>, wenn Sie ein <xref:System.Activities.Bookmark> erstellen, das genau einmal fortgesetzt werden soll. Verwenden Sie <xref:System.Activities.BookmarkOptions.MultipleResume>, wenn Sie ein <xref:System.Activities.Bookmark> erstellen, das mehrmals fortgesetzt werden kann. Verwenden Sie <xref:System.Activities.BookmarkOptions.NonBlocking>, wenn Sie ein <xref:System.Activities.Bookmark> erstellen, das möglicherweise nie fortgesetzt wird. Im Gegensatz zu Lesezeichen, die mit den standardmäßigen <xref:System.Activities.BookmarkOptions> erstellt werden, verhindern <xref:System.Activities.BookmarkOptions.NonBlocking>-Lesezeichen nicht, dass eine Aktivität abgeschlossen wird.  
  
## <a name="bookmark-resumption"></a>Wiederaufnahme von Lesezeichen  
 Lesezeichen können von Code außerhalb eines Workflows mit einer der <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A>-Überladungen wieder aufgenommen werden. In diesem Beispiel wird eine `ReadLine`-Aktivität erstellt. Bei der Ausführung erstellt die `ReadLine`-Aktivität ein <xref:System.Activities.Bookmark>-Objekt, registriert einen Rückruf und wartet dann darauf, dass das <xref:System.Activities.Bookmark>-Objekt wieder aufgenommen wird. Bei der Wiederaufnahme weist die `ReadLine`-Aktivität die Daten zu, die mit dem <xref:System.Activities.Bookmark>-Objekt an das <xref:System.Activities.Activity%601.Result%2A>-Argument übergeben wurden.  
  
```csharp  
public sealed class ReadLine : NativeActivity<string>  
{  
    [RequiredArgument]  
    public  InArgument<string> BookmarkName { get; set; }  
  
    protected override void Execute(NativeActivityContext context)  
    {  
        // Create a Bookmark and wait for it to be resumed.  
        context.CreateBookmark(BookmarkName.Get(context),
            new BookmarkCallback(OnResumeBookmark));  
    }  
  
    // NativeActivity derived activities that do asynchronous operations by calling
    // one of the CreateBookmark overloads defined on System.Activities.NativeActivityContext
    // must override the CanInduceIdle property and return true.  
    protected override bool CanInduceIdle  
    {  
        get { return true; }  
    }  
  
    public void OnResumeBookmark(NativeActivityContext context, Bookmark bookmark, object obj)  
    {  
        // When the Bookmark is resumed, assign its value to  
        // the Result argument.  
        Result.Set(context, (string)obj);  
    }  
}  
```  
  
 In diesem Beispiel wird ein Workflow erstellt, der mit der `ReadLine`-Aktivität den Namen des Benutzers erfasst und im Konsolenfenster anzeigt. Die Hostanwendung führt die tatsächlichen Aufgaben aus; sie sammelt die Eingaben und übergibt sie an den Workflow, indem das <xref:System.Activities.Bookmark> wieder aufgenommen wird.  
  
```csharp  
Variable<string> name = new Variable<string>  
{  
    Name = "name"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        name  
    },  
    Activities =  
    {  
        new WriteLine()  
        {  
            Text = "What is your name?"  
        },  
        new ReadLine()  
        {  
            BookmarkName = "UserName",  
            Result = name  
        },  
        new WriteLine()  
        {  
            Text = new InArgument<string>((env) => "Hello, " + name.Get(env))  
        }  
    }  
};  
  
AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
// Create the WorkflowApplication using the desired  
// workflow definition.  
WorkflowApplication wfApp = new WorkflowApplication(wf);  
  
// Handle the desired lifecycle events.  
wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
{  
    // Signal the host that the workflow is complete.  
    syncEvent.Set();  
};  
  
// Start the workflow.  
wfApp.Run();  
  
// Collect the user's name and resume the bookmark.  
// Bookmark resumption only occurs when the workflow  
// is idle. If a call to ResumeBookmark is made and the workflow  
// is not idle, ResumeBookmark blocks until the workflow becomes  
// idle before resuming the bookmark.  
wfApp.ResumeBookmark("UserName", Console.ReadLine());  
  
// Wait for Completed to arrive and signal that  
// the workflow is complete.  
syncEvent.WaitOne();  
```  
  
 Wenn die `ReadLine`-Aktivität ausgeführt wird, erstellt sie ein <xref:System.Activities.Bookmark>-Objekt mit dem Namen `UserName` und wartet dann darauf, dass das Lesezeichen wieder aufgenommen wird. Der Host sammelt die gewünschten Daten und nimmt das <xref:System.Activities.Bookmark>-Objekt dann wieder auf. Der Workflow wird fortgesetzt, zeigt den Namen an und wird dann abgeschlossen. Beachten Sie, dass kein Synchronisierungscode erforderlich ist, wenn das Lesezeichen wieder aufgenommen werden soll. Ein <xref:System.Activities.Bookmark> kann nur fortgesetzt werden, wenn sich der Workflow im Leerlauf befindet. Wenn er sich nicht im Leerlauf befindet, wird der Aufruf von <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> blockiert, bis der Workflow in den Leerlauf wechselt.  
  
## <a name="bookmark-resumption-result"></a>Ergebnis der Wiederaufnahme von Lesezeichen  
 Das <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> gibt einen <xref:System.Activities.BookmarkResumptionResult>-Enumerationswert zurück, um die Ergebnisse der Anforderung für eine Wiederaufnahme von Lesezeichen anzugeben. Die möglichen Rückgabewerte sind <xref:System.Activities.BookmarkResumptionResult.Success>, <xref:System.Activities.BookmarkResumptionResult.NotReady> und <xref:System.Activities.BookmarkResumptionResult.NotFound>. Hosts und Erweiterungen können mit diesem Wert bestimmen, wie fortgefahren werden soll.
