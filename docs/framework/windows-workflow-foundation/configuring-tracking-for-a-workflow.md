---
title: Konfigurieren der Nachverfolgung für einen Workflow
ms.date: 03/30/2017
ms.assetid: 905adcc9-30a0-4918-acd6-563f86db988a
ms.openlocfilehash: 098b295be00b1b8283e26e79ea14e78634fdb504
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557553"
---
# <a name="configuring-tracking-for-a-workflow"></a><span data-ttu-id="0feef-102">Konfigurieren der Nachverfolgung für einen Workflow</span><span class="sxs-lookup"><span data-stu-id="0feef-102">Configuring Tracking for a Workflow</span></span>

<span data-ttu-id="0feef-103">Es gibt drei Möglichkeiten zum Ausführen eines Workflows:</span><span class="sxs-lookup"><span data-stu-id="0feef-103">A workflow can execute in three ways:</span></span>

- <span data-ttu-id="0feef-104">Gehostet in <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="0feef-104">Hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>

- <span data-ttu-id="0feef-105">Ausgeführt als <xref:System.Activities.WorkflowApplication></span><span class="sxs-lookup"><span data-stu-id="0feef-105">Executed as a <xref:System.Activities.WorkflowApplication></span></span>

- <span data-ttu-id="0feef-106">Ausgeführt direkt mit <xref:System.Activities.WorkflowInvoker></span><span class="sxs-lookup"><span data-stu-id="0feef-106">Executed directly using <xref:System.Activities.WorkflowInvoker></span></span>

<span data-ttu-id="0feef-107">Abhängig von der Workflow-Hostingoption kann ein Nachverfolgungsteilnehmer entweder über Code oder eine Konfigurationsdatei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0feef-107">Depending on the workflow hosting option, a tracking participant can be added either through code or through a configuration file.</span></span> <span data-ttu-id="0feef-108">In diesem Thema wird beschrieben, wie die Nachverfolgung konfiguriert wird, indem einer <xref:System.Activities.WorkflowApplication> und einem <xref:System.ServiceModel.Activities.WorkflowServiceHost> ein Nachverfolgungsteilnehmer hinzugefügt wird, und wie die Nachverfolgung bei der Verwendung von  <xref:System.Activities.WorkflowInvoker> aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="0feef-108">This topic describes how tracking is configured by adding a tracking participant to a <xref:System.Activities.WorkflowApplication> and to a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, and how to enable tracking when using <xref:System.Activities.WorkflowInvoker>.</span></span>

## <a name="configuring-workflow-application-tracking"></a><span data-ttu-id="0feef-109">Konfigurieren der Nachverfolgung von Workflowanwendungen</span><span class="sxs-lookup"><span data-stu-id="0feef-109">Configuring Workflow Application Tracking</span></span>

<span data-ttu-id="0feef-110">Ein Workflow kann mit der <xref:System.Activities.WorkflowApplication>-Klasse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0feef-110">A workflow can run using the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="0feef-111">Dieses Thema veranschaulicht, wie die Nachverfolgung für eine [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]-Workflowanwendung konfiguriert wird, indem dem <xref:System.Activities.WorkflowApplication>-Workflowhost ein Nachverfolgungsteilnehmer hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0feef-111">This topic demonstrates how tracking is configured for a [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] workflow application by adding a tracking participant to the <xref:System.Activities.WorkflowApplication> workflow host.</span></span> <span data-ttu-id="0feef-112">In diesem Fall wird der Workflow als Workflowanwendung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0feef-112">In this case, the workflow runs as a workflow application.</span></span> <span data-ttu-id="0feef-113">Sie konfigurieren eine Workflowanwendung über Code (statt eine Konfigurationsdatei zu verwenden), der aus einer selbst gehosteten EXE-Datei unter Verwendung der <xref:System.Activities.WorkflowApplication>-Klasse besteht.</span><span class="sxs-lookup"><span data-stu-id="0feef-113">You configure a workflow application through code (rather than by using a configuration file), which is a self-hosted .exe file using the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="0feef-114">Der Nachverfolgungsteilnehmer wird der <xref:System.Activities.WorkflowApplication>-Instanz als Erweiterung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0feef-114">The tracking participant is added as an extension to the <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="0feef-115">Dies geschieht, indem der Erweiterungsauflistung für die WorkflowApplication-Instanz der <xref:System.Activities.Tracking.TrackingParticipant> hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0feef-115">This is done by adding the <xref:System.Activities.Tracking.TrackingParticipant> to the extensions collection for the WorkflowApplication instance.</span></span>

<span data-ttu-id="0feef-116">Sie können einer Workflowanwendung die Erweiterung zum <xref:System.Activities.Tracking.EtwTrackingParticipant>-Verhalten hinzufügen. Dies wird im folgenden Code demonstriert.</span><span class="sxs-lookup"><span data-stu-id="0feef-116">For a workflow application, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> behavior extension as shown in the following code.</span></span>

```csharp
LogActivity activity = new LogActivity();

WorkflowApplication instance = new WorkflowApplication(activity);
EtwTrackingParticipant trackingParticipant =
    new EtwTrackingParticipant
{

        TrackingProfile = new TrackingProfile
           {
               Name = "SampleTrackingProfile",
               ActivityDefinitionId = "ProcessOrder",
               Queries = new WorkflowInstanceQuery
               {
                  States = { "*" }
              }
          }
       };
instance.Extensions.Add(trackingParticipant);
```

### <a name="configuring-workflow-service-tracking"></a><span data-ttu-id="0feef-117">Konfigurieren der Überwachung von Workflowdiensten</span><span class="sxs-lookup"><span data-stu-id="0feef-117">Configuring Workflow Service Tracking</span></span>

<span data-ttu-id="0feef-118">Ein Workflow kann als WCF-Dienst verfügbar gemacht werden, wenn er im <xref:System.ServiceModel.Activities.WorkflowServiceHost> Dienst Host gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="0feef-118">A workflow can be exposed as a WCF service when hosted in the <xref:System.ServiceModel.Activities.WorkflowServiceHost> service host.</span></span> <span data-ttu-id="0feef-119"><xref:System.ServiceModel.Activities.WorkflowServiceHost> ist eine spezialisierte .NET ServiceHost-Implementierung für einen workflowbasierten Dienst.</span><span class="sxs-lookup"><span data-stu-id="0feef-119"><xref:System.ServiceModel.Activities.WorkflowServiceHost> is a specialized .NET ServiceHost implementation for a workflow-based service.</span></span> <span data-ttu-id="0feef-120">In diesem Abschnitt wird erläutert, wie Sie die Nachverfolgung für einen im [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ausgeführten <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Workflowdienst konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0feef-120">This section explains how to configure tracking for a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow service running in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="0feef-121">Er wird durch eine Web.config-Datei (für einen im Web gehosteten Dienst) oder eine App.config-Datei (für einen Dienst, der in einer eigenständigen Anwendung, z. B. einer Konsolenanwendung, gehostet wird) konfiguriert, indem ein Dienstverhalten angegeben wird, oder durch Code, indem der <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>-Auflistung für den Diensthost ein nachverfolgungsspezifisches Verhalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0feef-121">It is configured through a Web.config file (for a Web-hosted service) or an App.config file (for a service hosted in a stand-alone application, such as a console application) by specifying a service behavior or through code by adding a tracking-specific behavior to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection for the service host.</span></span>

<span data-ttu-id="0feef-122">Für einen Workflow Dienst <xref:System.ServiceModel.WorkflowServiceHost> , der in gehostet wird, können Sie <xref:System.Activities.Tracking.EtwTrackingParticipant> mithilfe des <`behavior`>-Elements in einer Konfigurationsdatei hinzufügen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0feef-122">For a workflow service hosted in <xref:System.ServiceModel.WorkflowServiceHost>, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>

```xml
<behaviors>
   <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile" />
        </behavior>
   </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="0feef-123">Alternativ können Sie einem Workflowdienst, der im <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, die Erweiterung für das <xref:System.Activities.Tracking.EtwTrackingParticipant>-Verhalten über Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0feef-123">Alternatively, for a workflow service hosted in <xref:System.ServiceModel.WorkflowServiceHost>, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> behavior extension through code.</span></span> <span data-ttu-id="0feef-124">Um einen benutzerdefinierten Überwachungsteilnehmer hinzuzufügen, erstellen Sie eine neue Verhaltenserweiterung, und fügen Sie diese dem <xref:System.ServiceModel.ServiceHost> hinzu, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0feef-124">To add a custom tracking participant, create a new behavior extension and add it to the <xref:System.ServiceModel.ServiceHost> as shown in the following example code.</span></span>

> [!NOTE]
> <span data-ttu-id="0feef-125">Wenn Sie Beispielcode anzeigen möchten, der zeigt, wie ein benutzerdefiniertes Verhaltens Element erstellt wird, das einen benutzerdefinierten nach Verfolgungs Teilnehmer hinzufügt, lesen Sie die nach [Verfolgungs](./samples/tracking.md) Beispiele.</span><span class="sxs-lookup"><span data-stu-id="0feef-125">If you want to view sample code that shows how to create a custom behavior element that adds a custom tracking participant, refer to the [Tracking](./samples/tracking.md) samples.</span></span>

```csharp
ServiceHost svcHost = new ServiceHost(typeof(WorkflowService), new
                                 Uri("http://localhost:8001/Sample"));
EtwTrackingBehavior trackingBehavior =
    new EtwTrackingBehavior
    {
        ProfileName = "Sample Tracking Profile"
    };
svcHost.Description.Behaviors.Add(trackingBehavior);
svcHost.Open();
```

<span data-ttu-id="0feef-126">Der Überwachungsteilnehmer wird dem Workflow-Diensthost als Erweiterung zum Verhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0feef-126">The tracking participant is added to the workflow service host as an extension to the behavior.</span></span>

<span data-ttu-id="0feef-127">Aus dem unten angezeigten Beispielcode können Sie ersehen, wie ein Überwachungsprofil aus der Konfigurationsdatei gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="0feef-127">This sample code below shows how to read a tracking profile from configuration file.</span></span>

```csharp
TrackingProfile GetProfile(string profileName, string displayName)
        {
            TrackingProfile trackingProfile = null;
            TrackingSection trackingSection = (TrackingSection)WebConfigurationManager.GetSection("system.serviceModel/tracking");
            if (trackingSection == null)
            {
                return null;
            }

            profileName ??= "";

            //Find the profile with the specified profile name in the list of profile found in config
            var match = from p in new List<TrackingProfile>(trackingSection.TrackingProfiles)
                        where (p.Name == profileName) && ((p.ActivityDefinitionId == displayName) || (p.ActivityDefinitionId == "*"))
                        select p;

            if (match.Count() == 0)
            {
                //return an empty profile
                trackingProfile = new TrackingProfile()
                {
                    ActivityDefinitionId = displayName
                };

            }
            else
            {
                trackingProfile = match.First();
            }

            return trackingProfile;
```

<span data-ttu-id="0feef-128">In diesem Beispielcode wird gezeigt, wie einem Workflowhost ein Nachverfolgungsprofil hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0feef-128">This sample code shows how to add a tracking profile to a workflow host.</span></span>

```csharp
WorkflowServiceHost workflowServiceHost = serviceHostBase as WorkflowServiceHost;
if (null != workflowServiceHost)
{
    string workflowDisplayName = workflowServiceHost.Activity.DisplayName;
    TrackingProfile trackingProfile = GetProfile(this.profileName, workflowDisplayName);
    workflowServiceHost.WorkflowExtensions.Add(()  => new EtwTrackingParticipant {
        TrackingProfile = trackingProfile
    });
 }
```

> [!NOTE]
> <span data-ttu-id="0feef-129">Weitere Informationen zu Überwachungs Profilen finden Sie unter [Überwachungs profile](tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0feef-129">For more information on tracking profiles, refer to [Tracking Profiles](tracking-profiles.md).</span></span>

### <a name="configuring-tracking-using-workflowinvoker"></a><span data-ttu-id="0feef-130">Konfigurieren der Nachverfolgung mit WorkflowInvoker</span><span class="sxs-lookup"><span data-stu-id="0feef-130">Configuring tracking using WorkflowInvoker</span></span>

<span data-ttu-id="0feef-131">Um die Nachverfolgung für einen mit <xref:System.Activities.WorkflowInvoker> ausgeführten Workflow zu konfigurieren, fügen Sie den Nachverfolgungsanbieter als Erweiterung einer <xref:System.Activities.WorkflowInvoker>-Instanz hinzu.</span><span class="sxs-lookup"><span data-stu-id="0feef-131">To configure tracking for a workflow executed using <xref:System.Activities.WorkflowInvoker>, add the tracking provider as an extension to a <xref:System.Activities.WorkflowInvoker> instance.</span></span> <span data-ttu-id="0feef-132">Das folgende Codebeispiel wird aus dem Beispiel für die [benutzerdefinierte Nachverfolgung](./samples/custom-tracking.md) entnommen.</span><span class="sxs-lookup"><span data-stu-id="0feef-132">The following code example is from the [Custom Tracking](./samples/custom-tracking.md) sample.</span></span>

```csharp
WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
invoker.Invoke();
```

### <a name="viewing-tracking-records-in-event-viewer"></a><span data-ttu-id="0feef-133">Anzeigen von Nachverfolgungsdatensätzen in der Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="0feef-133">Viewing tracking records in Event Viewer</span></span>

<span data-ttu-id="0feef-134">Es gibt zwei Ereignisanzeigeprotokolle, die bei der Nachverfolgung der WF-Ausführung besonders von Interesse sind: das Analyseprotokoll und das Debugprotokoll.</span><span class="sxs-lookup"><span data-stu-id="0feef-134">There are two Event Viewer logs of particular interest to view when tracking WF execution - the Analytic log and the Debug log.</span></span> <span data-ttu-id="0feef-135">Beide befinden sich unter dem Knoten "Microsoft&#124;Windows&#124;Anwendungs Server-Anwendungen".</span><span class="sxs-lookup"><span data-stu-id="0feef-135">Both reside under the Microsoft&#124;Windows&#124;Application Server-Applications node.</span></span> <span data-ttu-id="0feef-136">Protokolle in diesem Abschnitt enthalten Ereignisse einer einzelnen Anwendung und keine Ereignisse, die Auswirkungen auf das gesamte System haben.</span><span class="sxs-lookup"><span data-stu-id="0feef-136">Logs within this section contain events from a single application rather than events that have an impact on the entire system.</span></span>

<span data-ttu-id="0feef-137">Ereignisse zur Debugablaufverfolgung werden in das Debugprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0feef-137">Debug trace events are written to the Debug Log.</span></span> <span data-ttu-id="0feef-138">Um WF-Debugablaufverfolgungs-Ereignisse in der Ereignisanzeige zu sammeln, aktivieren Sie das Debugprotokoll.</span><span class="sxs-lookup"><span data-stu-id="0feef-138">To collect WF debug trace events in the Event Viewer, enable the Debug Log.</span></span>

1. <span data-ttu-id="0feef-139">Klicken Sie zum Öffnen von Ereignisanzeige auf **Start**und dann auf **ausführen.**</span><span class="sxs-lookup"><span data-stu-id="0feef-139">To open Event Viewer, click **Start**, and then click **Run.**</span></span> <span data-ttu-id="0feef-140">Geben Sie im Dialogfeld Ausführen ein `eventvwr` .</span><span class="sxs-lookup"><span data-stu-id="0feef-140">In the Run dialog, type `eventvwr`.</span></span>

2. <span data-ttu-id="0feef-141">Erweitern Sie im Dialogfeld Ereignisanzeige den Knoten **Anwendungs-und Dienst Protokolle** .</span><span class="sxs-lookup"><span data-stu-id="0feef-141">In the Event Viewer dialog, expand the **Applications and Services Logs** node.</span></span>

3. <span data-ttu-id="0feef-142">Erweitern Sie die Knoten **Microsoft**, **Windows**und **Anwendungs Server-Anwendungen** .</span><span class="sxs-lookup"><span data-stu-id="0feef-142">Expand the **Microsoft**, **Windows**, and **Application Server-Applications** nodes.</span></span>

4. <span data-ttu-id="0feef-143">Klicken Sie mit der rechten Maustaste unter dem Knoten **Anwendungs Server-Anwendungen** auf den Knoten **Debuggen** , und wählen Sie **Protokoll aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="0feef-143">Right-click the **Debug** node under the **Application Server-Applications** node, and select **Enable Log**.</span></span>

5. <span data-ttu-id="0feef-144">Führen Sie die für die Ablaufverfolgung aktivierte Anwendung aus, um Ablaufverfolgungsereignisse zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0feef-144">Execute your tracing-enabled application to generate tracing events.</span></span>

6. <span data-ttu-id="0feef-145">Klicken Sie mit der rechten Maustaste auf den Knoten **Debug** , und wählen Sie **Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="0feef-145">Right-click the **Debug** node and select **Refresh.**</span></span> <span data-ttu-id="0feef-146">Ablaufverfolgungsereignisse sollten im mittleren Bereich sichtbar sein.</span><span class="sxs-lookup"><span data-stu-id="0feef-146">Tracing events should be visible in the center pane.</span></span>

<span data-ttu-id="0feef-147">WF4 stellt einen Nachverfolgungsteilnehmer bereit, der Nachverfolgungsdatensätze in eine ETW (Ereignisablaufverfolgung für Windows)-Sitzung schreibt.</span><span class="sxs-lookup"><span data-stu-id="0feef-147">WF 4 provides a tracking participant that writes tracking records to an ETW (Event Tracing for Windows) session.</span></span> <span data-ttu-id="0feef-148">Der ETW-Überwachungsteilnehmer ist mit einem Überwachungsprofil konfiguriert, um Überwachungsdatensätze zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="0feef-148">The ETW tracking participant is configured with a tracking profile to subscribe to tracking records.</span></span> <span data-ttu-id="0feef-149">Wenn die Nachverfolgung aktiviert ist, werden Nachverfolgungsdatensätze für Fehler in ETW ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="0feef-149">When tracking is enabled, errors tracking records are emitted to ETW.</span></span> <span data-ttu-id="0feef-150">ETW-Nachverfolgungsereignisse (im Bereich von 100-113), die den vom ETW-Nachverfolgungsteilnehmer ausgegebenen Nachverfolgungsereignissen entsprechen, werden in das Analyseprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0feef-150">ETW tracking events (between the range of 100-113) corresponding to the tracking events emitted by the ETW tracking participant are written to the Analytic Log.</span></span>

<span data-ttu-id="0feef-151">Gehen Sie wie folgt vor, um Nachverfolgungsdatensätze anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0feef-151">To view tracking records, follow these steps.</span></span>

1. <span data-ttu-id="0feef-152">Klicken Sie zum Öffnen von Ereignisanzeige auf **Start**und dann auf **ausführen.**</span><span class="sxs-lookup"><span data-stu-id="0feef-152">To open Event Viewer, click **Start**, and then click **Run.**</span></span> <span data-ttu-id="0feef-153">Geben Sie im Dialogfeld Ausführen ein `eventvwr` .</span><span class="sxs-lookup"><span data-stu-id="0feef-153">In the Run dialog, type `eventvwr`.</span></span>

2. <span data-ttu-id="0feef-154">Erweitern Sie im Dialogfeld Ereignisanzeige den Knoten **Anwendungs-und Dienst Protokolle** .</span><span class="sxs-lookup"><span data-stu-id="0feef-154">In the Event Viewer dialog, expand the **Applications and Services Logs** node.</span></span>

3. <span data-ttu-id="0feef-155">Erweitern Sie die Knoten **Microsoft**, **Windows**und **Anwendungs Server-Anwendungen** .</span><span class="sxs-lookup"><span data-stu-id="0feef-155">Expand the **Microsoft**, **Windows**, and **Application Server-Applications** nodes.</span></span>

4. <span data-ttu-id="0feef-156">Klicken Sie mit der rechten Maustaste auf den Knoten **Analyse** unter dem Knoten **Anwendungs Server-Anwendungen** , und wählen Sie **Protokoll aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="0feef-156">Right-click the **Analytic** node under the **Application Server-Applications** node, and select **Enable Log**.</span></span>

5. <span data-ttu-id="0feef-157">Führen Sie die für die Nachverfolgung aktivierte Anwendung aus, um Nachverfolgungsdatensätze zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0feef-157">Execute your tracking-enabled application to generate tracking records.</span></span>

6. <span data-ttu-id="0feef-158">Klicken Sie mit der rechten Maustaste auf den Knoten **Analyse** , und wählen Sie **Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="0feef-158">Right-click the **Analytic** node and select **Refresh.**</span></span> <span data-ttu-id="0feef-159">Nachverfolgungsdatensätze sollten im mittleren Bereich sichtbar sein.</span><span class="sxs-lookup"><span data-stu-id="0feef-159">Tracking records should be visible in the center pane.</span></span>

<span data-ttu-id="0feef-160">Die folgende Abbildung zeigt nach Verfolgungs Ereignisse in der Ereignisanzeige:</span><span class="sxs-lookup"><span data-stu-id="0feef-160">The following image shows tracking events in the event viewer:</span></span>

![Screenshot der Ereignisanzeige, die nach Verfolgungs Datensätze zeigt](./media/configuring-tracking-for-a-workflow/tracking-event-viewer.png)

### <a name="registering-an-application-specific-provider-id"></a><span data-ttu-id="0feef-162">Registrieren einer anwendungsspezifischen Anbieter-ID</span><span class="sxs-lookup"><span data-stu-id="0feef-162">Registering an application-specific provider ID</span></span>

<span data-ttu-id="0feef-163">Wenn Ereignisse in ein bestimmtes Anwendungsprotokoll geschrieben werden müssen, führen Sie folgende Schritte aus, um das neue Anbietermanifest zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="0feef-163">If events need to be written to a specific application log, follow these steps to register the new provider manifest.</span></span>

1. <span data-ttu-id="0feef-164">Deklarieren Sie die Anbieter-ID in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0feef-164">Declare the provider ID in the application configuration file.</span></span>

    ```xml
    <system.serviceModel>
        <diagnostics etwProviderId="2720e974-9fe9-477a-bb60-81fe3bf91eec"/>
    </system.serviceModel>
    ```

2. <span data-ttu-id="0feef-165">Kopieren Sie die Manifest-Datei aus "%windir%\Microsoft.NET\Framework \\ \<latest version of [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]> \Microsoft.Windows.ApplicationServer.Applications.man" an einen temporären Speicherort, und benennen Sie Sie in "Microsoft. Windows. ApplicationServer. Applications_Provider1. man" um.</span><span class="sxs-lookup"><span data-stu-id="0feef-165">Copy the manifest file from %windir%\Microsoft.NET\Framework\\\<latest version of [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]>\Microsoft.Windows.ApplicationServer.Applications.man to a temporary location, and rename it to Microsoft.Windows.ApplicationServer.Applications_Provider1.man</span></span>

3. <span data-ttu-id="0feef-166">Ändern Sie die GUID in der Manifestdatei in die neue GUID.</span><span class="sxs-lookup"><span data-stu-id="0feef-166">Change the GUID in the manifest file to the new GUID.</span></span>

    ```xml
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}" />
    ```

4. <span data-ttu-id="0feef-167">Ändern Sie den Anbieternamen, wenn Sie den Standardanbieter nicht deinstallieren wollen.</span><span class="sxs-lookup"><span data-stu-id="0feef-167">Change the provider name if you do not want to uninstall the default provider.</span></span>

    ```xml
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}" />
    ```

5. <span data-ttu-id="0feef-168">Wenn Sie den Anbieternamen im vorherigen Schritt änderten, ändern Sie die Kanalnamen in der Manifestdatei in den neuen Anbieternamen.</span><span class="sxs-lookup"><span data-stu-id="0feef-168">If you changed the provider name in the previous step, change the channel names in the manifest file to the new provider name.</span></span>

    ```xml
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Admin" chid="ADMIN_CHANNEL" symbol="ADMIN_CHANNEL" type="Admin" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ADMIN_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Operational" chid="OPERATIONAL_CHANNEL" symbol="OPERATIONAL_CHANNEL" type="Operational" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.OPERATIONAL_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Debug" chid="DEBUG_CHANNEL" symbol="DEBUG_CHANNEL" type="Debug" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.DEBUG_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Perf" chid="PERF_CHANNEL" symbol="PERF_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.PERF_CHANNEL.message)" />
    ```

6. <span data-ttu-id="0feef-169">Generieren Sie die Ressourcen-DLL, indem Sie folgende Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="0feef-169">Generate the resource DLL by following these steps.</span></span>

    1. <span data-ttu-id="0feef-170">Installieren Sie das Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="0feef-170">Install the Windows SDK.</span></span> <span data-ttu-id="0feef-171">Der Windows SDK enthält den Nachrichten Compiler ([mc.exe](/windows/win32/wes/message-compiler--mc-exe-)) und den Ressourcen Compiler ([rc.exe](/windows/win32/menurc/using-rc-the-rc-command-line-)).</span><span class="sxs-lookup"><span data-stu-id="0feef-171">The Windows SDK includes the message compiler ([mc.exe](/windows/win32/wes/message-compiler--mc-exe-)) and resource compiler ([rc.exe](/windows/win32/menurc/using-rc-the-rc-command-line-)).</span></span>

    2. <span data-ttu-id="0feef-172">Führen Sie in einer Windows SDK-Eingabeaufforderung mc.exe für die neue Manifestdatei aus.</span><span class="sxs-lookup"><span data-stu-id="0feef-172">In a Windows SDK command prompt, run mc.exe on the new manifest file.</span></span>

        ```console
        mc.exe Microsoft.Windows.ApplicationServer.Applications_Provider1.man
        ```

    3. <span data-ttu-id="0feef-173">Führen Sie rc.exe für die im vorherigen Schritt generierte Ressourcendatei aus.</span><span class="sxs-lookup"><span data-stu-id="0feef-173">Run rc.exe on the resource file generated in the previous step.</span></span>

        ```console
        rc.exe  Microsoft.Windows.ApplicationServer.Applications_Provider1.rc
        ```

    4. <span data-ttu-id="0feef-174">Erstellen Sie eine leere CS-Datei mit dem Namen NewProviderReg.cs.</span><span class="sxs-lookup"><span data-stu-id="0feef-174">Create an empty cs file called NewProviderReg.cs.</span></span>

    5. <span data-ttu-id="0feef-175">Erstellen Sie eine Ressourcen-DLL mithilfe des C#-Compilers.</span><span class="sxs-lookup"><span data-stu-id="0feef-175">Create a resource DLL using the C# compiler.</span></span>

        ```console
        csc /target:library /win32res:Microsoft.Windows.ApplicationServer.Applications_Provider1.res NewProviderReg.cs /out:Microsoft.Windows.ApplicationServer.Applications_Provider1.dll
        ```

    6. <span data-ttu-id="0feef-176">Ändern Sie den Namen der Ressourcen-und nachrichtendll in der Manifest-Datei von in `Microsoft.Windows.ApplicationServer.Applications.Provider1.man` den neuen DLL-Namen.</span><span class="sxs-lookup"><span data-stu-id="0feef-176">Change the resource and message dll name in the manifest file from `Microsoft.Windows.ApplicationServer.Applications.Provider1.man` to the new dll name.</span></span>

        ```xml
        <provider name="Microsoft-Windows-Application Server-Applications_Provider1" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}" symbol="Microsoft_Windows_ApplicationServer_ApplicationEvents" resourceFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll" messageFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll" />
        ```

    7. <span data-ttu-id="0feef-177">Verwenden Sie [wevtutil](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732848(v=ws.10)) , um das Manifest zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="0feef-177">Use [wevtutil](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732848(v=ws.10)) to register the manifest.</span></span>

        ```console
        wevtutil im Microsoft.Windows.ApplicationServer.Applications_Provider1.man
        ```

## <a name="see-also"></a><span data-ttu-id="0feef-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0feef-178">See also</span></span>

- <span data-ttu-id="0feef-179">[Windows Server-App-Fabric-Überwachung](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0feef-179">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="0feef-180">[Überwachen von Anwendungen mit App-Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0feef-180">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
