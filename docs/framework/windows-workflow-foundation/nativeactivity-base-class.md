---
title: NativeActivity-Basisklasse
ms.date: 03/30/2017
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
ms.openlocfilehash: d746bb92dab79e7e68075ad003c420e7e37ed683
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637500"
---
# <a name="nativeactivity-base-class"></a><span data-ttu-id="24b3d-102">NativeActivity-Basisklasse</span><span class="sxs-lookup"><span data-stu-id="24b3d-102">NativeActivity Base Class</span></span>

<span data-ttu-id="24b3d-103"><xref:System.Activities.NativeActivity> ist eine abstrakte Klasse mit einem geschützten Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="24b3d-103"><xref:System.Activities.NativeActivity> is an abstract class with a protected constructor.</span></span> <span data-ttu-id="24b3d-104">Wie <xref:System.Activities.CodeActivity> wird auch <xref:System.Activities.NativeActivity> zum Schreiben von imperativem Verhalten durch die Implementierung einer <xref:System.Activities.NativeActivity.Execute%2A>-Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="24b3d-104">Like <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> is used for writing imperative behavior by implementing an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span> <span data-ttu-id="24b3d-105">Im Gegensatz zu <xref:System.Activities.CodeActivity> verfügt <xref:System.Activities.NativeActivity> jedoch über Zugriff auf alle verfügbar gemachten Funktionen der Workflowlaufzeit durch das <xref:System.Activities.NativeActivityContext>-Objekt, das an die <xref:System.Activities.NativeActivity.Execute%2A>-Methode übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="24b3d-105">Unlike <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> has access to all of the exposed features of the workflow runtime through the <xref:System.Activities.NativeActivityContext> object passed to the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

## <a name="using-nativeactivitycontext"></a><span data-ttu-id="24b3d-106">Verwenden von NativeActivityContext</span><span class="sxs-lookup"><span data-stu-id="24b3d-106">Using NativeActivityContext</span></span>
 <span data-ttu-id="24b3d-107">Innerhalb der <xref:System.Activities.NativeActivity.Execute%2A>-Methode kann mithilfe von Membern des `context`-Parameters vom Typ <xref:System.Activities.NativeActivityContext> auf Funktionen des Workflows zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="24b3d-107">Features of the workflow runtime can be accessed from within the <xref:System.Activities.NativeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.NativeActivityContext>.</span></span> <span data-ttu-id="24b3d-108">Über <xref:System.Activities.NativeActivityContext> sind unter anderem folgende Funktionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="24b3d-108">The features available through <xref:System.Activities.NativeActivityContext> include the following:</span></span>

- <span data-ttu-id="24b3d-109">Abrufen und Festlegen von Argumenten und Variablen</span><span class="sxs-lookup"><span data-stu-id="24b3d-109">Getting and setting of arguments and variables.</span></span>

- <span data-ttu-id="24b3d-110">Planen von untergeordneten Aktivitäten mit <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A></span><span class="sxs-lookup"><span data-stu-id="24b3d-110">Scheduling child activities with <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A></span></span>

- <span data-ttu-id="24b3d-111">Abbrechen der Ausführung von Aktivitäten mit <xref:System.Activities.NativeActivityContext.Abort%2A>.</span><span class="sxs-lookup"><span data-stu-id="24b3d-111">Aborting activity execution using <xref:System.Activities.NativeActivityContext.Abort%2A>.</span></span>

- <span data-ttu-id="24b3d-112">Abbrechen der Ausführung untergeordneter Elemente mit <xref:System.Activities.NativeActivityContext.CancelChild%2A> und <xref:System.Activities.NativeActivityContext.CancelChildren%2A></span><span class="sxs-lookup"><span data-stu-id="24b3d-112">Canceling child execution using <xref:System.Activities.NativeActivityContext.CancelChild%2A> and <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.</span></span>

- <span data-ttu-id="24b3d-113">Zugreifen auf Aktivitätslesezeichen mit Methoden wie <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A> und <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A></span><span class="sxs-lookup"><span data-stu-id="24b3d-113">Access to activity bookmarks using such methods as <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A>, and <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.</span></span>

- <span data-ttu-id="24b3d-114">Benutzerdefinierte Überwachungsfunktionen mit <xref:System.Activities.CodeActivityContext.Track%2A></span><span class="sxs-lookup"><span data-stu-id="24b3d-114">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

- <span data-ttu-id="24b3d-115">Zugeifen auf die Ausführungseigenschaften und Werteigenschaften der Aktivität mit <xref:System.Activities.CodeActivityContext.GetProperty%2A> und <xref:System.Activities.NativeActivityContext.GetValue%2A></span><span class="sxs-lookup"><span data-stu-id="24b3d-115">Access to the activity’s execution properties and value properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A> and <xref:System.Activities.NativeActivityContext.GetValue%2A>.</span></span>

- <span data-ttu-id="24b3d-116">Planen von Aktivitätsaktionen und Funktionen mit <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> und <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A></span><span class="sxs-lookup"><span data-stu-id="24b3d-116">Scheduling activity actions and functions using <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> and <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.</span></span>

### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a><span data-ttu-id="24b3d-117">So erstellen Sie eine benutzerdefinierte Aktivität, die von NativeActivity erbt</span><span class="sxs-lookup"><span data-stu-id="24b3d-117">To create a custom activity that inherits from NativeActivity</span></span>

1. <span data-ttu-id="24b3d-118">OpenVisual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="24b3d-118">OpenVisual Studio 2010.</span></span>

2. <span data-ttu-id="24b3d-119">Wählen Sie **Datei**, **neue**, und klicken Sie dann **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="24b3d-119">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="24b3d-120">Wählen Sie **Workflow 4.0** unter **Visual C#-** in die **Projekttypen** , und wählen die **v2010** Knoten.</span><span class="sxs-lookup"><span data-stu-id="24b3d-120">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="24b3d-121">Wählen Sie **Aktivitätsbibliothek** in die **Vorlagen** Fenster.</span><span class="sxs-lookup"><span data-stu-id="24b3d-121">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="24b3d-122">Geben Sie dem neuen Projekt den Namen "HelloActivity".</span><span class="sxs-lookup"><span data-stu-id="24b3d-122">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="24b3d-123">Mit der rechten Maustaste Activity1.xaml im HelloActivity-Projekt, und wählen Sie **löschen**.</span><span class="sxs-lookup"><span data-stu-id="24b3d-123">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="24b3d-124">Maustaste auf das HelloActivity-Projekt, und wählen Sie **hinzufügen**, und klicken Sie dann **Klasse**.</span><span class="sxs-lookup"><span data-stu-id="24b3d-124">Right-click the HelloActivity project and select **Add**, and then **Class**.</span></span> <span data-ttu-id="24b3d-125">Nennen Sie die neue Klasse HelloActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="24b3d-125">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="24b3d-126">Fügen Sie der Datei "HelloActivity.cs" die folgenden `using`-Direktiven hinzu.</span><span class="sxs-lookup"><span data-stu-id="24b3d-126">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="24b3d-127">Legen Sie fest, dass die neue Klasse von <xref:System.Activities.NativeActivity> erben soll, indem Sie der Klassendeklaration eine Basisklasse hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="24b3d-127">Make the new class inherit from <xref:System.Activities.NativeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : NativeActivity
    ```

7. <span data-ttu-id="24b3d-128">Fügen Sie der Klasse die Funktionalität hinzu, indem Sie eine <xref:System.Activities.NativeActivity.Execute%2A>-Methode hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="24b3d-128">Add functionality to the class by adding an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(NativeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="24b3d-129">Überschreiben Sie die <xref:System.Activities.NativeActivity.CacheMetadata%2A>-Methode, und rufen Sie die entsprechende Add-Methode auf, um Informationen zu den Variablen, Argumenten, untergeordneten Elementen und Delegaten der benutzerdefinierten Aktivität für die Workflowlaufzeit bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="24b3d-129">Override the <xref:System.Activities.NativeActivity.CacheMetadata%2A> method and call the appropriate Add method to let the workflow runtime know about the custom activity’s variables, arguments, children, and delegates.</span></span> <span data-ttu-id="24b3d-130">Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Activities.NativeActivityMetadata>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="24b3d-130">For more information see the <xref:System.Activities.NativeActivityMetadata> class.</span></span>

9. <span data-ttu-id="24b3d-131">Verwenden Sie das <xref:System.Activities.NativeActivityContext>-Objekt, um ein Lesezeichen zu planen.</span><span class="sxs-lookup"><span data-stu-id="24b3d-131">Use the <xref:System.Activities.NativeActivityContext> object to schedule a bookmark.</span></span> <span data-ttu-id="24b3d-132">Nähere Informationen zum Erstellen, Planen und Fortsetzen eines Lesezeichens finden Sie unter <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A>.</span><span class="sxs-lookup"><span data-stu-id="24b3d-132">See <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> for details on how to create, schedule, and resume a bookmark.</span></span>

    ```
    protected override void Execute(NativeActivityContext context)
        {
            // Create a Bookmark and wait for it to be resumed.
            context.CreateBookmark(BookmarkName.Get(context),
                new BookmarkCallback(OnResumeBookmark));
        }
    ```
