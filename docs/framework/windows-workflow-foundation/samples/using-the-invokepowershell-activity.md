---
title: "Verwenden der InvokePowerShell-Aktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 956251a0-31ca-4183-bf76-d277c08585df
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5ea3106f87dae64204ea0c02a1388ed8893c858b
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-invokepowershell-activity"></a><span data-ttu-id="fc32f-102">Verwenden der InvokePowerShell-Aktivität</span><span class="sxs-lookup"><span data-stu-id="fc32f-102">Using the InvokePowerShell Activity</span></span>
<span data-ttu-id="fc32f-103">Im InvokePowerShell-Beispiel wird veranschaulicht, wie Windows PowerShell-Befehle mit der `InvokePowerShell`-Aktivität aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fc32f-103">The InvokePowerShell sample demonstrates how to invoke Windows PowerShell commands using the `InvokePowerShell` activity.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="fc32f-104">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="fc32f-104">Demonstrates</span></span>  
  
-   <span data-ttu-id="fc32f-105">Einfache Innovation von Windows PowerShell-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-105">Simple innovation of Windows PowerShell commands.</span></span>  
  
-   <span data-ttu-id="fc32f-106">Rufen Sie Werte aus der Windows PowerShell-Ausgabepipeline ab, und speichern Sie diese in Workflowvariablen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-106">Retrieve values from the Windows PowerShell output pipeline and store them in workflow variables.</span></span>  
  
-   <span data-ttu-id="fc32f-107">Übergeben Sie Daten an Windows PowerShell als Eingabepipeline für einen Ausführungsbefehl.</span><span class="sxs-lookup"><span data-stu-id="fc32f-107">Pass data into windows PowerShell as input pipeline for an executing command.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fc32f-108">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="fc32f-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fc32f-109">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fc32f-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fc32f-110">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fc32f-111">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fc32f-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## <a name="discussion"></a><span data-ttu-id="fc32f-112">Diskussion</span><span class="sxs-lookup"><span data-stu-id="fc32f-112">Discussion</span></span>  
 <span data-ttu-id="fc32f-113">Dieses Beispiel enthält die folgenden drei Projekte.</span><span class="sxs-lookup"><span data-stu-id="fc32f-113">This sample contains the following three projects.</span></span>  
  
|<span data-ttu-id="fc32f-114">Projektname</span><span class="sxs-lookup"><span data-stu-id="fc32f-114">Project Name</span></span>|<span data-ttu-id="fc32f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc32f-115">Description</span></span>|<span data-ttu-id="fc32f-116">Hauptdateien</span><span class="sxs-lookup"><span data-stu-id="fc32f-116">Main Files</span></span>|  
|------------------|-----------------|----------------|  
|<span data-ttu-id="fc32f-117">CodedClient</span><span class="sxs-lookup"><span data-stu-id="fc32f-117">CodedClient</span></span>|<span data-ttu-id="fc32f-118">Eine Beispielclientanwendung, die die PowerShell-Aktivität verwendet.</span><span class="sxs-lookup"><span data-stu-id="fc32f-118">A sample client application that uses the PowerShell activity.</span></span>|<span data-ttu-id="fc32f-119">-   **Datei "Program.cs"**: erstellt programmgesteuert einen sequenzbasierten Workflow, der die InvokePowerShell-Aktivität aufruft.</span><span class="sxs-lookup"><span data-stu-id="fc32f-119">-   **Program.cs**: Programmatically creates a sequence-based workflow that calls the InvokePowerShell activity.</span></span>|  
|<span data-ttu-id="fc32f-120">DesignerClient</span><span class="sxs-lookup"><span data-stu-id="fc32f-120">DesignerClient</span></span>|<span data-ttu-id="fc32f-121">Ein Satz benutzerdefinierter Aktivitäten, die die benutzerdefinierte Aktivität `InvokePowerShell` und weitere benutzerdefinierte Aktivitäten sowie einen Workflow, der sie verwendet, enthalten.</span><span class="sxs-lookup"><span data-stu-id="fc32f-121">A set of custom activities that contain the `InvokePowerShell` custom activity and other miscellaneous custom activities, and a workflow that uses them.</span></span>|<ul><li><span data-ttu-id="fc32f-122">Aktivitäten:</span><span class="sxs-lookup"><span data-stu-id="fc32f-122">Activities:</span></span><br /><br /> <ul><li><span data-ttu-id="fc32f-123">**PrintCollection.cs**: eine hilfsaktivität, die alle Elemente in einer Auflistung in der Konsole ausgibt.</span><span class="sxs-lookup"><span data-stu-id="fc32f-123">**PrintCollection.cs**: A helper activity that prints all the items in a collection to the console.</span></span></li><li><span data-ttu-id="fc32f-124">**ReadLine.cs**: eine hilfsaktivität zum Lesen von Eingaben über die Konsole.</span><span class="sxs-lookup"><span data-stu-id="fc32f-124">**ReadLine.cs**: A helper activity for reading input from the console.</span></span></li></ul></li><li><span data-ttu-id="fc32f-125">Dateisystem:</span><span class="sxs-lookup"><span data-stu-id="fc32f-125">File System:</span></span><br /><br /> <ul><li><span data-ttu-id="fc32f-126">**Copy.XAML**: eine Aktivität, die eine Datei kopiert.</span><span class="sxs-lookup"><span data-stu-id="fc32f-126">**Copy.xaml**: An activity that copies a file.</span></span></li><li><span data-ttu-id="fc32f-127">**CreateFile.xaml**: eine Aktivität, eine Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="fc32f-127">**CreateFile.xaml**: An activity that creates a file.</span></span></li><li><span data-ttu-id="fc32f-128">**DeleteFile.xaml**: eine Aktivität, die eine Datei gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="fc32f-128">**DeleteFile.xaml**: An activity that deletes a file.</span></span></li><li><span data-ttu-id="fc32f-129">**MakeDir.xaml**: eine Aktivität, die ein Verzeichnis erstellt.</span><span class="sxs-lookup"><span data-stu-id="fc32f-129">**MakeDir.xaml**: An activity that creates a directory.</span></span></li><li><span data-ttu-id="fc32f-130">**Move.XAML**: eine Aktivität, die eine Datei verschiebt.</span><span class="sxs-lookup"><span data-stu-id="fc32f-130">**Move.xaml**: An activity that moves a file.</span></span></li><li><span data-ttu-id="fc32f-131">**ReadFile.xaml**: eine Aktivität, die eine Datei liest und ihren Inhalt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fc32f-131">**ReadFile.xaml**: An activity that reads a file and returns its contents.</span></span></li><li><span data-ttu-id="fc32f-132">**TestPath.xaml**: eine Aktivität, die das Vorhandensein eines Pfads überprüft.</span><span class="sxs-lookup"><span data-stu-id="fc32f-132">**TestPath.xaml**: An activity that tests for the existence of a path.</span></span></li></ul></li><li><span data-ttu-id="fc32f-133">Prozess:</span><span class="sxs-lookup"><span data-stu-id="fc32f-133">Process:</span></span><br /><br /> <ul><li><span data-ttu-id="fc32f-134">**GetProcess.xaml**: eine Aktivität, die eine Liste der ausgeführten Prozesse abruft.</span><span class="sxs-lookup"><span data-stu-id="fc32f-134">**GetProcess.xaml**: An activity that gets a list of running processes.</span></span></li><li><span data-ttu-id="fc32f-135">**StopProcess.xaml**: eine Aktivität, die einen bestimmten Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="fc32f-135">**StopProcess.xaml**: An activity that stops a specific process.</span></span></li></ul></li><li><span data-ttu-id="fc32f-136">**Datei "Program.cs"**: Ruft den Sequence1-Workflow.</span><span class="sxs-lookup"><span data-stu-id="fc32f-136">**Program.cs**: Calls the Sequence1 workflow.</span></span></li><li><span data-ttu-id="fc32f-137">**Sequence1.XAML**: ein sequenzbasierter Workflow.</span><span class="sxs-lookup"><span data-stu-id="fc32f-137">**Sequence1.xaml**: A sequence-based workflow.</span></span></li></ul>|  
|<span data-ttu-id="fc32f-138">PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc32f-138">PowerShell</span></span>|<span data-ttu-id="fc32f-139">Die `InvokePowerShell`-Aktivität und ihre zugeordneten Designer.</span><span class="sxs-lookup"><span data-stu-id="fc32f-139">The `InvokePowerShell` activity and its associated designers.</span></span>|<span data-ttu-id="fc32f-140">Aktivitätsdateien</span><span class="sxs-lookup"><span data-stu-id="fc32f-140">Activity Files</span></span><br /><br /> <span data-ttu-id="fc32f-141">-   **ExecutePowerShell.cs**: die hauptausführungslogik der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fc32f-141">-   **ExecutePowerShell.cs**: The main execution logic of the activity.</span></span><br /><span data-ttu-id="fc32f-142">-   **InvokePowerShell.cs**: der Wrapper um die hauptausführungslogik, die eine generische (Rückgabewert) und eine (nicht-Rückgabewert) für nicht generische Version enthält.</span><span class="sxs-lookup"><span data-stu-id="fc32f-142">-   **InvokePowerShell.cs**: The wrapper around the main execution logic, which contains a generic (return value) version and a non-generic (non-return value) version.</span></span> <span data-ttu-id="fc32f-143">Dies ist die öffentliche Schnittstelle für die Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fc32f-143">This is the public interface for the activity.</span></span><br /><span data-ttu-id="fc32f-144">-   **NoPersistZone.cs**: Diese Aktivität verhindert, dass alle untergeordneten Aktivitäten beibehalten.</span><span class="sxs-lookup"><span data-stu-id="fc32f-144">-   **NoPersistZone.cs**: This activity prevents any child activities from persisting.</span></span> <span data-ttu-id="fc32f-145">Diese Klasse wird in der Implementierung der `InvokePowerShell`-Aktivität verwendet, um zu verhindern, dass die Aktivität mitten in der Ausführung beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="fc32f-145">This class is used within the `InvokePowerShell` activity implementation to prevent the activity from being persisted mid-execution.</span></span><br /><br /> <span data-ttu-id="fc32f-146">Designerdateien:</span><span class="sxs-lookup"><span data-stu-id="fc32f-146">Designer files:</span></span><br /><br /> <span data-ttu-id="fc32f-147">1.  **ArgumentDictionaryEditor.cs**: ein Windows-Dialogfeld, das dem Benutzer ermöglicht, die Argumente der Bearbeiten der `InvokePowerShell` Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fc32f-147">1.  **ArgumentDictionaryEditor.cs**: A Windows dialog that allows the user to edit the arguments of the `InvokePowerShell` activity.</span></span><br /><span data-ttu-id="fc32f-148">2.  **GenericInvokePowerShellDesigner.xaml** und **GenericInvokePowerShellDesigner.xaml.cs**: definiert die Darstellung der generischen `InvokePowerShell` Aktivität im [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc32f-148">2.  **GenericInvokePowerShellDesigner.xaml** and **GenericInvokePowerShellDesigner.xaml.cs**: Defines the appearance of the generic `InvokePowerShell` activity in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span><br /><span data-ttu-id="fc32f-149">3.  **InvokePowerShellDesigner.xaml** und **InvokePowerShellDesigner.cs**: definiert die Darstellung von nicht-generische `InvokePowerShell` Aktivität im [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc32f-149">3.  **InvokePowerShellDesigner.xaml** and **InvokePowerShellDesigner.cs**: Defines the appearance of the non-generic `InvokePowerShell` activity in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>|  
  
 <span data-ttu-id="fc32f-150">Die Clientprojekte werden zuerst erläutert, da es einfacher ist, die interne Funktionalität der PowerShell-Aktivität zu verstehen, nachdem ihre Verwendung verstanden wurde.</span><span class="sxs-lookup"><span data-stu-id="fc32f-150">The client projects are discussed first, as it is easier to understand the internal functionality of the PowerShell activity once its use is understood.</span></span>  
  
## <a name="using-this-sample"></a><span data-ttu-id="fc32f-151">Verwenden dieses Beispiels</span><span class="sxs-lookup"><span data-stu-id="fc32f-151">Using This Sample</span></span>  
 <span data-ttu-id="fc32f-152">In den folgenden Abschnitten wird beschrieben, wie die drei Projekte im Beispiel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc32f-152">The following sections describe how to use the three projects in the sample.</span></span>  
  
### <a name="using-the-coded-client-project"></a><span data-ttu-id="fc32f-153">Verwenden des codierten Clientprojekts</span><span class="sxs-lookup"><span data-stu-id="fc32f-153">Using the Coded Client Project</span></span>  
 <span data-ttu-id="fc32f-154">Der Beispielclient erstellt programmgesteuert eine Sequenzaktivität, die Beispiele für mehrere verschiedene Methoden für die Verwendung der `InvokePowerShell`-Aktivität enthält.</span><span class="sxs-lookup"><span data-stu-id="fc32f-154">The sample client programmatically creates a sequence activity, which contains examples of several different methods of using the `InvokePowerShell` activity.</span></span> <span data-ttu-id="fc32f-155">Mit dem ersten Aufruf wird der Editor gestartet.</span><span class="sxs-lookup"><span data-stu-id="fc32f-155">The first invocation launches Notepad.</span></span>  
  
```  
new InvokePowerShell()  
{  
    CommandText = "notepad"  
},  
```  
  
 <span data-ttu-id="fc32f-156">Der zweite Aufruf ruft eine Liste der Prozesse ab, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fc32f-156">The second invocation gets a list of the processes running on the local machine.</span></span>  
  
```  
new InvokePowerShell<Process>()  
{  
    CommandText = "Get-Process",  
    Output = processes1,  
},  
```  
  
 <span data-ttu-id="fc32f-157">`Output` ist die Variable, die zum Speichern der Ausgabe des Befehls verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fc32f-157">`Output` is the variable used to store the output of the command.</span></span>  
  
 <span data-ttu-id="fc32f-158">Der nächste Aufruf veranschaulicht, wie ein Nachverarbeitungsschritt für jede einzelne Ausgabe des PowerShell-Aufrufs ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fc32f-158">The next call demonstrates how to run a post-processing step on each individual output of the PowerShell invocation.</span></span> <span data-ttu-id="fc32f-159">Für `InitializationAction` wird die Funktion festgelegt, die eine Zeichenfolgendarstellung für die einzelnen Prozesse ausgibt.</span><span class="sxs-lookup"><span data-stu-id="fc32f-159">`InitializationAction` is set to the function that outputs a string representation for each process.</span></span> <span data-ttu-id="fc32f-160">Die Auflistung dieser Zeichenfolgen wird in der `Output`-Variablen von der `InvokePowerShell<string>`-Aktivität zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fc32f-160">The collection of these strings is returned in the `Output` variable by the `InvokePowerShell<string>` activity.</span></span>  
  
 <span data-ttu-id="fc32f-161">Die erfolgreichen `InvokePowerShell`-Aufrufe veranschaulichen das Übergeben von Daten an die Aktivität und Abrufen von Ausgaben und Fehlern.</span><span class="sxs-lookup"><span data-stu-id="fc32f-161">The succeeding `InvokePowerShell` calls demonstrate passing data into the activity and getting outputs and errors out.</span></span>  
  
### <a name="using-the-designer-client-project"></a><span data-ttu-id="fc32f-162">Verwenden des Designerclientprojekts</span><span class="sxs-lookup"><span data-stu-id="fc32f-162">Using the Designer Client Project</span></span>  
 <span data-ttu-id="fc32f-163">Das DesignerClient-Projekt besteht aus einem Satz benutzerdefinierter Aktivitäten, die fast alle die `InvokePowerShell`-Aktivität enthalten.</span><span class="sxs-lookup"><span data-stu-id="fc32f-163">The DesignerClient project consists of a set of custom activities, almost all of which are built containing the `InvokePowerShell` activity.</span></span> <span data-ttu-id="fc32f-164">Die meisten der Aktivitäten rufen die nicht generische Version der `InvokePowerShell`-Aktivität auf und erwarten keinen Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="fc32f-164">Most of the activities call the non-generic version of the `InvokePowerShell` activity, and do not expect a return value.</span></span> <span data-ttu-id="fc32f-165">Andere Aktivitäten verwenden die generische Version der `InvokePowerShell`-Aktivität und verwenden das `InitializationAction`-Argument für die Nachverarbeitung der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="fc32f-165">Other activities use the generic version of the `InvokePowerShell` activity, and use the `InitializationAction` argument to post-process the results.</span></span>  
  
## <a name="using-the-powershell-project"></a><span data-ttu-id="fc32f-166">Verwenden des PowerShell-Projekts</span><span class="sxs-lookup"><span data-stu-id="fc32f-166">Using the PowerShell Project</span></span>  
 <span data-ttu-id="fc32f-167">Die Hauptaktion der Aktivität findet in der `ExecutePowerShell`-Klasse statt.</span><span class="sxs-lookup"><span data-stu-id="fc32f-167">The main action of the activity takes place in the `ExecutePowerShell` class.</span></span> <span data-ttu-id="fc32f-168">Da die Ausführung von PowerShell-Befehlen den Hauptworkflowthread nicht blockieren sollte, wird die Aktivität als asynchrone Aktivität erstellt, indem sie von der <xref:System.Activities.AsyncCodeActivity>-Klasse erbt.</span><span class="sxs-lookup"><span data-stu-id="fc32f-168">Because the execution of PowerShell commands should not block the main workflow thread, the activity is created to be an asynchronous activity by inheriting from the <xref:System.Activities.AsyncCodeActivity> class.</span></span>  
  
 <span data-ttu-id="fc32f-169">Die <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>-Methode wird von der Workflowlaufzeit aufgerufen, um mit der Ausführung der Aktivität zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-169">The <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> method is called by the workflow runtime to begin running the activity.</span></span> <span data-ttu-id="fc32f-170">Sie beginnt mit dem Aufruf von PowerShell-APIs zum Erstellen einer PowerShell-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="fc32f-170">It starts by calling PowerShell APIs to create a PowerShell pipeline.</span></span>  
  
```  
runspace = RunspaceFactory.CreateRunspace();  
runspace.Open();  
pipeline = runspace.CreatePipeline();  
```  
  
 <span data-ttu-id="fc32f-171">Anschließend erstellt sie einen PowerShell-Befehl und füllt ihn mit Parametern und Variablen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-171">It then creates a PowerShell command and populates it with parameters and variables.</span></span>  
  
```  
Command cmd = new Command(this.CommandText, this.IsScript);   
// loop over parameters and run: cmd.Parameters.Add(...)  
// loop over variables and run: runspace.SessionStateProxy.SetVariable(...)  
pipeline.Commands.Add(cmd);  
```  
  
 <span data-ttu-id="fc32f-172">Die über die Pipeline übergebenen Eingaben werden an diesem Punkt ebenfalls an die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="fc32f-172">The inputs piped in are also sent to the pipeline at this point.</span></span> <span data-ttu-id="fc32f-173">Zum Schluss wird die Pipeline mit einem `PipelineInvokerAsyncResult`-Objekt als Wrapper versehen und zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fc32f-173">Finally, the pipeline is wrapped in a `PipelineInvokerAsyncResult` object and returned.</span></span> <span data-ttu-id="fc32f-174">Das `PipelineInvokerAsyncResult`-Objekt registriert einen Listener und ruft die Pipeline auf.</span><span class="sxs-lookup"><span data-stu-id="fc32f-174">The `PipelineInvokerAsyncResult` object registers a listener and invokes the pipeline.</span></span>  
  
```  
pipeline.InvokeAsync();  
```  
  
 <span data-ttu-id="fc32f-175">Nach dem Beenden der Ausführung werden die Ausgabe und Fehler in demselben `PipelineInvokerAsyncResult`-Objekt gespeichert. Die Workflowlaufzeit erlangt wieder die Steuerung, indem die ursprünglich an <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> übergebene Rückrufmethode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fc32f-175">When execution finishes, output and errors are stored within the same `PipelineInvokerAsyncResult` object, and control is handed back to the workflow runtime by calling the callback method originally passed to <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.</span></span>  
  
 <span data-ttu-id="fc32f-176">Bei Ende der Methodenausführung ruft die Workflowlaufzeit die <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>-Methode der Aktivität auf.</span><span class="sxs-lookup"><span data-stu-id="fc32f-176">At the end of the method's execution, the workflow runtime calls the activity’s <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> method.</span></span>  
  
 <span data-ttu-id="fc32f-177">Die `InvokePowerShell`-Klasse fungiert als Wrapper der `ExecutePowerShellCommand`-Klasse und erstellt zwei Versionen der Aktivität, eine generische Version und eine nicht generische Version.</span><span class="sxs-lookup"><span data-stu-id="fc32f-177">The `InvokePowerShell` class wraps the `ExecutePowerShellCommand` class and creates two versions of the activity; a generic version and a non-generic version.</span></span> <span data-ttu-id="fc32f-178">Die nicht generische Version gibt die Ausgabe der PowerShell-Ausführung direkt zurück, wohingegen die generische Version die einzelnen Ergebnisse in den generischen Typ transformiert.</span><span class="sxs-lookup"><span data-stu-id="fc32f-178">The non-generic version returns the output of the PowerShell execution directly, whereas the generic version transforms the individual results to the generic type.</span></span>  
  
 <span data-ttu-id="fc32f-179">Die generische Version der Aktivität wird als sequenzieller Workflow implementiert, der `ExecutePowerShellCommand` aufruft und die Ergebnisse nachverarbeitet.</span><span class="sxs-lookup"><span data-stu-id="fc32f-179">The generic version of the activity is implemented as a sequential workflow that calls `ExecutePowerShellCommand` and post-processes its results.</span></span> <span data-ttu-id="fc32f-180">Für jedes Element in der Ergebnisauflistung ruft der Nachverarbeitungsschritt `InitializationAction` auf, wenn dies festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fc32f-180">For each element in the result collection, the post-processing step calls `InitializationAction` if it is set.</span></span> <span data-ttu-id="fc32f-181">Andernfalls wird eine einfache Umwandlung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fc32f-181">Otherwise, it does a simple cast.</span></span>  
  
```  
new ForEach<PSObject>  
{  
    Values = psObjects,  
    Body = new ActivityAction<PSObject>  
    {  
        Argument = psObject,  
        Handler = new Sequence  
        {  
            Activities =  
            {  
                new If  
                {  
                    Condition = // Is InitializationAction set?  
                    Then = new InvokeFunc<PSObject, TResult>  
                    {  
                        Argument = psObject,  
                        Result = outputObject,  
                        Func = this.InitializationAction  
                    },  
                    Else = new Assign<TResult>  
                    {  
                        To = outputObject,  
                        Value = new InArgument<TResult>(ctx => (TResult) psObject.Get(ctx).BaseObject),  
                    }  
                },  
                new AddToCollection<TResult>  
                {  
                    Collection = outputObjects,  
                    Item = outputObject  
                },  
            }  
        }  
    }  
},  
```  
  
 <span data-ttu-id="fc32f-182">Für jede der beiden `InvokePowerShell`-Aktivitäten (generisch und nicht generisch) wurde ein Designer erstellt.</span><span class="sxs-lookup"><span data-stu-id="fc32f-182">For each of the two `InvokePowerShell` activities (generic, and non-generic), a designer was created.</span></span> <span data-ttu-id="fc32f-183">InvokePowerShellDesigner.xaml und die entsprechende CS-Datei definieren die Darstellung in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] für die nicht generische Version der `InvokePowerShell`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fc32f-183">InvokePowerShellDesigner.xaml and its associated .cs file define the appearance in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] for the non-generic version of the `InvokePowerShell` activity.</span></span> <span data-ttu-id="fc32f-184">In InvokePowerShellDesigner.xaml wird ein <xref:System.Windows.Controls.DockPanel> verwendet, um die grafische Schnittstelle darzustellen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-184">Inside InvokePowerShellDesigner.xaml, a <xref:System.Windows.Controls.DockPanel> is used to represent the graphical interface.</span></span>  
  
```  
<DockPanel x:Uid="DockPanel_1" LastChildFill="True">  
        <TextBlock x:Uid="TextBlock_1" Text="CommandText" />  
        <TextBox x:Uid="TextBox_1" Text="{Binding Path=ModelItem.CommandText, Mode=TwoWay}"  
                 TextWrapping="WrapWithOverflow"  AcceptsReturn="True" MinLines="4" MaxLines="4"  
                 Background="{x:Null}" Margin="3" />  
    </DockPanel>  
```  
  
 <span data-ttu-id="fc32f-185">Beachten Sie, dass die `Text`-Eigenschaft des Textfelds eine bidirektionale Bindung ist, die sicherstellt, dass der Wert der `CommandText`-Eigenschaft der Aktivität dem im Designer eingegebenen Wert entspricht.</span><span class="sxs-lookup"><span data-stu-id="fc32f-185">Note that the `Text` property of the text box is a two-way binding that ensures that the value of the activity’s `CommandText` property is equivalent to the value input into the designer.</span></span>  
  
 <span data-ttu-id="fc32f-186">GenericInvokePowerShellDesigner.xaml und die entsprechende CS-Datei definieren die grafische Schnittstelle für die generische `InvokePowerShell`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fc32f-186">GenericInvokePowerShellDesigner.xaml and its associated .cs file define the graphical interface for the generic `InvokePowerShell` activity.</span></span> <span data-ttu-id="fc32f-187">Der Designer ist etwas komplizierter, da er Benutzern ermöglicht, eine `InitializationAction` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-187">The designer is slightly more complicated because it allows users to set an `InitializationAction`.</span></span> <span data-ttu-id="fc32f-188">Das Schlüsselelement ist die Verwendung von <xref:System.Activities.Presentation.WorkflowItemPresenter>, wodurch das Ziehen und Ablegen untergeordneter Aktivitäten in die `InvokePowerShell`-Designer Oberfläche ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="fc32f-188">The key element is the usage of <xref:System.Activities.Presentation.WorkflowItemPresenter> to allow drag and drop of child activities onto the `InvokePowerShell` designer surface.</span></span>  
  
```  
<sap:WorkflowItemPresenter x:Uid="sap:WorkflowItemPresenter_1" Margin="0,10,0,10"  
    HintText="Drop Activities Here"  
    AllowedItemType="{x:Type sa:Activity}"  
    Item="{Binding Path=ModelItem.InitializationAction.Handler, Mode=TwoWay}"  
    Grid.Row="1" Grid.Column="1" />  
```  
  
 <span data-ttu-id="fc32f-189">Die Designeranpassung hört nicht mit den XAML-Dateien auf, die die Darstellung der Aktivität im Zeichenbereich definieren.</span><span class="sxs-lookup"><span data-stu-id="fc32f-189">The designer customization does not stop with the .xaml files that define the appearance of the activity on the design canvas.</span></span> <span data-ttu-id="fc32f-190">Die Dialogfelder, die zum Anzeigen der Parameter der Aktivität verwendet werden, können ebenfalls angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="fc32f-190">The dialog boxes used to display the parameters of the activity can also be customized.</span></span> <span data-ttu-id="fc32f-191">Diese Parameter und PowerShell-Variablen wirken sich auf das Verhalten von PowerShell-Befehlen aus.</span><span class="sxs-lookup"><span data-stu-id="fc32f-191">These parameters and PowerShell variables affect the behavior of PowerShell commands.</span></span> <span data-ttu-id="fc32f-192">Die Aktivität macht sie als <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` Typen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-192">The activity exposes them as <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` types.</span></span> <span data-ttu-id="fc32f-193">Mit ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml und PropertyEditorResources.cs wird das Dialogfeld definiert, das Ihnen ermöglicht, diese Typen zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="fc32f-193">ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml and PropertyEditorResources.cs define the dialog box that allows you to edit these types.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fc32f-194">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="fc32f-194">To set up, build, and run the sample</span></span>  
 <span data-ttu-id="fc32f-195">Sie müssen Windows PowerShell installieren, um dieses Beispiel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="fc32f-195">You must install Windows PowerShell to run this sample.</span></span> <span data-ttu-id="fc32f-196">Windows PowerShell kann von diesem Speicherort installiert werden: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).</span><span class="sxs-lookup"><span data-stu-id="fc32f-196">Windows PowerShell can be installed from this location: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).</span></span>  
  
#### <a name="to-run-the-coded-client"></a><span data-ttu-id="fc32f-197">So führen Sie den kodierten Client aus</span><span class="sxs-lookup"><span data-stu-id="fc32f-197">To run the coded client</span></span>  
  
1.  <span data-ttu-id="fc32f-198">Öffnen Sie PowerShell.sln mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc32f-198">Open PowerShell.sln using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="fc32f-199">Klicken Sie mit der rechten Maustaste auf die Projektmappe, und erstellen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="fc32f-199">Right-click the solution and build it.</span></span>  
  
3.  <span data-ttu-id="fc32f-200">Mit der rechten Maustaste die **CodedClient** Projekt, und wählen Sie **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="fc32f-200">Right-click the **CodedClient** project and select **Set as Startup Project**.</span></span>  
  
4.  <span data-ttu-id="fc32f-201">Drücken Sie STRG+F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-201">Press CTRL+F5 to run the application.</span></span>  
  
#### <a name="to-run-the-designer-client"></a><span data-ttu-id="fc32f-202">So führen Sie den Designerclient aus</span><span class="sxs-lookup"><span data-stu-id="fc32f-202">To run the designer client</span></span>  
  
1.  <span data-ttu-id="fc32f-203">Öffnen Sie PowerShell.sln mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc32f-203">Open PowerShell.sln using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="fc32f-204">Klicken Sie mit der rechten Maustaste auf die Projektmappe, und erstellen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="fc32f-204">Right-click the solution and build it.</span></span>  
  
3.  <span data-ttu-id="fc32f-205">Mit der rechten Maustaste die **DesignerClient** Projekt, und wählen Sie **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="fc32f-205">Right-click the **DesignerClient** project and select **Set as Startup Project**.</span></span>  
  
4.  <span data-ttu-id="fc32f-206">Drücken Sie STRG+F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-206">Press CTRL+F5 to run the application.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="fc32f-207">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="fc32f-207">Known Issues</span></span>  
  
1.  <span data-ttu-id="fc32f-208">Wenn das Verweisen auf die `InvokePowerShell`-Aktivitätsassembly oder das Projekt von einem anderen Projekt zu einem Buildfehler führt, müssen Sie das `<SpecificVersion>True</SpecificVersion>`-Element möglicherweise manuell der CSPROJ-Datei des neuen Projekts unter der Zeile, die auf `InvokePowerShell` verweist, hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-208">If referencing the `InvokePowerShell` activity assembly or project from another project results in a build error, you may need to manually add the `<SpecificVersion>True</SpecificVersion>` element to the .csproj file of the new project under the line that references `InvokePowerShell`.</span></span>  
  
2.  <span data-ttu-id="fc32f-209">Wenn Windows PowerShell nicht installiert ist, wird die folgende Fehlermeldung in Visual Studio angezeigt, als Sie hinzufügen, eine `InvokePowerShell` Aktivität in einem Workflow:`Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`</span><span class="sxs-lookup"><span data-stu-id="fc32f-209">If Windows PowerShell is not installed, the following error message is displayed in Visual Studio as soon as you add an `InvokePowerShell` activity onto a workflow: `Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`</span></span>  
  
3.  <span data-ttu-id="fc32f-210">In Windows PowerShell 2.0 schlägt das programmgesteuerte Aufrufen von `$input.MoveNext()` fehl, und Skripte, die `$input.MoveNext()` verwenden, führen zu unbeabsichtigten Fehlern und Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-210">In Windows PowerShell 2.0, programmatically calling `$input.MoveNext()` fails and scripts using `$input.MoveNext()` produce unintended errors and results.</span></span> <span data-ttu-id="fc32f-211">Um dieses Problem zu vermeiden, ziehen Sie die Verwendung des PowerShell-Verbs `foreach` in Betracht, anstatt bei der Wiederholung eines Arrays `MoveNext()` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-211">To work around this issue, consider using the PowerShell verb `foreach` instead of calling `MoveNext()` when iterating an array.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fc32f-212">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="fc32f-212">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fc32f-213">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fc32f-213">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fc32f-214">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="fc32f-214">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fc32f-215">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fc32f-215">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`