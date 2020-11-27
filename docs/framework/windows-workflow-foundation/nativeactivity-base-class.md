---
title: NativeActivity-Basisklasse
ms.date: 03/30/2017
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
ms.openlocfilehash: d875f62dacadb2baf6b5d7e93ddb2933aed9cdb0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274958"
---
# <a name="nativeactivity-base-class"></a><span data-ttu-id="da311-102">NativeActivity-Basisklasse</span><span class="sxs-lookup"><span data-stu-id="da311-102">NativeActivity Base Class</span></span>

<span data-ttu-id="da311-103"><xref:System.Activities.NativeActivity> ist eine abstrakte Klasse mit einem geschützten Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="da311-103"><xref:System.Activities.NativeActivity> is an abstract class with a protected constructor.</span></span> <span data-ttu-id="da311-104">Wie <xref:System.Activities.CodeActivity> wird auch <xref:System.Activities.NativeActivity> zum Schreiben von imperativem Verhalten durch die Implementierung einer <xref:System.Activities.NativeActivity.Execute%2A>-Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="da311-104">Like <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> is used for writing imperative behavior by implementing an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span> <span data-ttu-id="da311-105">Im Gegensatz zu <xref:System.Activities.CodeActivity> verfügt <xref:System.Activities.NativeActivity> jedoch über Zugriff auf alle verfügbar gemachten Funktionen der Workflowlaufzeit durch das <xref:System.Activities.NativeActivityContext>-Objekt, das an die <xref:System.Activities.NativeActivity.Execute%2A>-Methode übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="da311-105">Unlike <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> has access to all of the exposed features of the workflow runtime through the <xref:System.Activities.NativeActivityContext> object passed to the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

## <a name="using-nativeactivitycontext"></a><span data-ttu-id="da311-106">Verwenden von NativeActivityContext</span><span class="sxs-lookup"><span data-stu-id="da311-106">Using NativeActivityContext</span></span>

 <span data-ttu-id="da311-107">Innerhalb der <xref:System.Activities.NativeActivity.Execute%2A>-Methode kann mithilfe von Membern des `context`-Parameters vom Typ <xref:System.Activities.NativeActivityContext> auf Funktionen des Workflows zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="da311-107">Features of the workflow runtime can be accessed from within the <xref:System.Activities.NativeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.NativeActivityContext>.</span></span> <span data-ttu-id="da311-108">Über <xref:System.Activities.NativeActivityContext> sind unter anderem folgende Funktionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="da311-108">The features available through <xref:System.Activities.NativeActivityContext> include the following:</span></span>

- <span data-ttu-id="da311-109">Abrufen und Festlegen von Argumenten und Variablen</span><span class="sxs-lookup"><span data-stu-id="da311-109">Getting and setting of arguments and variables.</span></span>

- <span data-ttu-id="da311-110">Planen von untergeordneten Aktivitäten mit <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A></span><span class="sxs-lookup"><span data-stu-id="da311-110">Scheduling child activities with <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A></span></span>

- <span data-ttu-id="da311-111">Abbrechen der Ausführung von Aktivitäten mit <xref:System.Activities.NativeActivityContext.Abort%2A>.</span><span class="sxs-lookup"><span data-stu-id="da311-111">Aborting activity execution using <xref:System.Activities.NativeActivityContext.Abort%2A>.</span></span>

- <span data-ttu-id="da311-112">Abbrechen der Ausführung untergeordneter Elemente mit <xref:System.Activities.NativeActivityContext.CancelChild%2A> und <xref:System.Activities.NativeActivityContext.CancelChildren%2A></span><span class="sxs-lookup"><span data-stu-id="da311-112">Canceling child execution using <xref:System.Activities.NativeActivityContext.CancelChild%2A> and <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.</span></span>

- <span data-ttu-id="da311-113">Zugreifen auf Aktivitätslesezeichen mit Methoden wie <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A> und <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A></span><span class="sxs-lookup"><span data-stu-id="da311-113">Access to activity bookmarks using such methods as <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A>, and <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.</span></span>

- <span data-ttu-id="da311-114">Benutzerdefinierte Überwachungsfunktionen mit <xref:System.Activities.CodeActivityContext.Track%2A></span><span class="sxs-lookup"><span data-stu-id="da311-114">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

- <span data-ttu-id="da311-115">Zugeifen auf die Ausführungseigenschaften und Werteigenschaften der Aktivität mit <xref:System.Activities.CodeActivityContext.GetProperty%2A> und <xref:System.Activities.NativeActivityContext.GetValue%2A></span><span class="sxs-lookup"><span data-stu-id="da311-115">Access to the activity’s execution properties and value properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A> and <xref:System.Activities.NativeActivityContext.GetValue%2A>.</span></span>

- <span data-ttu-id="da311-116">Planen von Aktivitätsaktionen und Funktionen mit <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> und <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A></span><span class="sxs-lookup"><span data-stu-id="da311-116">Scheduling activity actions and functions using <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> and <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.</span></span>

### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a><span data-ttu-id="da311-117">So erstellen Sie eine benutzerdefinierte Aktivität, die von NativeActivity erbt</span><span class="sxs-lookup"><span data-stu-id="da311-117">To create a custom activity that inherits from NativeActivity</span></span>

1. <span data-ttu-id="da311-118">Openvisual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="da311-118">OpenVisual Studio 2010.</span></span>

2. <span data-ttu-id="da311-119">Wählen Sie **Datei**, **neu** und dann **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="da311-119">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="da311-120">Wählen Sie im Fenster **Projekttypen** unter **Visual c#** die Option **Workflow 4,0** aus, und wählen Sie den Knoten **v2010** aus.</span><span class="sxs-lookup"><span data-stu-id="da311-120">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="da311-121">Wählen Sie im Fenster **Vorlagen** die Option **Aktivitäts Bibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="da311-121">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="da311-122">Geben Sie dem neuen Projekt den Namen "HelloActivity".</span><span class="sxs-lookup"><span data-stu-id="da311-122">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="da311-123">Klicken Sie im HelloActivity-Projekt mit der rechten Maustaste auf Activity1. XAML, und wählen Sie **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="da311-123">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="da311-124">Klicken Sie mit der rechten Maustaste auf das Projekt HelloActivity, und wählen Sie **Hinzufügen** und dann **Klasse** aus.</span><span class="sxs-lookup"><span data-stu-id="da311-124">Right-click the HelloActivity project and select **Add**, and then **Class**.</span></span> <span data-ttu-id="da311-125">Nennen Sie die neue Klasse HelloActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="da311-125">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="da311-126">Fügen Sie der Datei "HelloActivity.cs" die folgenden `using`-Direktiven hinzu.</span><span class="sxs-lookup"><span data-stu-id="da311-126">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="da311-127">Legen Sie fest, dass die neue Klasse von <xref:System.Activities.NativeActivity> erben soll, indem Sie der Klassendeklaration eine Basisklasse hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="da311-127">Make the new class inherit from <xref:System.Activities.NativeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : NativeActivity
    ```

7. <span data-ttu-id="da311-128">Fügen Sie der Klasse die Funktionalität hinzu, indem Sie eine <xref:System.Activities.NativeActivity.Execute%2A>-Methode hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="da311-128">Add functionality to the class by adding an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(NativeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="da311-129">Überschreiben Sie die <xref:System.Activities.NativeActivity.CacheMetadata%2A>-Methode, und rufen Sie die entsprechende Add-Methode auf, um Informationen zu den Variablen, Argumenten, untergeordneten Elementen und Delegaten der benutzerdefinierten Aktivität für die Workflowlaufzeit bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="da311-129">Override the <xref:System.Activities.NativeActivity.CacheMetadata%2A> method and call the appropriate Add method to let the workflow runtime know about the custom activity’s variables, arguments, children, and delegates.</span></span> <span data-ttu-id="da311-130">Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Activities.NativeActivityMetadata>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="da311-130">For more information see the <xref:System.Activities.NativeActivityMetadata> class.</span></span>

9. <span data-ttu-id="da311-131">Verwenden Sie das <xref:System.Activities.NativeActivityContext>-Objekt, um ein Lesezeichen zu planen.</span><span class="sxs-lookup"><span data-stu-id="da311-131">Use the <xref:System.Activities.NativeActivityContext> object to schedule a bookmark.</span></span> <span data-ttu-id="da311-132">Nähere Informationen zum Erstellen, Planen und Fortsetzen eines Lesezeichens finden Sie unter <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A>.</span><span class="sxs-lookup"><span data-stu-id="da311-132">See <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> for details on how to create, schedule, and resume a bookmark.</span></span>

    ```csharp
    protected override void Execute(NativeActivityContext context)
        {
            // Create a Bookmark and wait for it to be resumed.
            context.CreateBookmark(BookmarkName.Get(context),
                new BookmarkCallback(OnResumeBookmark));
        }
    ```
