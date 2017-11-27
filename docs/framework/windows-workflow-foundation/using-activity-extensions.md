---
title: "Verwenden von Aktivitätserweiterungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7ff4f441df437dc5785b6df77c16923a1a1c9906
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-activity-extensions"></a><span data-ttu-id="3e3d8-102">Verwenden von Aktivitätserweiterungen</span><span class="sxs-lookup"><span data-stu-id="3e3d8-102">Using Activity Extensions</span></span>
<span data-ttu-id="3e3d8-103">Aktivitäten können mit Erweiterungen von Workflowanwendungen interagieren, die es dem Host ermöglichen, weitere Funktionen bereitzustellen, die nicht explizit im Workflow modelliert wurden.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-103">Activities can interact with workflow application extensions that allow the host to provide additional functionality that is not explicitly modeled in the workflow.</span></span>  <span data-ttu-id="3e3d8-104">In diesem Thema wird beschrieben, wie eine Erweiterung erstellt und verwendet wird, mit der die Häufigkeit der Ausführung einer Aktivität erfasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-104">This topic describes how to create and use an extension to count the number of times the activity executes.</span></span>  
  
### <a name="to-use-an-activity-extension-to-count-executions"></a><span data-ttu-id="3e3d8-105">So verwenden Sie die Aktivitätserweiterung zum Erfassen der Häufigkeit der Ausführung</span><span class="sxs-lookup"><span data-stu-id="3e3d8-105">To use an activity extension to count executions</span></span>  
  
1.  <span data-ttu-id="3e3d8-106">Öffnen Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e3d8-106">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span> <span data-ttu-id="3e3d8-107">Wählen Sie **neue**, **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-107">Select **New**, **Project**.</span></span> <span data-ttu-id="3e3d8-108">Klicken Sie unter der **Visual C#-** Knoten **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-108">Under the **Visual C#** node, select **Workflow**.</span></span>  <span data-ttu-id="3e3d8-109">Wählen Sie **Workflowkonsolenanwendung** aus der Liste der Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-109">Select **Workflow Console Application** from the list of templates.</span></span> <span data-ttu-id="3e3d8-110">Benennen Sie das Projekt mit `Extensions`.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-110">Name the project `Extensions`.</span></span> <span data-ttu-id="3e3d8-111">Klicken Sie auf **OK** zum Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-111">Click **OK** to create the project.</span></span>  
  
2.  <span data-ttu-id="3e3d8-112">Hinzufügen einer `using` -Anweisung in der Datei "Program.cs" für die **System.Collections.Generic** Namespace.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-112">Add a `using` statement in the Program.cs file for the **System.Collections.Generic** namespace.</span></span>  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
3.  <span data-ttu-id="3e3d8-113">Erstellen Sie eine neue Klasse mit dem Namen in der Datei "Program.cs" **ExecutionCountExtension**.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-113">In the Program.cs file, create a new class named **ExecutionCountExtension**.</span></span> <span data-ttu-id="3e3d8-114">Der folgende Code erstellt eine workflowerweiterung, die Instanz-IDs verfolgt bei seiner **registrieren** -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-114">The following code creates a workflow extension that tracks instance IDs when its **Register** method is called.</span></span>  
  
    ```  
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
  
4.  <span data-ttu-id="3e3d8-115">Erstellen Sie eine Aktivität, die **ExecutionCountExtension**.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-115">Create an activity that consumes the **ExecutionCountExtension**.</span></span> <span data-ttu-id="3e3d8-116">Der folgende Code definiert eine Aktivität, die abgerufen der **ExecutionCountExtension** Objekt aus der Common Language Runtime und ruft seine **registrieren** Methode, wenn die Aktivität ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-116">The following code defines an activity that retrieves the **ExecutionCountExtension** object from the runtime and calls its **Register** method when the activity executes.</span></span>  
  
    ```  
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
  
5.  <span data-ttu-id="3e3d8-117">Implementieren Sie die Aktivität in der **Main** -Methode der Datei "Program.cs".</span><span class="sxs-lookup"><span data-stu-id="3e3d8-117">Implement the activity in the **Main** method of the program.cs file.</span></span> <span data-ttu-id="3e3d8-118">Der folgende Code enthält Methoden, mit denen zwei unterschiedliche Workflows generiert, die Workflows mehrfach ausgeführt und die resultierenden Daten in der Erweiterung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3e3d8-118">The following code contains methods to generate two different workflows, execute each workflow several times, and display the resulting data that is contained in the extension.</span></span>  
  
    ```  
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
