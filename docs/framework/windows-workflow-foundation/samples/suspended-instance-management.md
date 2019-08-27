---
title: Angehaltene Instanzverwaltung
ms.date: 03/30/2017
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
ms.openlocfilehash: 7a2f36ac2c127376eea56601f54aa5e571d66a55
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70037896"
---
# <a name="suspended-instance-management"></a><span data-ttu-id="f5f91-102">Angehaltene Instanzverwaltung</span><span class="sxs-lookup"><span data-stu-id="f5f91-102">Suspended Instance Management</span></span>
<span data-ttu-id="f5f91-103">In diesem Beispiel wird veranschaulicht, wie Workflowinstanzen, die angehalten wurden, verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="f5f91-103">This sample demonstrates how to manage workflow instances that have been suspended.</span></span>  <span data-ttu-id="f5f91-104">Die Standardaktion für <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> ist `AbandonAndSuspend`.</span><span class="sxs-lookup"><span data-stu-id="f5f91-104">The default action for <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is `AbandonAndSuspend`.</span></span> <span data-ttu-id="f5f91-105">Dies bedeutet, dass nicht behandelte Ausnahmen, die von einer Workflowinstanz ausgelöst werden, die im <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, standardmäßig dazu führen, dass die Instanz aus dem Speicher verworfen (abgebrochen) und dass die dauerhafte/persistente Version der Instanz als angehalten markiert wird.</span><span class="sxs-lookup"><span data-stu-id="f5f91-105">This means that by default, unhandled exceptions thrown from a workflow instance hosted in the <xref:System.ServiceModel.WorkflowServiceHost> will cause the instance to be disposed from memory (abandoned) and the durable/persisted version of the instance to be marked as suspended.</span></span> <span data-ttu-id="f5f91-106">Eine angehaltene Workflowinstanz kann erst ausgeführt werden, nachdem sie fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="f5f91-106">A suspended workflow instance will not be able to run until it has been unsuspended.</span></span>

 <span data-ttu-id="f5f91-107">Das Beispiel zeigt, wie ein Befehlszeilenprogramm implementiert werden kann, um angehaltene Instanzen abzufragen, und wie dem Benutzer die Option gegeben wird, um die Instanz fortzusetzen oder zu beenden.</span><span class="sxs-lookup"><span data-stu-id="f5f91-107">The sample shows how a command-line utility can be implemented to query for suspended instances, and how to give the user the option to resume or terminate the instance.</span></span> <span data-ttu-id="f5f91-108">In diesem Beispiel löst ein Workflowdienst absichtlich eine Ausnahme aus, wodurch verursacht wird, dass er angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="f5f91-108">In this sample, a workflow service intentionally throws an exception, causing it to become suspended.</span></span> <span data-ttu-id="f5f91-109">Das Befehlszeilenprogramm kann dann verwendet werden, um die Instanz abzufragen und anschließend die Instanz fortzusetzen oder zu beenden.</span><span class="sxs-lookup"><span data-stu-id="f5f91-109">The command-line utility can then be used to query for the instance and subsequently resume or terminate the instance.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="f5f91-110">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="f5f91-110">Demonstrates</span></span>
 <span data-ttu-id="f5f91-111"><xref:System.ServiceModel.WorkflowServiceHost>mit <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> und<xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="f5f91-111"><xref:System.ServiceModel.WorkflowServiceHost> with <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> and <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in Windows Workflow Foundation (WF).</span></span>

## <a name="discussion"></a><span data-ttu-id="f5f91-112">Diskussion</span><span class="sxs-lookup"><span data-stu-id="f5f91-112">Discussion</span></span>
 <span data-ttu-id="f5f91-113">Das in diesem Beispiel implementierte Befehlszeilenprogramm ist speziell auf die SQL-Instanzspeicherimplementierung ausgerichtet, die in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f5f91-113">The command-line utility implemented in this sample is specific to the SQL instance store implementation that ships in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="f5f91-114">Wenn Sie über eine benutzerdefinierte Implementierung des Instanzspeichers verfügen, können Sie dieses Hilfsprogramm anpassen, indem Sie die `WorkflowInstanceCommand`-Implementierungen im Beispiel durch Implementierungen speziell für Ihren Instanzspeicher ersetzen.</span><span class="sxs-lookup"><span data-stu-id="f5f91-114">If you have a custom implementation of the instance store, then you can adapt this utility by replacing the `WorkflowInstanceCommand` implementations in the sample with implementations that are specific to your instance store.</span></span>

 <span data-ttu-id="f5f91-115">Die bereitgestellte Implementierung führt SQL-Befehle direkt für den SQL-Instanzspeicher aus, um angehaltene Instanzen direkt aufzuführen, und diese basiert auf einem <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>, der dem <xref:System.ServiceModel.WorkflowServiceHost> hinzugefügt wurde, um die Instanzen fortzusetzen oder zu beenden.</span><span class="sxs-lookup"><span data-stu-id="f5f91-115">The provided implementation runs SQL commands against the SQL instance store directly to list suspended instances, and it relies on a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> added to the <xref:System.ServiceModel.WorkflowServiceHost> in order to resume or terminate the instances.</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f5f91-116">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="f5f91-116">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="f5f91-117">Dieses Beispiel erfordert, dass die folgenden Windows-Komponenten aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="f5f91-117">This sample requires that the following Windows components are enabled:</span></span>

    1. <span data-ttu-id="f5f91-118">Microsoft Message Queues (MSMQ) Server</span><span class="sxs-lookup"><span data-stu-id="f5f91-118">Microsoft Message Queues (MSMQ) Server</span></span>

    2. <span data-ttu-id="f5f91-119">SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="f5f91-119">SQL Server Express</span></span>

2. <span data-ttu-id="f5f91-120">Richten Sie die SQL Server-Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="f5f91-120">Set up the SQL Server database.</span></span>

    1. <span data-ttu-id="f5f91-121">Führen Sie an einer Visual Studio 2010-Eingabeaufforderung "Setup. cmd" aus dem Beispiel Verzeichnis suspendedinstancemanagement aus, das Folgendes bewirkt:</span><span class="sxs-lookup"><span data-stu-id="f5f91-121">From a Visual Studio 2010 command prompt, run "setup.cmd" from the SuspendedInstanceManagement sample directory, which does the following:</span></span>

        1. <span data-ttu-id="f5f91-122">Erstellung einer Persistenzdatenbank mit SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="f5f91-122">Creates a persistence database using SQL Server Express.</span></span> <span data-ttu-id="f5f91-123">Wenn die Persistenzdatenbank bereits vorhanden ist, dann wird diese gelöscht und neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="f5f91-123">If the persistence database already exists, then it is dropped and re-created</span></span>

        2. <span data-ttu-id="f5f91-124">Einrichten der Datenbank für Persistenz.</span><span class="sxs-lookup"><span data-stu-id="f5f91-124">Sets up the database for persistence.</span></span>

        3. <span data-ttu-id="f5f91-125">Fügt IIS der InstanceStoreUsers-Rolle, die beim Einrichten der Datenbank für Persistenz definiert wurde, APPPOOL\DefaultAppPool und NT AUTHORITY\Network Service hinzu.</span><span class="sxs-lookup"><span data-stu-id="f5f91-125">Adds IIS APPPOOL\DefaultAppPool and NT AUTHORITY\Network Service to the InstanceStoreUsers role that was defined when setting up the database for persistence.</span></span>

3. <span data-ttu-id="f5f91-126">Einrichten der Dienstwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="f5f91-126">Set up the service queue.</span></span>

    1. <span data-ttu-id="f5f91-127">Klicken Sie in Visual Studio 2010 mit der rechten Maustaste auf das Projekt **sampleworkflowapp** , und klicken Sie auf **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="f5f91-127">In Visual Studio 2010, right-click the **SampleWorkflowApp** project and click **Set as Startup Project**.</span></span>

    2. <span data-ttu-id="f5f91-128">Kompilieren Sie sampleworkflowapp, und führen Sie es aus, indem Sie **F5**drücken.</span><span class="sxs-lookup"><span data-stu-id="f5f91-128">Compile and run the SampleWorkflowApp by pressing **F5**.</span></span> <span data-ttu-id="f5f91-129">Dadurch wird die erforderliche Warteschlange erstellt.</span><span class="sxs-lookup"><span data-stu-id="f5f91-129">This will create the required queue.</span></span>

    3. <span data-ttu-id="f5f91-130">Drücken **Sie die Eingabe** Taste, um die sampleworkflowapp zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="f5f91-130">Press **Enter** to stop the SampleWorkflowApp.</span></span>

    4. <span data-ttu-id="f5f91-131">Öffnen Sie die Computerverwaltungskonsole, indem Sie "Compmgmt.msc" an einer Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="f5f91-131">Open the Computer Management console by running Compmgmt.msc from a command prompt.</span></span>

    5. <span data-ttu-id="f5f91-132">Erweitern Sie **Dienst und Anwendungen**, **Message Queuing**, **private Warteschlangen**.</span><span class="sxs-lookup"><span data-stu-id="f5f91-132">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>

    6. <span data-ttu-id="f5f91-133">Klicken Sie mit der rechten Maustaste auf **receivetx** , und wählen Sie **Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="f5f91-133">Right click the **ReceiveTx** queue and select **Properties**.</span></span>

    7. <span data-ttu-id="f5f91-134">Wählen Sie die Registerkarte **Sicherheit** aus, und gewähren Sie **allen** Benutzern dieBerechtigung zum **empfangen**von Nachrichten, einsehen und Senden von nach **richten**.</span><span class="sxs-lookup"><span data-stu-id="f5f91-134">Select the **Security** tab and allow **Everyone** to have permissions to **Receive Message**, **Peek Message**, and **Send Message**.</span></span>

4. <span data-ttu-id="f5f91-135">Führen Sie nun das Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="f5f91-135">Now, run the sample.</span></span>

    1. <span data-ttu-id="f5f91-136">Führen Sie das Projekt sampleworkflowapp in Visual Studio 2010 erneut ohne Debuggen aus, indem Sie **STRG + F5**drücken.</span><span class="sxs-lookup"><span data-stu-id="f5f91-136">In Visual Studio 2010, run the SampleWorkflowApp project again without debugging by pressing **Ctrl+F5**.</span></span> <span data-ttu-id="f5f91-137">Zwei Endpunktadressen werden im Konsolenfenster ausgegeben: eine für den Anwendungsendpunkt und die andere vom <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="f5f91-137">Two endpoint addresses will be printed in the console window: one for the application endpoint and then other from the <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span></span> <span data-ttu-id="f5f91-138">Daraufhin wird eine Workflowinstanz erstellt, und Überwachungsdatensätze für diese Instanz werden im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5f91-138">A workflow instance is then created, and tracking records for that instance will appear in the console window.</span></span> <span data-ttu-id="f5f91-139">Die Workflowinstanz löst eine Ausnahme aus, die bewirkt, dass die Instanz angehalten und abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="f5f91-139">The workflow instance will throw an exception causing the instance to be suspended and aborted.</span></span>

    2. <span data-ttu-id="f5f91-140">Das Befehlszeilenprogramm kann dann verwendet werden, um weitere Aktionen für diese Instanzen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f5f91-140">The command-line utility can then be used to take further action on any of these instances.</span></span> <span data-ttu-id="f5f91-141">Die Syntax für Befehlszeilenargumente ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f5f91-141">The syntax for command line arguments is as follows::</span></span>

         `SuspendedInstanceManagement -Command:[CommandName] -Server:[ServerName] -Database:[DatabaseName] -InstanceId:[InstanceId]`

         <span data-ttu-id="f5f91-142">Die unterstützten Befehle sind: `Query`, `Resume` und `Terminate`.</span><span class="sxs-lookup"><span data-stu-id="f5f91-142">The supported commands are: `Query`, `Resume`, and `Terminate`.</span></span>  <span data-ttu-id="f5f91-143">Der InstanceId-Schalter ist nur für `Resume`- und `Terminate`-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f5f91-143">The InstanceId switch is only required for `Resume` and `Terminate` operations.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="f5f91-144">So führen Sie eine (optionale) Bereinigung durch</span><span class="sxs-lookup"><span data-stu-id="f5f91-144">To cleanup (Optional)</span></span>

1. <span data-ttu-id="f5f91-145">Öffnen Sie die Computerverwaltungskonsole, indem Sie "Compmgmt.msc" an einer `vs2010`-Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="f5f91-145">Open the Computer Management console by running Compmgmt.msc from a `vs2010` command prompt.</span></span>

2. <span data-ttu-id="f5f91-146">Erweitern Sie **Dienst und Anwendungen**, **Message Queuing**, **private Warteschlangen**.</span><span class="sxs-lookup"><span data-stu-id="f5f91-146">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>

3. <span data-ttu-id="f5f91-147">Löschen Sie die **receivetx** -Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="f5f91-147">Delete the **ReceiveTx** queue.</span></span>

4. <span data-ttu-id="f5f91-148">Um die Persistenzdatenbank zu entfernen, führen Sie "cleanup.cmd" aus.</span><span class="sxs-lookup"><span data-stu-id="f5f91-148">To remove the persistence database, run cleanup.cmd.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5f91-149">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f5f91-149">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f5f91-150">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f5f91-150">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="f5f91-151">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="f5f91-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f5f91-152">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f5f91-152">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`
