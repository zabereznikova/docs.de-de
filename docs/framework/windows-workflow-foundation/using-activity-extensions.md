---
title: Verwenden von Aktivitätserweiterungen
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: 32c465ae42a1f0238fab7bba5ea795486db3b562
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-activity-extensions"></a>Verwenden von Aktivitätserweiterungen
Aktivitäten können mit Erweiterungen von Workflowanwendungen interagieren, die es dem Host ermöglichen, weitere Funktionen bereitzustellen, die nicht explizit im Workflow modelliert wurden.  In diesem Thema wird beschrieben, wie eine Erweiterung erstellt und verwendet wird, mit der die Häufigkeit der Ausführung einer Aktivität erfasst werden kann.  
  
### <a name="to-use-an-activity-extension-to-count-executions"></a>So verwenden Sie die Aktivitätserweiterung zum Erfassen der Häufigkeit der Ausführung  
  
1.  Öffnen Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]. Wählen Sie **neue**, **Projekt**. Klicken Sie unter der **Visual C#-** Knoten **Workflow**.  Wählen Sie **Workflowkonsolenanwendung** aus der Liste der Vorlagen. Benennen Sie das Projekt mit `Extensions`. Klicken Sie auf **OK**, um das Projekt zu erstellen.  
  
2.  Hinzufügen einer `using` -Anweisung in der Datei "Program.cs" für die **System.Collections.Generic** Namespace.  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
3.  Erstellen Sie eine neue Klasse mit dem Namen in der Datei "Program.cs" **ExecutionCountExtension**. Der folgende Code erstellt eine workflowerweiterung, die Instanz-IDs verfolgt bei seiner **registrieren** -Methode aufgerufen wird.  
  
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
  
4.  Erstellen Sie eine Aktivität, die **ExecutionCountExtension**. Der folgende Code definiert eine Aktivität, die abgerufen der **ExecutionCountExtension** Objekt aus der Common Language Runtime und ruft seine **registrieren** Methode, wenn die Aktivität ausgeführt wird.  
  
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
  
5.  Implementieren Sie die Aktivität in der **Main** -Methode der Datei "Program.cs". Der folgende Code enthält Methoden, mit denen zwei unterschiedliche Workflows generiert, die Workflows mehrfach ausgeführt und die resultierenden Daten in der Erweiterung angezeigt werden.  
  
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
