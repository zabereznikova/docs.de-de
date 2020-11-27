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
# <a name="using-activity-extensions"></a>Verwenden von Aktivitätserweiterungen

Aktivitäten können mit Erweiterungen von Workflowanwendungen interagieren, die es dem Host ermöglichen, weitere Funktionen bereitzustellen, die nicht explizit im Workflow modelliert wurden.  In diesem Thema wird beschrieben, wie eine Erweiterung erstellt und verwendet wird, mit der die Häufigkeit der Ausführung einer Aktivität erfasst werden kann.

### <a name="to-use-an-activity-extension-to-count-executions"></a>So verwenden Sie die Aktivitätserweiterung zum Erfassen der Häufigkeit der Ausführung

1. Öffnen Sie Visual Studio 2010. Wählen Sie **neu**, **Projekt** aus. Wählen Sie unter dem Knoten **Visual c#** die Option **Workflow** aus.  Wählen Sie in der Liste der Vorlagen die Option **Konsolenanwendung für Workflows** aus. Benennen Sie das Projekt mit `Extensions`. Klicken Sie auf **OK**, um das Projekt zu erstellen.

2. Fügen Sie `using` in der Datei Program.cs eine-Anweisung für den **System. Collections. Generic** -Namespace hinzu.

    ```csharp
    using System.Collections.Generic;
    ```

3. Erstellen Sie in der Datei Program.cs eine neue Klasse mit dem Namen " **executionzähltextension**". Mit dem folgenden Code wird eine Workflow Erweiterung erstellt, die Instanz-IDs nachverfolgt, wenn Ihre **Register** -Methode aufgerufen wird.

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

4. Erstellen Sie eine Aktivität, die die **executionzähltextension** verwendet. Der folgende Code definiert eine Aktivität, die das **executionzähltextension** -Objekt von der Laufzeit abruft und seine **Register** -Methode aufruft, wenn die Aktivität ausgeführt wird.

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

5. Implementieren Sie die-Aktivität in der **Main** -Methode der Program.cs-Datei. Der folgende Code enthält Methoden, mit denen zwei unterschiedliche Workflows generiert, die Workflows mehrfach ausgeführt und die resultierenden Daten in der Erweiterung angezeigt werden.

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
