---
title: Lesezeichen-WF
ms.date: 03/30/2017
ms.assetid: 9b51a346-09ae-455c-a70a-e2264ddeb9e2
ms.openlocfilehash: 7a52823ff68d8f09895bb3a9323a57d3abccd823
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289112"
---
# <a name="bookmarks"></a><span data-ttu-id="a8620-102">Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="a8620-102">Bookmarks</span></span>

<span data-ttu-id="a8620-103">Lesezeichen stellen für eine Aktivität eine Möglichkeit dar, passiv auf eine Eingabe zu warten, ohne einen Workflowthread weiter auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a8620-103">Bookmarks are the mechanism that enables an activity to passively wait for input without holding onto a workflow thread.</span></span> <span data-ttu-id="a8620-104">Wenn eine Aktivität signalisiert, dass sie auf eine Reaktion wartet, kann sie ein Lesezeichen erstellen.</span><span class="sxs-lookup"><span data-stu-id="a8620-104">When an activity signals that it is waiting for stimulus, it can create a bookmark.</span></span> <span data-ttu-id="a8620-105">Damit wird der Laufzeit angezeigt, dass die Ausführung der Aktivität nicht als abgeschlossen betrachtet werden kann, auch wenn die momentan ausgeführte Methode (die das <xref:System.Activities.Bookmark> erstellt hat) zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="a8620-105">This indicates to the runtime that the activity’s execution should not be considered complete even when the currently executing method (which created the <xref:System.Activities.Bookmark>) returns.</span></span>  
  
## <a name="bookmark-basics"></a><span data-ttu-id="a8620-106">Grundlegendes zu Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="a8620-106">Bookmark Basics</span></span>  

 <span data-ttu-id="a8620-107">Ein <xref:System.Activities.Bookmark> stellt einen Punkt dar, an dem die Ausführung in einer Workflowinstanz wiederaufgenommen werden kann (und durch den Eingaben übermittelt werden können).</span><span class="sxs-lookup"><span data-stu-id="a8620-107">A <xref:System.Activities.Bookmark> represents a point at which execution can be resumed (and through which input can be delivered) within a workflow instance.</span></span> <span data-ttu-id="a8620-108">In der Regel wird einem <xref:System.Activities.Bookmark> ein Name gegeben, und externer Code (Host oder Erweiterung) ist für das Fortsetzen des Lesezeichens mit relevanten Daten zuständig.</span><span class="sxs-lookup"><span data-stu-id="a8620-108">Typically, a <xref:System.Activities.Bookmark> is given a name and external (host or extension) code is responsible for resuming the bookmark with relevant data.</span></span> <span data-ttu-id="a8620-109">Wenn ein <xref:System.Activities.Bookmark> fortgesetzt wird, plant die Workflowlaufzeit den <xref:System.Activities.BookmarkCallback>-Delegaten, der diesem <xref:System.Activities.Bookmark> bei seiner Erstellung zugeordnet war.</span><span class="sxs-lookup"><span data-stu-id="a8620-109">When a <xref:System.Activities.Bookmark> is resumed, the workflow runtime schedules the <xref:System.Activities.BookmarkCallback> delegate that was associated with that <xref:System.Activities.Bookmark> at the time of its creation.</span></span>  
  
## <a name="bookmark-options"></a><span data-ttu-id="a8620-110">Lesezeichenoptionen</span><span class="sxs-lookup"><span data-stu-id="a8620-110">Bookmark Options</span></span>  

 <span data-ttu-id="a8620-111">Die <xref:System.Activities.BookmarkOptions> -Klasse gibt den Typ des <xref:System.Activities.Bookmark> an, das erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a8620-111">The <xref:System.Activities.BookmarkOptions> class specifies the type of <xref:System.Activities.Bookmark> being created.</span></span> <span data-ttu-id="a8620-112">Die möglichen Werte, die sich nicht gegenseitig ausschließen, sind <xref:System.Activities.BookmarkOptions.None>, <xref:System.Activities.BookmarkOptions.MultipleResume> und <xref:System.Activities.BookmarkOptions.NonBlocking>.</span><span class="sxs-lookup"><span data-stu-id="a8620-112">The possible non mutually-exclusive values are <xref:System.Activities.BookmarkOptions.None>, <xref:System.Activities.BookmarkOptions.MultipleResume>, and <xref:System.Activities.BookmarkOptions.NonBlocking>.</span></span> <span data-ttu-id="a8620-113">Verwenden Sie die Standardeinstellung <xref:System.Activities.BookmarkOptions.None>, wenn Sie ein <xref:System.Activities.Bookmark> erstellen, das genau einmal fortgesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a8620-113">Use <xref:System.Activities.BookmarkOptions.None>, the default, when creating a <xref:System.Activities.Bookmark> that is expected to be resumed exactly once.</span></span> <span data-ttu-id="a8620-114">Verwenden Sie <xref:System.Activities.BookmarkOptions.MultipleResume>, wenn Sie ein <xref:System.Activities.Bookmark> erstellen, das mehrmals fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a8620-114">Use <xref:System.Activities.BookmarkOptions.MultipleResume> when creating a <xref:System.Activities.Bookmark> that can be resumed multiple times.</span></span> <span data-ttu-id="a8620-115">Verwenden Sie <xref:System.Activities.BookmarkOptions.NonBlocking>, wenn Sie ein <xref:System.Activities.Bookmark> erstellen, das möglicherweise nie fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="a8620-115">Use <xref:System.Activities.BookmarkOptions.NonBlocking> when creating a <xref:System.Activities.Bookmark> that might never be resumed.</span></span> <span data-ttu-id="a8620-116">Im Gegensatz zu Lesezeichen, die mit den standardmäßigen <xref:System.Activities.BookmarkOptions> erstellt werden, verhindern <xref:System.Activities.BookmarkOptions.NonBlocking>-Lesezeichen nicht, dass eine Aktivität abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="a8620-116">Unlike bookmarks created using the default <xref:System.Activities.BookmarkOptions>, <xref:System.Activities.BookmarkOptions.NonBlocking> bookmarks do not prevent an activity from completing.</span></span>  
  
## <a name="bookmark-resumption"></a><span data-ttu-id="a8620-117">Wiederaufnahme von Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="a8620-117">Bookmark Resumption</span></span>  

 <span data-ttu-id="a8620-118">Lesezeichen können von Code außerhalb eines Workflows mit einer der <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A>-Überladungen wieder aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="a8620-118">Bookmarks can be resumed by code outside of a workflow using one of the <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> overloads.</span></span> <span data-ttu-id="a8620-119">In diesem Beispiel wird eine `ReadLine`-Aktivität erstellt.</span><span class="sxs-lookup"><span data-stu-id="a8620-119">In this example, a `ReadLine` activity is created.</span></span> <span data-ttu-id="a8620-120">Bei der Ausführung erstellt die `ReadLine`-Aktivität ein <xref:System.Activities.Bookmark>-Objekt, registriert einen Rückruf und wartet dann darauf, dass das <xref:System.Activities.Bookmark>-Objekt wieder aufgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="a8620-120">When executed, the `ReadLine` activity creates a <xref:System.Activities.Bookmark>, registers a callback, and then waits for the <xref:System.Activities.Bookmark> to be resumed.</span></span> <span data-ttu-id="a8620-121">Bei der Wiederaufnahme weist die `ReadLine`-Aktivität die Daten zu, die mit dem <xref:System.Activities.Bookmark>-Objekt an das <xref:System.Activities.Activity%601.Result%2A>-Argument übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="a8620-121">When it is resumed, the `ReadLine` activity assigns the data that was passed with the <xref:System.Activities.Bookmark> to its <xref:System.Activities.Activity%601.Result%2A> argument.</span></span>  
  
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
  
 <span data-ttu-id="a8620-122">In diesem Beispiel wird ein Workflow erstellt, der mit der `ReadLine`-Aktivität den Namen des Benutzers erfasst und im Konsolenfenster anzeigt.</span><span class="sxs-lookup"><span data-stu-id="a8620-122">In this example, a workflow is created that uses the `ReadLine` activity to gather the user’s name and display it to the console window.</span></span> <span data-ttu-id="a8620-123">Die Hostanwendung führt die tatsächlichen Aufgaben aus; sie sammelt die Eingaben und übergibt sie an den Workflow, indem das <xref:System.Activities.Bookmark> wieder aufgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="a8620-123">The host application performs the actual work of gathering the input and passes it to the workflow by resuming the <xref:System.Activities.Bookmark>.</span></span>  
  
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
  
 <span data-ttu-id="a8620-124">Wenn die `ReadLine`-Aktivität ausgeführt wird, erstellt sie ein <xref:System.Activities.Bookmark>-Objekt mit dem Namen `UserName` und wartet dann darauf, dass das Lesezeichen wieder aufgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="a8620-124">When the `ReadLine` activity is executed, it creates a <xref:System.Activities.Bookmark> named `UserName` and then waits for the bookmark to be resumed.</span></span> <span data-ttu-id="a8620-125">Der Host sammelt die gewünschten Daten und nimmt das <xref:System.Activities.Bookmark>-Objekt dann wieder auf.</span><span class="sxs-lookup"><span data-stu-id="a8620-125">The host collects the desired data and then resumes the <xref:System.Activities.Bookmark>.</span></span> <span data-ttu-id="a8620-126">Der Workflow wird fortgesetzt, zeigt den Namen an und wird dann abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a8620-126">The workflow resumes, displays the name, and then completes.</span></span> <span data-ttu-id="a8620-127">Beachten Sie, dass kein Synchronisierungscode erforderlich ist, wenn das Lesezeichen wieder aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a8620-127">Note that no synchronization code is required with regard to resuming the bookmark.</span></span> <span data-ttu-id="a8620-128">Ein <xref:System.Activities.Bookmark> kann nur fortgesetzt werden, wenn sich der Workflow im Leerlauf befindet. Wenn er sich nicht im Leerlauf befindet, wird der Aufruf von <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> blockiert, bis der Workflow in den Leerlauf wechselt.</span><span class="sxs-lookup"><span data-stu-id="a8620-128">A <xref:System.Activities.Bookmark> can only be resumed when the workflow is idle, and if the workflow is not idle, the call to <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> blocks until the workflow becomes idle.</span></span>  
  
## <a name="bookmark-resumption-result"></a><span data-ttu-id="a8620-129">Ergebnis der Wiederaufnahme von Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="a8620-129">Bookmark Resumption Result</span></span>  

 <span data-ttu-id="a8620-130">Das <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> gibt einen <xref:System.Activities.BookmarkResumptionResult>-Enumerationswert zurück, um die Ergebnisse der Anforderung für eine Wiederaufnahme von Lesezeichen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a8620-130"><xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> returns a <xref:System.Activities.BookmarkResumptionResult> enumeration value to indicate the results of the bookmark resumption request.</span></span> <span data-ttu-id="a8620-131">Die möglichen Rückgabewerte sind <xref:System.Activities.BookmarkResumptionResult.Success>, <xref:System.Activities.BookmarkResumptionResult.NotReady> und <xref:System.Activities.BookmarkResumptionResult.NotFound>.</span><span class="sxs-lookup"><span data-stu-id="a8620-131">The possible return values are <xref:System.Activities.BookmarkResumptionResult.Success>, <xref:System.Activities.BookmarkResumptionResult.NotReady>, and <xref:System.Activities.BookmarkResumptionResult.NotFound>.</span></span> <span data-ttu-id="a8620-132">Hosts und Erweiterungen können mit diesem Wert bestimmen, wie fortgefahren werden soll.</span><span class="sxs-lookup"><span data-stu-id="a8620-132">Hosts and extensions can use this value to determine how to proceed.</span></span>
