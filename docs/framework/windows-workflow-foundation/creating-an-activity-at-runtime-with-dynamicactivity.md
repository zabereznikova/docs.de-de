---
title: Erstellen einer Aktivität zur Laufzeit mit DynamicActivity
description: DynamicActivity ist eine konkrete, versiegelte Klasse mit einem öffentlichen Konstruktor. Verwenden Sie die-Klasse, um Aktivitäts Funktionen zur Laufzeit mit einem Aktivitäts-Dom zusammenzustellen.
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: 17ee14be7df4801018c7afd2e91f1fb07c34e8e1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421539"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="3c187-104">Erstellen einer Aktivität zur Laufzeit mit DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="3c187-104">Creating an Activity at Runtime with DynamicActivity</span></span>
<span data-ttu-id="3c187-105"><xref:System.Activities.DynamicActivity> ist eine konkrete, versiegelte Klasse mit einem öffentlichen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="3c187-105"><xref:System.Activities.DynamicActivity> is a concrete, sealed class with a public constructor.</span></span> <span data-ttu-id="3c187-106"><xref:System.Activities.DynamicActivity> kann zur Zusammenstellung von Aktivitätsfunktionen zur Laufzeit mit einem Aktivitäts-DOM verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3c187-106"><xref:System.Activities.DynamicActivity> can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="3c187-107">DynamicActivity-Funktionen</span><span class="sxs-lookup"><span data-stu-id="3c187-107">DynamicActivity Features</span></span>  
 <span data-ttu-id="3c187-108"><xref:System.Activities.DynamicActivity> hat Zugriff auf Ausführungseigenschaften, Argumente und Variablen, jedoch keinen Zugriff auf Laufzeitdienste, wie z. B. die Planung untergeordneter Aktivitäten oder die Nachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="3c187-108"><xref:System.Activities.DynamicActivity> has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="3c187-109">Eigenschaften der obersten Ebene können mit <xref:System.Activities.Argument>-Workflowobjekten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3c187-109">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="3c187-110">In imperativem Code werden diese Argumente mittels CLR-Eigenschaften für einen neuen Typ erstellt.</span><span class="sxs-lookup"><span data-stu-id="3c187-110">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="3c187-111">In XAML werden sie mit dem `x:Class`-Tag und dem `x:Member`-Tag deklariert.</span><span class="sxs-lookup"><span data-stu-id="3c187-111">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="3c187-112">Der Designer-Zugriff für die mit <xref:System.Activities.DynamicActivity> konstruierten Aktivitäten erfolgt über <xref:System.ComponentModel.ICustomTypeDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="3c187-112">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="3c187-113">Im Designer erstellte Aktivitäten können dynamisch mit <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> geladen werden, wie in der folgenden Prozedur veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3c187-113">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="3c187-114">So erstellen Sie zur Laufzeit eine Aktivität mit imperativem Code</span><span class="sxs-lookup"><span data-stu-id="3c187-114">To create an activity at runtime using imperative code</span></span>  
  
1. <span data-ttu-id="3c187-115">Openvisual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="3c187-115">OpenVisual Studio 2010.</span></span>  
  
2. <span data-ttu-id="3c187-116">Wählen Sie **Datei**, **neu**und **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="3c187-116">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="3c187-117">Wählen Sie im Fenster **Projekttypen** unter **Visual c#** die Option **Workflow 4,0** aus, und wählen Sie den Knoten **v2010** aus.</span><span class="sxs-lookup"><span data-stu-id="3c187-117">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="3c187-118">Wählen Sie im Fenster **Vorlagen** die Option **Konsolenanwendung für sequenzielle Workflows** aus.</span><span class="sxs-lookup"><span data-stu-id="3c187-118">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="3c187-119">Geben Sie dem neuen Projekt den Namen DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="3c187-119">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="3c187-120">Klicken Sie im HelloActivity-Projekt mit der rechten Maustaste auf Workflow1. XAML, und wählen Sie **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="3c187-120">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4. <span data-ttu-id="3c187-121">Öffnen Sie die Datei Program.cs.</span><span class="sxs-lookup"><span data-stu-id="3c187-121">Open Program.cs.</span></span> <span data-ttu-id="3c187-122">Fügen Sie am Anfang der Datei die folgende Direktive hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c187-122">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
5. <span data-ttu-id="3c187-123">Ersetzen Sie den Inhalt der `Main`-Methode durch den folgenden Code, mit dem eine <xref:System.Activities.Statements.Sequence>-Aktivität erstellt wird, die eine einzelne <xref:System.Activities.Statements.WriteLine>-Aktivität enthält. Diese wird der <xref:System.Activities.DynamicActivity.Implementation%2A>-Eigenschaft einer neuen dynamischen Aktivität zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3c187-123">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6. <span data-ttu-id="3c187-124">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="3c187-124">Execute the application.</span></span> <span data-ttu-id="3c187-125">Ein Konsolenfenster mit dem Text "Hallo Welt!"</span><span class="sxs-lookup"><span data-stu-id="3c187-125">A console window with the text "Hello World!"</span></span> <span data-ttu-id="3c187-126">anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3c187-126">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="3c187-127">So erstellen Sie zur Laufzeit eine Aktivität mit XAML</span><span class="sxs-lookup"><span data-stu-id="3c187-127">To create an activity at runtime using XAML</span></span>  
  
1. <span data-ttu-id="3c187-128">Öffnen Sie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="3c187-128">Open Visual Studio 2010.</span></span>  
  
2. <span data-ttu-id="3c187-129">Wählen Sie **Datei**, **neu**und **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="3c187-129">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="3c187-130">Wählen Sie im Fenster **Projekttypen** unter **Visual c#** die Option **Workflow 4,0** aus, und wählen Sie den Knoten **v2010** aus.</span><span class="sxs-lookup"><span data-stu-id="3c187-130">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="3c187-131">Wählen Sie im Fenster **Vorlagen** die Option **Konsolenanwendung für Workflows** aus.</span><span class="sxs-lookup"><span data-stu-id="3c187-131">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="3c187-132">Geben Sie dem neuen Projekt den Namen DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="3c187-132">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="3c187-133">Öffnen Sie Workflow1.xaml im HelloActivity-Projekt.</span><span class="sxs-lookup"><span data-stu-id="3c187-133">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="3c187-134">Klicken Sie unten im Designer auf die Option **Argumente** .</span><span class="sxs-lookup"><span data-stu-id="3c187-134">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="3c187-135">Erstellen Sie ein neues `In`-Argument mit dem Namen `TextToWrite` und dem Typ `String`.</span><span class="sxs-lookup"><span data-stu-id="3c187-135">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4. <span data-ttu-id="3c187-136">Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der Toolbox auf die Designer Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="3c187-136">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="3c187-137">Weisen Sie den Wert der `TextToWrite` Eigenschaft **Text** der Aktivität zu.</span><span class="sxs-lookup"><span data-stu-id="3c187-137">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5. <span data-ttu-id="3c187-138">Öffnen Sie die Datei Program.cs.</span><span class="sxs-lookup"><span data-stu-id="3c187-138">Open Program.cs.</span></span> <span data-ttu-id="3c187-139">Fügen Sie am Anfang der Datei die folgende Direktive hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c187-139">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Activities.XamlIntegration;  
    ```  
  
6. <span data-ttu-id="3c187-140">Ersetzen Sie den Inhalt der `Main`-Methode durch folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="3c187-140">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```csharp  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7. <span data-ttu-id="3c187-141">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="3c187-141">Execute the application.</span></span> <span data-ttu-id="3c187-142">Ein Konsolenfenster mit dem Text "Hallo Welt!"</span><span class="sxs-lookup"><span data-stu-id="3c187-142">A console window with the text "Hello World!"</span></span> <span data-ttu-id="3c187-143"> wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c187-143">appears.</span></span>  
  
8. <span data-ttu-id="3c187-144">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei Workflow1. XAML, und wählen Sie **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="3c187-144">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="3c187-145">Beachten Sie, dass die Aktivitätsklasse mit `x:Class` und die Eigenschaft mit `x:Property` erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3c187-145">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c187-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c187-146">See also</span></span>

- [<span data-ttu-id="3c187-147">Erstellen von Workflows, Aktivitäten und Ausdrücken mit imperativem Code</span><span class="sxs-lookup"><span data-stu-id="3c187-147">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](authoring-workflows-activities-and-expressions-using-imperative-code.md)
