---
title: Anhalten und Fortsetzen eines Workflows
ms.date: 03/30/2017
ms.assetid: 11f38339-79c7-4295-b610-24a7223bbf6d
ms.openlocfilehash: aa0431b18f6d0e4b96d7494ec2e65acd355992c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61860957"
---
# <a name="pausing-and-resuming-a-workflow"></a><span data-ttu-id="4df5e-102">Anhalten und Fortsetzen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="4df5e-102">Pausing and Resuming a Workflow</span></span>
<span data-ttu-id="4df5e-103">Workflows werden in Abhängigkeit von Lesezeichen und Blockieraktivitäten wie <xref:System.Activities.Statements.Delay> angehalten und fortgesetzt, können jedoch auch durch Persistenz explizit angehalten, entladen und wieder aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="4df5e-103">Workflows will pause and resume in response to bookmarks and blocking activities such as <xref:System.Activities.Statements.Delay>, but a workflow can also be explicitly paused, unloaded, and resumed by using persistence.</span></span>  
  
## <a name="pausing-a-workflow"></a><span data-ttu-id="4df5e-104">Anhalten eines Workflows</span><span class="sxs-lookup"><span data-stu-id="4df5e-104">Pausing a Workflow</span></span>  
 <span data-ttu-id="4df5e-105">Verwenden Sie <xref:System.Activities.WorkflowApplication.Unload%2A>, um einen Workflow anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="4df5e-105">To pause a workflow, use <xref:System.Activities.WorkflowApplication.Unload%2A>.</span></span>  <span data-ttu-id="4df5e-106">Mit dieser Methode wird das Beibehalten und Entladen des Workflows angefordert, und eine <xref:System.TimeoutException> wird ausgelöst, wenn der Workflow nicht innerhalb von 30 Sekunden entladen wird.</span><span class="sxs-lookup"><span data-stu-id="4df5e-106">This method requests that the workflow persist and unload, and will throw a <xref:System.TimeoutException> if the workflow does not unload in 30 seconds.</span></span>  
  
```csharp  
try  
{  
    // attempt to unload will fail if the workflow is idle within a NoPersistZone  
    application.Unload(TimeSpan.FromSeconds(5));  
}  
catch (TimeoutException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
## <a name="resuming-a-workflow"></a><span data-ttu-id="4df5e-107">Wiederaufnehmen von Workflows</span><span class="sxs-lookup"><span data-stu-id="4df5e-107">Resuming a Workflow</span></span>  
 <span data-ttu-id="4df5e-108">Verwenden Sie <xref:System.Activities.WorkflowApplication.Load%2A>, um einen Workflow wiederaufzunehmen, der angehalten und entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="4df5e-108">To resume a previously paused and unloaded workflow, use <xref:System.Activities.WorkflowApplication.Load%2A>.</span></span> <span data-ttu-id="4df5e-109">Diese Methode lädt einen Workflow aus einem Persistenzspeicher in den Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="4df5e-109">This method loads a workflow from a persistence store into memory.</span></span>  
  
```csharp  
WorkflowApplication application = new WorkflowApplication(activity);  
application.InstanceStore = instanceStore;  
application.Load(id);  
```  
  
## <a name="example"></a><span data-ttu-id="4df5e-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4df5e-110">Example</span></span>  
 <span data-ttu-id="4df5e-111">Im folgenden Codebeispiel wird veranschaulicht, wie ein Workflow mithilfe der Persistenz angehalten und fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4df5e-111">The following code sample demonstrates how to pause and resume a workflow by using persistence.</span></span>  
  
```csharp  
static string bkName = "bkName";  
static void Main(string[] args)   
{  
    StartAndUnloadInstance();  
}  
  
static void StartAndUnloadInstance()   
{  
    AutoResetEvent waitHandler = new AutoResetEvent(false);  
    WorkflowApplication wfApp = new WorkflowApplication(GetDelayedWF());  
    SqlWorkflowInstanceStore instanceStore = SetupSqlpersistenceStore();  
    wfApp.InstanceStore = instanceStore;  
    wfApp.Extensions.Add(SetupMyFileTrackingParticipant);  
    wfApp.PersistableIdle = (e) => {          ///persists application state and remove it from memory   
    return PersistableIdleAction.Unload;  
    };  
    wfApp.Unloaded = (e) => {  
        waitHandler.Set();  
    };  
    Guid id = wfApp.Id;  
    wfApp.Run();  
    waitHandler.WaitOne();  
    LoadAndCompleteInstance(id);  
}  
  
static void LoadAndCompleteInstance(Guid id)   
{            
    Console.WriteLine("Press <enter> to load the persisted workflow");  
    Console.ReadLine();  
    AutoResetEvent waitHandler = new AutoResetEvent(false);  
    WorkflowApplication wfApp = new WorkflowApplication(GetDelayedWF());  
    wfApp.InstanceStore =  
        new SqlWorkflowInstanceStore(ConfigurationManager.AppSettings["SqlWF4PersistenceConnectionString"].ToString());  
    wfApp.Completed = (workflowApplicationCompletedEventArgs) => {  
        Console.WriteLine("\nWorkflowApplication has Completed in the {0} state.",  
            workflowApplicationCompletedEventArgs.CompletionState);  
    };  
    wfApp.Unloaded = (workflowApplicationEventArgs) => {  
        Console.WriteLine("WorkflowApplication has Unloaded\n");  
        waitHandler.Set();  
    };  
    wfApp.Load(id);  
    wfApp.Run();  
    waitHandler.WaitOne();  
}  
  
public static Activity GetDelayedWF()   
{  
    return new Sequence {  
        Activities ={  
            new WriteLine{Text="Workflow Started"},  
            new Delay{Duration=TimeSpan.FromSeconds(10)},  
            new WriteLine{Text="Workflow Ended"}  
        }  
    };  
}  
  
private static SqlWorkflowInstanceStore SetupSqlpersistenceStore()   
{   
     string connectionString = ConfigurationManager.AppSettings["SqlWF4PersistenceConnectionString"].ToString();  
    SqlWorkflowInstanceStore sqlWFInstanceStore = new SqlWorkflowInstanceStore(connectionString);  
    sqlWFInstanceStore.InstanceCompletionAction = InstanceCompletionAction.DeleteAll;  
    InstanceHandle handle = sqlWFInstanceStore.CreateInstanceHandle();  
    InstanceView view = sqlWFInstanceStore.Execute(handle, new CreateWorkflowOwnerCommand(), TimeSpan.FromSeconds(5));  
    handle.Free();  
    sqlWFInstanceStore.DefaultInstanceOwner = view.InstanceOwner;  
    return sqlWFInstanceStore;  
}  
```
