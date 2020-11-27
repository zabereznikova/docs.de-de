---
title: Verwenden von Aktivitätserweiterungen
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: 3a9cabda9fe92b2ea4e708da8f853f3029328775
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293285"
---
# <a name="using-activity-extensions"></a><span data-ttu-id="f157e-102">Verwenden von Aktivitätserweiterungen</span><span class="sxs-lookup"><span data-stu-id="f157e-102">Using Activity Extensions</span></span>

<span data-ttu-id="f157e-103">Aktivitäten können mit Erweiterungen von Workflowanwendungen interagieren, die es dem Host ermöglichen, weitere Funktionen bereitzustellen, die nicht explizit im Workflow modelliert wurden.</span><span class="sxs-lookup"><span data-stu-id="f157e-103">Activities can interact with workflow application extensions that allow the host to provide additional functionality that is not explicitly modeled in the workflow.</span></span>  <span data-ttu-id="f157e-104">In diesem Thema wird beschrieben, wie eine Erweiterung erstellt und verwendet wird, mit der die Häufigkeit der Ausführung einer Aktivität erfasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="f157e-104">This topic describes how to create and use an extension to count the number of times the activity executes.</span></span>

### <a name="to-use-an-activity-extension-to-count-executions"></a><span data-ttu-id="f157e-105">So verwenden Sie die Aktivitätserweiterung zum Erfassen der Häufigkeit der Ausführung</span><span class="sxs-lookup"><span data-stu-id="f157e-105">To use an activity extension to count executions</span></span>

1. <span data-ttu-id="f157e-106">Öffnen Sie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="f157e-106">Open Visual Studio 2010.</span></span> <span data-ttu-id="f157e-107">Wählen Sie **neu**, **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="f157e-107">Select **New**, **Project**.</span></span> <span data-ttu-id="f157e-108">Wählen Sie unter dem Knoten **Visual c#** die Option **Workflow** aus.</span><span class="sxs-lookup"><span data-stu-id="f157e-108">Under the **Visual C#** node, select **Workflow**.</span></span>  <span data-ttu-id="f157e-109">Wählen Sie in der Liste der Vorlagen die Option **Konsolenanwendung für Workflows** aus.</span><span class="sxs-lookup"><span data-stu-id="f157e-109">Select **Workflow Console Application** from the list of templates.</span></span> <span data-ttu-id="f157e-110">Benennen Sie das Projekt mit `Extensions`.</span><span class="sxs-lookup"><span data-stu-id="f157e-110">Name the project `Extensions`.</span></span> <span data-ttu-id="f157e-111">Klicken Sie auf **OK**, um das Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f157e-111">Click **OK** to create the project.</span></span>

2. <span data-ttu-id="f157e-112">Fügen Sie `using` in der Datei Program.cs eine-Anweisung für den **System. Collections. Generic** -Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="f157e-112">Add a `using` statement in the Program.cs file for the **System.Collections.Generic** namespace.</span></span>

    ```csharp
    using System.Collections.Generic;
    ```

3. <span data-ttu-id="f157e-113">Erstellen Sie in der Datei Program.cs eine neue Klasse mit dem Namen " **executionzähltextension**".</span><span class="sxs-lookup"><span data-stu-id="f157e-113">In the Program.cs file, create a new class named **ExecutionCountExtension**.</span></span> <span data-ttu-id="f157e-114">Mit dem folgenden Code wird eine Workflow Erweiterung erstellt, die Instanz-IDs nachverfolgt, wenn Ihre **Register** -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f157e-114">The following code creates a workflow extension that tracks instance IDs when its **Register** method is called.</span></span>

    ```csharp
    // This extension collects a list of workflow Ids
    public class ExecutionCountExtension
    {
        IList<Guid> instances = new List<Guid>();

        public int ExecutionCount
        {
            get
            {
                return this.instances.Count;
            }
        }

        public IEnumerable<Guid> InstanceIds
        {
            get
            {
                return this.instances;
            }
        }

        public void Register(Guid activityInstanceId)
        {
            if (!this.instances.Contains<Guid>(activityInstanceId))
            {
                instances.Add(activityInstanceId);
            }
        }
    }
    ```

4. <span data-ttu-id="f157e-115">Erstellen Sie eine Aktivität, die die **executionzähltextension** verwendet.</span><span class="sxs-lookup"><span data-stu-id="f157e-115">Create an activity that consumes the **ExecutionCountExtension**.</span></span> <span data-ttu-id="f157e-116">Der folgende Code definiert eine Aktivität, die das **executionzähltextension** -Objekt von der Laufzeit abruft und seine **Register** -Methode aufruft, wenn die Aktivität ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f157e-116">The following code defines an activity that retrieves the **ExecutionCountExtension** object from the runtime and calls its **Register** method when the activity executes.</span></span>

    ```csharp
    // Activity that consumes an extension provided by the host. If the extension is available
    // in the context, it will invoke (in this case, registers the Id of the executing workflow)
    public class MyActivity: CodeActivity
    {
        protected override void Execute(CodeActivityContext context)
        {
            ExecutionCountExtension ext = context.GetExtension<ExecutionCountExtension>();
            if (ext != null)
            {
                ext.Register(context.WorkflowInstanceId);
            }

        }
    }
    ```

5. <span data-ttu-id="f157e-117">Implementieren Sie die-Aktivität in der **Main** -Methode der Program.cs-Datei.</span><span class="sxs-lookup"><span data-stu-id="f157e-117">Implement the activity in the **Main** method of the program.cs file.</span></span> <span data-ttu-id="f157e-118">Der folgende Code enthält Methoden, mit denen zwei unterschiedliche Workflows generiert, die Workflows mehrfach ausgeführt und die resultierenden Daten in der Erweiterung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f157e-118">The following code contains methods to generate two different workflows, execute each workflow several times, and display the resulting data that is contained in the extension.</span></span>

    ```csharp
    class Program
    {
        // Creates a workflow that uses the activity that consumes the extension
        static Activity CreateWorkflow1()
        {
            return new Sequence
            {
                Activities =
                {
                    new MyActivity()
                }
            };
        }

        // Creates a workflow that uses two instances of the activity that consumes the extension
        static Activity CreateWorkflow2()
        {
            return new Sequence
            {
                Activities =
                {
                    new MyActivity(),
                    new MyActivity()
                }
            };
        }

        static void Main(string[] args)
        {
            // create the extension
            ExecutionCountExtension executionCountExt = new ExecutionCountExtension();

            // configure the first invoker and execute 3 times
            WorkflowInvoker invoker = new WorkflowInvoker(CreateWorkflow1());
            invoker.Extensions.Add(executionCountExt);
            invoker.Invoke();
            invoker.Invoke();
            invoker.Invoke();

            // configure the second invoker and execute 2 times
            WorkflowInvoker invoker2 = new WorkflowInvoker(CreateWorkflow2());
            invoker2.Extensions.Add(executionCountExt);
            invoker2.Invoke();
            invoker2.Invoke();

            // show the data in the extension
            Console.WriteLine("Executed {0} times", executionCountExt.ExecutionCount);
            executionCountExt.InstanceIds.ToList().ForEach(i => Console.WriteLine("...{0}", i));
        }
    }
    ```
