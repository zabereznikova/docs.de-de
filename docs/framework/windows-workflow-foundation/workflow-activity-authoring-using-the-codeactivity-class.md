---
title: Erstellen von Workflowaktivitäten mit der CodeActivity-Klasse
ms.date: 03/30/2017
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
ms.openlocfilehash: 714e0971a006db20d002b0f3a486533b1357fba7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293818"
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a><span data-ttu-id="0fba3-102">Erstellen von Workflowaktivitäten mit der CodeActivity-Klasse</span><span class="sxs-lookup"><span data-stu-id="0fba3-102">Workflow Activity Authoring Using the CodeActivity Class</span></span>

<span data-ttu-id="0fba3-103">Aktivitäten, die durch das Erben von <xref:System.Activities.CodeActivity> erstellt werden, können das grundlegende imperative Verhalten implementieren, indem sie die <xref:System.Activities.CodeActivity.Execute%2A>-Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="0fba3-103">Activities created by inheriting from <xref:System.Activities.CodeActivity> can implement basic imperative behavior by overriding the <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

## <a name="using-codeactivitycontext"></a><span data-ttu-id="0fba3-104">Verwenden von CodeActivityContext</span><span class="sxs-lookup"><span data-stu-id="0fba3-104">Using CodeActivityContext</span></span>

 <span data-ttu-id="0fba3-105">Innerhalb der <xref:System.Activities.CodeActivity.Execute%2A>-Methode kann mithilfe von Membern des `context`-Parameters vom Typ <xref:System.Activities.CodeActivityContext> auf Funktionen des Workflows zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="0fba3-105">Features of the workflow runtime can be accessed from within the <xref:System.Activities.CodeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.CodeActivityContext>.</span></span> <span data-ttu-id="0fba3-106">Über <xref:System.Activities.CodeActivityContext> sind unter anderem folgende Funktionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0fba3-106">The features available through <xref:System.Activities.CodeActivityContext> include the following:</span></span>

- <span data-ttu-id="0fba3-107">Abrufen und Festlegen der Werte von Variablen und Argumenten</span><span class="sxs-lookup"><span data-stu-id="0fba3-107">Getting and setting the values of variables and arguments.</span></span>

- <span data-ttu-id="0fba3-108">Benutzerdefinierte Überwachungsfunktionen mit <xref:System.Activities.CodeActivityContext.Track%2A></span><span class="sxs-lookup"><span data-stu-id="0fba3-108">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

- <span data-ttu-id="0fba3-109">Zugreifen auf die Ausführungseigenschaften der Aktivität mithilfe von <xref:System.Activities.CodeActivityContext.GetProperty%2A></span><span class="sxs-lookup"><span data-stu-id="0fba3-109">Access to the activity’s execution properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span></span>

#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a><span data-ttu-id="0fba3-110">So erstellen Sie eine benutzerdefinierte Aktivität, die von CodeActivity erbt</span><span class="sxs-lookup"><span data-stu-id="0fba3-110">To create a custom activity that inherits from CodeActivity</span></span>

1. <span data-ttu-id="0fba3-111">Öffnen Sie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="0fba3-111">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="0fba3-112">Wählen Sie **Datei**, **neu** und dann **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="0fba3-112">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="0fba3-113">Wählen Sie im Fenster **Projekttypen** unter **Visual c#** die Option **Workflow 4,0** aus, und wählen Sie den Knoten **v2010** aus.</span><span class="sxs-lookup"><span data-stu-id="0fba3-113">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="0fba3-114">Wählen Sie im Fenster **Vorlagen** die Option **Aktivitäts Bibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="0fba3-114">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="0fba3-115">Geben Sie dem neuen Projekt den Namen "HelloActivity".</span><span class="sxs-lookup"><span data-stu-id="0fba3-115">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="0fba3-116">Klicken Sie im HelloActivity-Projekt mit der rechten Maustaste auf Activity1. XAML, und wählen Sie **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="0fba3-116">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="0fba3-117">Klicken Sie mit der rechten Maustaste auf das Projekt HelloActivity, und wählen Sie **Hinzufügen** und dann **Klasse** aus.</span><span class="sxs-lookup"><span data-stu-id="0fba3-117">Right-click the HelloActivity project and select **Add** , and then **Class**.</span></span> <span data-ttu-id="0fba3-118">Nennen Sie die neue Klasse HelloActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="0fba3-118">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="0fba3-119">Fügen Sie der Datei "HelloActivity.cs" die folgenden `using`-Direktiven hinzu.</span><span class="sxs-lookup"><span data-stu-id="0fba3-119">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="0fba3-120">Legen Sie fest, dass die neue Klasse von <xref:System.Activities.CodeActivity> erben soll, indem Sie der Klassendeklaration eine Basisklasse hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0fba3-120">Make the new class inherit from <xref:System.Activities.CodeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : CodeActivity
    ```

7. <span data-ttu-id="0fba3-121">Fügen Sie der Klasse die Funktionalität hinzu, indem Sie eine <xref:System.Activities.CodeActivity.Execute%2A>-Methode hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0fba3-121">Add functionality to the class by adding an <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="0fba3-122">Verwenden Sie die <xref:System.Activities.CodeActivityContext>-Instanz, um einen Nachverfolgungsdatensatz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0fba3-122">Use the <xref:System.Activities.CodeActivityContext> to create a tracking record.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));
        context.Track(record);
    }
    ```
