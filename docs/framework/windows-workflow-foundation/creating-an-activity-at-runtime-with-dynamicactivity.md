---
title: Erstellen einer Aktivität zur Laufzeit mit DynamicActivity
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: ed133e972caa9a3a62ab2ac1310cb1bd666947ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774074"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="0775f-102">Erstellen einer Aktivität zur Laufzeit mit DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="0775f-102">Creating an Activity at Runtime with DynamicActivity</span></span>
<span data-ttu-id="0775f-103"><xref:System.Activities.DynamicActivity> ist eine konkrete, versiegelte Klasse mit einem öffentlichen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="0775f-103"><xref:System.Activities.DynamicActivity> is a concrete, sealed class with a public constructor.</span></span> <span data-ttu-id="0775f-104"><xref:System.Activities.DynamicActivity> kann zur Zusammenstellung von Aktivitätsfunktionen zur Laufzeit mit einem Aktivitäts-DOM verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0775f-104"><xref:System.Activities.DynamicActivity> can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="0775f-105">DynamicActivity-Funktionen</span><span class="sxs-lookup"><span data-stu-id="0775f-105">DynamicActivity Features</span></span>  
 <span data-ttu-id="0775f-106"><xref:System.Activities.DynamicActivity> hat Zugriff auf Ausführungseigenschaften, Argumente und Variablen, jedoch keinen Zugriff auf Laufzeitdienste, wie z. B. die Planung untergeordneter Aktivitäten oder die Nachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="0775f-106"><xref:System.Activities.DynamicActivity> has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="0775f-107">Eigenschaften der obersten Ebene können mit <xref:System.Activities.Argument>-Workflowobjekten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0775f-107">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="0775f-108">In imperativem Code werden diese Argumente mittels CLR-Eigenschaften für einen neuen Typ erstellt.</span><span class="sxs-lookup"><span data-stu-id="0775f-108">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="0775f-109">In XAML werden sie mit dem `x:Class`-Tag und dem `x:Member`-Tag deklariert.</span><span class="sxs-lookup"><span data-stu-id="0775f-109">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="0775f-110">Der Designer-Zugriff für die mit <xref:System.Activities.DynamicActivity> konstruierten Aktivitäten erfolgt über <xref:System.ComponentModel.ICustomTypeDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="0775f-110">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="0775f-111">Im Designer erstellte Aktivitäten können dynamisch mit <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> geladen werden, wie in der folgenden Prozedur veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0775f-111">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="0775f-112">So erstellen Sie zur Laufzeit eine Aktivität mit imperativem Code</span><span class="sxs-lookup"><span data-stu-id="0775f-112">To create an activity at runtime using imperative code</span></span>  
  
1. <span data-ttu-id="0775f-113">OpenVisual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="0775f-113">OpenVisual Studio 2010.</span></span>  
  
2. <span data-ttu-id="0775f-114">Wählen Sie **Datei**, **neue**, **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="0775f-114">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="0775f-115">Wählen Sie **Workflow 4.0** unter **Visual C#-** in die **Projekttypen** , und wählen die **v2010** Knoten.</span><span class="sxs-lookup"><span data-stu-id="0775f-115">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="0775f-116">Wählen Sie **Konsolenanwendung für sequenzielle Workflows** in die **Vorlagen** Fenster.</span><span class="sxs-lookup"><span data-stu-id="0775f-116">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="0775f-117">Geben Sie dem neuen Projekt den Namen DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="0775f-117">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="0775f-118">Mit der rechten Maustaste Workflow1.xaml im HelloActivity-Projekt, und wählen Sie **löschen**.</span><span class="sxs-lookup"><span data-stu-id="0775f-118">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4. <span data-ttu-id="0775f-119">Öffnen Sie die Datei Program.cs.</span><span class="sxs-lookup"><span data-stu-id="0775f-119">Open Program.cs.</span></span> <span data-ttu-id="0775f-120">Fügen Sie am Anfang der Datei die folgende Direktive hinzu.</span><span class="sxs-lookup"><span data-stu-id="0775f-120">Add the following directive to the top of the file.</span></span>  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
5. <span data-ttu-id="0775f-121">Ersetzen Sie den Inhalt der `Main`-Methode durch den folgenden Code, mit dem eine <xref:System.Activities.Statements.Sequence>-Aktivität erstellt wird, die eine einzelne <xref:System.Activities.Statements.WriteLine>-Aktivität enthält. Diese wird der <xref:System.Activities.DynamicActivity.Implementation%2A>-Eigenschaft einer neuen dynamischen Aktivität zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0775f-121">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
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
  
6. <span data-ttu-id="0775f-122">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="0775f-122">Execute the application.</span></span> <span data-ttu-id="0775f-123">Ein Konsolenfenster mit dem Text "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="0775f-123">A console window with the text "Hello World!"</span></span> <span data-ttu-id="0775f-124">wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0775f-124">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="0775f-125">So erstellen Sie zur Laufzeit eine Aktivität mit XAML</span><span class="sxs-lookup"><span data-stu-id="0775f-125">To create an activity at runtime using XAML</span></span>  
  
1. <span data-ttu-id="0775f-126">Öffnen Sie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="0775f-126">Open Visual Studio 2010.</span></span>  
  
2. <span data-ttu-id="0775f-127">Wählen Sie **Datei**, **neue**, **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="0775f-127">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="0775f-128">Wählen Sie **Workflow 4.0** unter **Visual C#-** in die **Projekttypen** , und wählen die **v2010** Knoten.</span><span class="sxs-lookup"><span data-stu-id="0775f-128">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="0775f-129">Wählen Sie **Konsolenanwendung für Workflows** in die **Vorlagen** Fenster.</span><span class="sxs-lookup"><span data-stu-id="0775f-129">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="0775f-130">Geben Sie dem neuen Projekt den Namen DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="0775f-130">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="0775f-131">Öffnen Sie Workflow1.xaml im HelloActivity-Projekt.</span><span class="sxs-lookup"><span data-stu-id="0775f-131">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="0775f-132">Klicken Sie auf die **Argumente** am unteren Rand des Designers die Option.</span><span class="sxs-lookup"><span data-stu-id="0775f-132">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="0775f-133">Erstellen Sie ein neues `In`-Argument mit dem Namen `TextToWrite` und dem Typ `String`.</span><span class="sxs-lookup"><span data-stu-id="0775f-133">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4. <span data-ttu-id="0775f-134">Ziehen Sie eine **WriteLine** Aktivität aus der **primitive** Abschnitt der Toolbox auf die Designeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="0775f-134">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="0775f-135">Weisen Sie den Wert `TextToWrite` auf die **Text** -Eigenschaft der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0775f-135">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5. <span data-ttu-id="0775f-136">Öffnen Sie die Datei Program.cs.</span><span class="sxs-lookup"><span data-stu-id="0775f-136">Open Program.cs.</span></span> <span data-ttu-id="0775f-137">Fügen Sie am Anfang der Datei die folgende Direktive hinzu.</span><span class="sxs-lookup"><span data-stu-id="0775f-137">Add the following directive to the top of the file.</span></span>  
  
    ```  
    using System.Activities.XamlIntegration;  
    ```  
  
6. <span data-ttu-id="0775f-138">Ersetzen Sie den Inhalt der `Main`-Methode durch folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="0775f-138">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7. <span data-ttu-id="0775f-139">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="0775f-139">Execute the application.</span></span> <span data-ttu-id="0775f-140">Ein Konsolenfenster mit dem Text "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="0775f-140">A console window with the text "Hello World!"</span></span> <span data-ttu-id="0775f-141">wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0775f-141">appears.</span></span>  
  
8. <span data-ttu-id="0775f-142">Mit der rechten Maustaste in der Datei "Workflow1.xaml", in der **Projektmappen-Explorer** , und wählen Sie **Ansichtscode**.</span><span class="sxs-lookup"><span data-stu-id="0775f-142">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="0775f-143">Beachten Sie, dass die Aktivitätsklasse mit `x:Class` und die Eigenschaft mit `x:Property` erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0775f-143">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0775f-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0775f-144">See also</span></span>

- [<span data-ttu-id="0775f-145">Erstellen von Workflows, Aktivitäten und Ausdrücken mit imperativem Code</span><span class="sxs-lookup"><span data-stu-id="0775f-145">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](authoring-workflows-activities-and-expressions-using-imperative-code.md)
