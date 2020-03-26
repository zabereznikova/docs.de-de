---
title: Überwachungsprofile
ms.date: 03/30/2017
ms.assetid: 22682566-1cd9-4672-9791-fb3523638e18
ms.openlocfilehash: 609c3f0c728e71d1bbf5335aae0b18d6f99a7181
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249037"
---
# <a name="tracking-profiles"></a><span data-ttu-id="394ab-102">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="394ab-102">Tracking Profiles</span></span>

<span data-ttu-id="394ab-103">Überwachungsprofile enthalten Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="394ab-103">Tracking profiles contain tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span>

## <a name="tracking-profiles"></a><span data-ttu-id="394ab-104">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="394ab-104">Tracking Profiles</span></span>

<span data-ttu-id="394ab-105">Mithilfe von Nachverfolgungsprofilen wird angegeben, welche Nachverfolgungsinformationen für eine Workflowinstanz ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="394ab-105">Tracking profiles are used to specify which tracking information is emitted for a workflow instance.</span></span> <span data-ttu-id="394ab-106">Wenn kein Profil angegeben wird, dann werden alle Nachverfolgungsereignisse ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="394ab-106">If no profile is specified, then all tracking events are emitted.</span></span> <span data-ttu-id="394ab-107">Wenn ein Profil angegeben ist, werden die Nachverfolgungsereignisse, die im Profil angegeben sind, ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="394ab-107">If a profile is specified, then the tracking events specified in the profile will be emitted.</span></span> <span data-ttu-id="394ab-108">Je nach Überwachungsanforderungen können Sie ein Profil schreiben, das sehr allgemein gehalten ist und einen kleinen Satz von unspezifischen Zustandsänderungen eines Workflows abonniert.</span><span class="sxs-lookup"><span data-stu-id="394ab-108">Depending on your monitoring requirements, you may write a profile that is very general, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="394ab-109">Umgekehrt ist es möglich, ein sehr ausführliches Profil zu erstellen, dessen resultierende Ereignisse umfangreich genug sind, um später einen detaillierten Ausführungsfluss zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="394ab-109">Conversely, you may create a very detailed profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>

<span data-ttu-id="394ab-110">Nachverfolgungsprofile manifestieren sich als XML-Elemente in einer Standard -NET Framework-Konfigurationsdatei oder im Code angegeben.</span><span class="sxs-lookup"><span data-stu-id="394ab-110">Tracking profiles manifest themselves as XML elements within a standard .NET Framework configuration file or specified in code.</span></span> <span data-ttu-id="394ab-111">Das folgende Beispiel ist einem [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]-Überwachungsprofil in einer Konfigurationsdatei entnommen, die es einem Überwachungsteilnehmer ermöglicht, `Started`-Workflowereignisse und `Completed`-Workflowereignisse zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="394ab-111">The following example is of a [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>

```xml
<system.serviceModel>
    ...
    <tracking>
     <profiles>
      <trackingProfile name="Sample Tracking Profile">
        <workflow activityDefinitionId="*">
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="Started"/>
                <state name="Completed"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
    ...
</system.serviceModel>
```

<span data-ttu-id="394ab-112">Im folgenden Beispiel wird das entsprechende Nachverfolgungsprofil dargestellt, das mithilfe von Code erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="394ab-112">The following example shows the equivalent tracking profile created using code.</span></span>

```csharp
TrackingProfile profile = new TrackingProfile()
{
    Name = "CustomTrackingProfile",
    Queries =
    {
        new WorkflowInstanceQuery()
        {
            // Limit workflow instance tracking records for started and
            // completed workflow states.
            States = { WorkflowInstanceStates.Started, WorkflowInstanceStates.Completed },
        }
    }
};
```

<span data-ttu-id="394ab-113">Überwachungsdatensätze werden innerhalb eines Überwachungsprofils mit dem <xref:System.Activities.Tracking.ImplementationVisibility>-Attribut über den Sichtbarkeitsmodus gefiltert.</span><span class="sxs-lookup"><span data-stu-id="394ab-113">Tracking records are filtered through the visibility mode within a tracking profile by using the <xref:System.Activities.Tracking.ImplementationVisibility> attribute.</span></span> <span data-ttu-id="394ab-114">Eine zusammengesetzte Aktivität ist eine allgemeine Aktivität mit weiteren Aktivitäten, die ihre Implementierung bilden.</span><span class="sxs-lookup"><span data-stu-id="394ab-114">A composite activity is a top-level activity that contains other activities that form its implementation.</span></span> <span data-ttu-id="394ab-115">Der Sichtbarkeitsmodus gibt die von zusammengesetzten Aktivitäten in einer Workflowaktivität ausgegebenen Überwachungsdatensätze an. Damit wird bestimmt, ob Aktivitäten, aus denen die Implementierung besteht, nachverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="394ab-115">The visibility mode specifies the tracking records emitted from composite activities within a workflow activity, to specify if activities that form the implementation are being tracked.</span></span> <span data-ttu-id="394ab-116">Der Sichtbarkeitsmodus gilt für die Ebene des Überwachungsprofils.</span><span class="sxs-lookup"><span data-stu-id="394ab-116">The visibility mode applies at the tracking profile level.</span></span> <span data-ttu-id="394ab-117">Die Filterung von Überwachungsdatensätzen für einzelne Aktivitäten eines Workflows wird von den Abfragen im Überwachungsprofil gesteuert.</span><span class="sxs-lookup"><span data-stu-id="394ab-117">The filtering of tracking records for individual activities within a workflow is controlled by the queries within the tracking profile.</span></span> <span data-ttu-id="394ab-118">Weitere Informationen finden Sie im Abschnitt **Tracking Profile Query Types** in diesem Dokument.</span><span class="sxs-lookup"><span data-stu-id="394ab-118">For more information, see the **Tracking Profile Query Types** section in this document.</span></span>

<span data-ttu-id="394ab-119">Die zwei Sichtbarkeitsmodi, die vom `implementationVisibility`-Attribut im Überwachungsprofil angegeben werden, sind `RootScope` und `All`.</span><span class="sxs-lookup"><span data-stu-id="394ab-119">The two visibility modes specified by the `implementationVisibility` attribute in the tracking profile are `RootScope` and `All`.</span></span> <span data-ttu-id="394ab-120">Durch Verwendung des `RootScope`-Modus werden Überwachungsdatensätze für Aktivitäten, die die Implementierung einer Aktivität bilden, unterdrückt, wenn der Stamm eines Workflows keine zusammengesetzte Aktivität ist.</span><span class="sxs-lookup"><span data-stu-id="394ab-120">Using the `RootScope` mode suppresses the tracking records for activities that form the implementation of an activity in the case where a composite activity is not the root of a workflow.</span></span> <span data-ttu-id="394ab-121">Dies bedeutet, dass nur die allgemeine Aktivität innerhalb der zusammengesetzten Aktivität nachverfolgt wird, wenn einem Workflow eine Aktivität hinzugefügt wird, die mit anderen Aktivitäten implementiert wird, und `implementationVisibility` auf RootScope festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="394ab-121">This implies that, when an activity that is implemented using other activities is added to a workflow, and the `implementationVisibility` set to RootScope, only the top-level activity within that composite activity is tracked.</span></span> <span data-ttu-id="394ab-122">Wenn eine Aktivität der Stamm des Workflows ist, stellt die Implementierung der Aktivität den Workflow selbst dar, und Überwachungsdatensätze werden für Aktivitäten ausgegeben, die die Implementierung bilden.</span><span class="sxs-lookup"><span data-stu-id="394ab-122">If an activity is the root of the workflow, then the implementation of the activity is the workflow itself and tracking records are emitted for activities that form the implementation.</span></span> <span data-ttu-id="394ab-123">Bei Verwendung des All-Modus werden die Überwachungsdatensätze für die Stammaktivität und alle zugehörigen zusammengesetzten Aktivitäten ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="394ab-123">Using the All mode permits all tracking records to be emitted for the root activity and all its composite activities.</span></span>

<span data-ttu-id="394ab-124">Angenommen, *MyActivity* ist eine zusammengesetzte Aktivität, deren Implementierung zwei Aktivitäten enthält, *Aktivität1* und *Aktivität2*.</span><span class="sxs-lookup"><span data-stu-id="394ab-124">For example, suppose *MyActivity* is a composite activity whose implementation contains two activities, *Activity1* and *Activity2*.</span></span> <span data-ttu-id="394ab-125">Wenn diese Aktivität zu einem Workflow hinzugefügt wird und `implementationVisibility` die `RootScope`Nachverfolgung mit einem Überwachungsprofil mit der Einstellung auf aktiviert ist, werden Nachverfolgungsdatensätze nur für *MyActivity*emittiert.</span><span class="sxs-lookup"><span data-stu-id="394ab-125">When this activity is added to a workflow and tracking is enabled with a tracking profile with `implementationVisibility` set to `RootScope`, tracking records are emitted only for *MyActivity*.</span></span> <span data-ttu-id="394ab-126">Für die Aktivitäten *Activity1* und *Activity2*werden jedoch keine Datensätze emittiert.</span><span class="sxs-lookup"><span data-stu-id="394ab-126">However, no records are emitted for activities *Activity1* and *Activity2*.</span></span>

<span data-ttu-id="394ab-127">`implementationVisibility` Wenn das Attribut für das Nachverfolgungsprofil jedoch auf `All`festgelegt ist, werden Tracking-Datensätze nicht nur für *MyActivity*, sondern auch für Die Aktivitäten *Activity1* und *Activity2*angezeigt.</span><span class="sxs-lookup"><span data-stu-id="394ab-127">However, if the `implementationVisibility` attribute for the tracking profile is  set to `All`, then tracking records are emitted not only for *MyActivity*, but also for activities *Activity1* and *Activity2*.</span></span>

<span data-ttu-id="394ab-128">Das `implementationVisibility`-Flag gilt für folgende Datensatztypen für die Nachverfolgung:</span><span class="sxs-lookup"><span data-stu-id="394ab-128">The `implementationVisibility` flag applies to following tracking record types:</span></span>

- <span data-ttu-id="394ab-129">ActivityStateRecord</span><span class="sxs-lookup"><span data-stu-id="394ab-129">ActivityStateRecord</span></span>

- <span data-ttu-id="394ab-130">FaultPropagationRecord</span><span class="sxs-lookup"><span data-stu-id="394ab-130">FaultPropagationRecord</span></span>

- <span data-ttu-id="394ab-131">CancelRequestedRecord</span><span class="sxs-lookup"><span data-stu-id="394ab-131">CancelRequestedRecord</span></span>

- <span data-ttu-id="394ab-132">ActivityScheduledRecord</span><span class="sxs-lookup"><span data-stu-id="394ab-132">ActivityScheduledRecord</span></span>

> [!NOTE]
> <span data-ttu-id="394ab-133">Von der Aktivitätsimplementierung ausgegebene CustomTrackingRecords werden von der implementationVisibility-Einstellung nicht herausgefiltert.</span><span class="sxs-lookup"><span data-stu-id="394ab-133">CustomTrackingRecords emitted from activity implementation are not filtered out by the implementationVisibility setting.</span></span>

<span data-ttu-id="394ab-134">Die `implementationVisibility`-Funktionalität wird für das Überwachungsprofil auf folgende Weise als <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> in Code angegeben:</span><span class="sxs-lookup"><span data-stu-id="394ab-134">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> on the tracking profile in code as follows:</span></span>

```csharp
TrackingProfile sampleTrackingProfile = new TrackingProfile()
{
    Name = "Sample Tracking Profile",
    ImplementationVisibility = ImplementationVisibility.RootScope
};
```

<span data-ttu-id="394ab-135">Die `implementationVisibility`-Funktionalität kann für das Überwachungsprofil auf folgende Weise als <xref:System.Activities.Tracking.ImplementationVisibility.All> in einer Konfigurationsdatei angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="394ab-135">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.All> on the tracking profile in a configuration file as follows:</span></span>

```xml
<tracking>
      <profiles>
        <trackingProfile name="Shipping Monitoring" implementationVisibility="All">
          <workflow activityDefinitionId="*">
...
         </workflow>
        </trackingProfile>
      </profiles>
</tracking>
```

<span data-ttu-id="394ab-136">Die `ImplementationVisibility`-Einstellung ist für das Überwachungsprofil optional.</span><span class="sxs-lookup"><span data-stu-id="394ab-136">The `ImplementationVisibility` setting on the tracking profile is optional.</span></span> <span data-ttu-id="394ab-137">Standardmäßig ist der Wert auf `RootScope` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="394ab-137">By default, its value is set to `RootScope`.</span></span> <span data-ttu-id="394ab-138">Bei den Werten für dieses Attribut muss die Groß-/Kleinschreibung beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="394ab-138">The values for this attribute are also case-sensitive.</span></span>

### <a name="tracking-profile-query-types"></a><span data-ttu-id="394ab-139">Abfragetypen für Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="394ab-139">Tracking Profile Query Types</span></span>

<span data-ttu-id="394ab-140">Überwachungsprofile werden als deklarative Abonnements für Überwachungsdatensätze angeordnet, die es Ihnen ermöglichen, bestimmte Überwachungsdatensätze aus der Workflowlaufzeit abzufragen.</span><span class="sxs-lookup"><span data-stu-id="394ab-140">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="394ab-141">Es gibt mehrere Abfragetypen, mit denen Sie andere Klassen von <xref:System.Activities.Tracking.TrackingRecord>-Objekten abonnieren können.</span><span class="sxs-lookup"><span data-stu-id="394ab-141">There are several query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="394ab-142">Überwachungsprofile können in der Konfiguration oder durch Code angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="394ab-142">Tracking profiles can be specified in configuration or through code.</span></span> <span data-ttu-id="394ab-143">Im Folgenden werden die häufigsten Abfragetypen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="394ab-143">Here are the most common query types:</span></span>

- <span data-ttu-id="394ab-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Hiermit können Sie Änderungen am Workflowinstanz-Lebenszyklus nachverfolgen, z. B. die bereits erwähnten Optionen `Started` und `Completed`.</span><span class="sxs-lookup"><span data-stu-id="394ab-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery> - Use this to track workflow instance life cycle changes like the previously-demonstrated `Started` and `Completed`.</span></span> <span data-ttu-id="394ab-145"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="394ab-145">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>

  - <xref:System.Activities.Tracking.WorkflowInstanceRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>

  <span data-ttu-id="394ab-146">Jeder Zustand, der abonniert werden kann, ist in der <xref:System.Activities.Tracking.WorkflowInstanceStates>-Klasse angegeben.</span><span class="sxs-lookup"><span data-stu-id="394ab-146">The states that can be subscribed to are specified in the <xref:System.Activities.Tracking.WorkflowInstanceStates> class.</span></span>

  <span data-ttu-id="394ab-147">Die Konfiguration bzw. der Code zum Abonnieren von Überwachungsdatensätzen auf Workflowinstanzebene für den `Started`-Instanzzustand mit dem <xref:System.Activities.Tracking.WorkflowInstanceQuery>-Objekt wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="394ab-147">The configuration or code used to subscribe to workflow instance-level tracking records for the `Started` instance state using the <xref:System.Activities.Tracking.WorkflowInstanceQuery> is shown in the following example.</span></span>

  ```xml
  <workflowInstanceQueries>
      <workflowInstanceQuery>
        <states>
          <state name="Started"/>
        </states>
      </workflowInstanceQuery>
  </workflowInstanceQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new WorkflowInstanceQuery()
          {
              States = { WorkflowInstanceStates.Started}
          }
      }
  };
  ```

- <span data-ttu-id="394ab-148"><xref:System.Activities.Tracking.ActivityStateQuery> – Hiermit können Sie die Lebenszyklusänderungen der Aktivitäten nachverfolgen, aus denen eine Workflowinstanz besteht.</span><span class="sxs-lookup"><span data-stu-id="394ab-148"><xref:System.Activities.Tracking.ActivityStateQuery> - Use this to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="394ab-149">Sie können z. B. jedes Mal nachverfolgen, wenn die Aktivität "E-Mail senden" in einer Workflowinstanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="394ab-149">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="394ab-150">Diese Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt <xref:System.Activities.Tracking.ActivityStateRecord>-Objekte abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="394ab-150">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityStateRecord> objects.</span></span> <span data-ttu-id="394ab-151">Die verfügbaren Zustände, die abonniert werden können, werden im <xref:System.Activities.Tracking.ActivityStates>-Objekt angegeben.</span><span class="sxs-lookup"><span data-stu-id="394ab-151">The available states to subscribe to are specified in <xref:System.Activities.Tracking.ActivityStates>.</span></span>

  <span data-ttu-id="394ab-152">Die Konfiguration und der Code zum Abonnieren von Überwachungsdatensätzen für den Aktivitätszustand, die das  <xref:System.Activities.Tracking.ActivityStateQuery>-Objekt für die `SendEmailActivity`-Aktivität verwenden, werden im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="394ab-152">The configuration and code used to subscribe activity state tracking records that use the <xref:System.Activities.Tracking.ActivityStateQuery> for the `SendEmailActivity` activity is shown in the following example.</span></span>

  ```xml
  <activityStateQueries>
    <activityStateQuery activityName="SendEmailActivity">
      <states>
        <state name="Closed"/>
      </states>
    </activityStateQuery>
  </activityStateQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new ActivityStateQuery()
          {
              ActivityName = "SendEmailActivity",
              States = { ActivityStates.Closed }
          }
      }
  };
  ```

  > [!NOTE]
  > <span data-ttu-id="394ab-153">Wenn mehrere activityStateQuery-Elemente denselben Namen haben, werden nur die Zustände im letzten Element im Nachverfolgungsprofil verwendet.</span><span class="sxs-lookup"><span data-stu-id="394ab-153">If multiple activityStateQuery elements have the same name, only the states in the last element are used in the tracking profile.</span></span>

- <span data-ttu-id="394ab-154"><xref:System.Activities.Tracking.ActivityScheduledQuery> – Mit dieser Abfrage können Sie eine Aktivität nachverfolgen, die von einer übergeordneten Aktivität ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="394ab-154"><xref:System.Activities.Tracking.ActivityScheduledQuery> - This query allows you to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="394ab-155">Die Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt <xref:System.Activities.Tracking.ActivityScheduledRecord>-Objekte abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="394ab-155">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityScheduledRecord> objects.</span></span>

  <span data-ttu-id="394ab-156">Die Konfiguration und der Code zum Abonnieren von Datensätzen, die mit der untergeordneten `SendEmailActivity`-Aktivität verknüpft sind, deren Planung mit dem <xref:System.Activities.Tracking.ActivityScheduledQuery>-Objekt erfolgt, wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="394ab-156">The configuration and code used to subscribe to records related to the `SendEmailActivity` child activity being scheduled using the <xref:System.Activities.Tracking.ActivityScheduledQuery> is shown in the following example.</span></span>

  ```xml
  <activityScheduledQueries>
    <activityScheduledQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />
  </activityScheduledQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new ActivityScheduledQuery()
          {
              ActivityName = "ProcessNotificationsActivity",
              ChildActivityName = "SendEmailActivity"
          }
      }
  };
  ```

- <span data-ttu-id="394ab-157"><xref:System.Activities.Tracking.FaultPropagationQuery> – Hiermit können Sie die Behandlung von Fehlern nachverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="394ab-157"><xref:System.Activities.Tracking.FaultPropagationQuery> - Use this to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="394ab-158">Die Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt <xref:System.Activities.Tracking.FaultPropagationRecord>-Objekte abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="394ab-158">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.FaultPropagationRecord> objects.</span></span>

  <span data-ttu-id="394ab-159">Die Konfiguration und der Code zum Abonnieren von mit der Fehlerweitergabe verknüpften Datensätzen mithilfe von <xref:System.Activities.Tracking.FaultPropagationQuery> werden im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="394ab-159">The configuration and code used to subscribe to records related to fault propagation using <xref:System.Activities.Tracking.FaultPropagationQuery> is shown in the following example.</span></span>

  ```xml
  <faultPropagationQueries>
    <faultPropagationQuery faultSourceActivityName="SendEmailActivity" faultHandlerActivityName="NotificationsFaultHandler" />
  </faultPropagationQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new FaultPropagationQuery()
          {
              FaultSourceActivityName = "SendEmailActivity",
              FaultHandlerActivityName = "NotificationsFaultHandler"
          }
      }
  };
  ```

- <span data-ttu-id="394ab-160"><xref:System.Activities.Tracking.CancelRequestedQuery> – Hiermit können Sie Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="394ab-160"><xref:System.Activities.Tracking.CancelRequestedQuery> - Use this to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="394ab-161">Die Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt <xref:System.Activities.Tracking.CancelRequestedRecord>-Objekte abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="394ab-161">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CancelRequestedRecord> objects.</span></span>

  <span data-ttu-id="394ab-162">Die Konfiguration und der Code, der zum <xref:System.Activities.Tracking.CancelRequestedQuery> Abonnieren von Datensätzen verwendet wird, die mit dem Abbruch von Aktivitäten zusammenhängen, werden im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="394ab-162">The configuration and code used to subscribe to records related to activity cancellation using <xref:System.Activities.Tracking.CancelRequestedQuery> is shown in the following example.</span></span>

  ```xml
  <cancelRequestedQueries>
    <cancelRequestedQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />
  </cancelRequestedQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new CancelRequestedQuery()
          {
              ActivityName = "ProcessNotificationsActivity",
              ChildActivityName = "SendEmailActivity"
          }
      }
  };
  ```

- <span data-ttu-id="394ab-163"><xref:System.Activities.Tracking.CustomTrackingQuery> – Hiermit können Sie Ereignisse nachverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="394ab-163"><xref:System.Activities.Tracking.CustomTrackingQuery> - Use this to track events that you define in your code activities.</span></span> <span data-ttu-id="394ab-164">Die Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekte abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="394ab-164">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CustomTrackingRecord> objects.</span></span>

  <span data-ttu-id="394ab-165">Die Konfiguration und der Code zum Abonnieren von mit der benutzerdefinierten Nachverfolgung verknüpften Datensätzen mit <xref:System.Activities.Tracking.CustomTrackingQuery> werden im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="394ab-165">The configuration and code used to subscribe to records related to custom tracking records using <xref:System.Activities.Tracking.CustomTrackingQuery> is shown in the following example.</span></span>

  ```xml
  <customTrackingQueries>
    <customTrackingQuery name="EmailAddress" activityName="SendEmailActivity" />
  </customTrackingQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new CustomTrackingQuery()
          {
              Name = "EmailAddress",
              ActivityName = "SendEmailActivity"
          }
      }
  };
  ```

- <span data-ttu-id="394ab-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery> – Hiermit können Sie die Wiederaufnahme eines Lesezeichens in einer Workflowinstanz nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="394ab-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery> - Use this to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="394ab-167">Diese Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt <xref:System.Activities.Tracking.BookmarkResumptionRecord>-Objekte abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="394ab-167">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.BookmarkResumptionRecord> objects.</span></span>

  <span data-ttu-id="394ab-168">Die Konfiguration und der Code zum Abonnieren von mit der Wiederaufnahme von Lesezeichen verknüpften Datensätzen mithilfe von <xref:System.Activities.Tracking.BookmarkResumptionQuery> werden im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="394ab-168">The configuration and code used to subscribe to records related to bookmark resumption using <xref:System.Activities.Tracking.BookmarkResumptionQuery> is shown in the following example.</span></span>

  ```xml
  <bookmarkResumptionQueries>
    <bookmarkResumptionQuery name="SentEmailBookmark" />
  </bookmarkResumptionQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new BookmarkResumptionQuery()
          {
              Name = "sentEmailBookmark"
          }
      }
  };
  ```

### <a name="annotations"></a><span data-ttu-id="394ab-169">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="394ab-169">Annotations</span></span>

<span data-ttu-id="394ab-170">Anmerkungen ermöglichen es Ihnen, Überwachungsdatensätze mit einem beliebigen Wert zu markieren, der nach der Erstellung konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="394ab-170">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="394ab-171">Sie können z. B. mehrere Tracking-Datensätze in mehreren Workflows mit "Mail Server" == "Mail Server1" kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="394ab-171">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="394ab-172">Auf diese Weise können alle Datensätze mit diesem Tag einfach gefunden werden, wenn zu einem späteren Zeitpunkt Überwachungsdatensätze abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="394ab-172">This makes it easy to find all records with this tag when querying tracking records later.</span></span>

<span data-ttu-id="394ab-173">Damit dies funktioniert, wird einer Überwachungsabfrage eine Anmerkung hinzugefügt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="394ab-173">To accomplish this, an annotation is added to a tracking query as shown in the following example.</span></span>

```xml
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed"/>
  </states>
  <annotations>
    <annotation name="MailServer" value="Mail Server1"/>
  </annotations>
</activityStateQuery>
```

### <a name="how-to-create-a-tracking-profile"></a><span data-ttu-id="394ab-174">Erstellen eines Überwachungsprofils</span><span class="sxs-lookup"><span data-stu-id="394ab-174">How to Create a Tracking Profile</span></span>

<span data-ttu-id="394ab-175">Nachverfolgungsabfrageelemente werden verwendet, um ein Nachverfolgungsprofil mithilfe einer XML-Konfigurationsdatei oder [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] eines Codes zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="394ab-175">Tracking query elements are used to create a tracking profile using either an XML configuration file or [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] code.</span></span> <span data-ttu-id="394ab-176">Im Folgenden finden Sie ein Beispiel für ein mit einer Konfigurationsdatei erstelltes Überwachungsprofil.</span><span class="sxs-lookup"><span data-stu-id="394ab-176">Here is an example of a tracking profile created using a configuration file.</span></span>

```xml
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="Sample Tracking Profile ">
        <workflow activityDefinitionId="*">
          <!--Specify the tracking profile query elements to subscribe for tracking records-->
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```

> [!WARNING]
> <span data-ttu-id="394ab-177">Bei WF mit dem Workflowdiensthost wird das Überwachungsprofil in der Regel mit einer Konfigurationsdatei erstellt.</span><span class="sxs-lookup"><span data-stu-id="394ab-177">For a WF using the Workflow service host, the tracking profile is typically created using a configuration file.</span></span> <span data-ttu-id="394ab-178">Es ist auch möglich, ein Überwachungsprofil mit Code zu erstellen. Dazu wird die API für Überwachungsprofile und Überwachungsabfragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="394ab-178">It is also possible to create a tracking profile with code using the tracking profile and tracking query API.</span></span>

<span data-ttu-id="394ab-179">Ein Profil, das als XML-Konfigurationsdatei konfiguriert ist, wird mit einer Verhaltenserweiterung auf einen Überwachungsteilnehmer angewendet.</span><span class="sxs-lookup"><span data-stu-id="394ab-179">A profile configured as an XML configuration file is applied to a tracking participant using a behavior extension.</span></span> <span data-ttu-id="394ab-180">Dies wird einem WorkflowServiceHost hinzugefügt, wie im späteren Abschnitt [Konfigurieren der Nachverfolgung für einen Workflow](configuring-tracking-for-a-workflow.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="394ab-180">This is added to a WorkflowServiceHost as described in the later section [Configuring Tracking for a Workflow](configuring-tracking-for-a-workflow.md).</span></span>

<span data-ttu-id="394ab-181">Der Detailliertheitsgrad der Überwachungsdatensätze, die vom Host ausgegeben werden, wird von den Konfigurationseinstellungen im Überwachungsprofil bestimmt.</span><span class="sxs-lookup"><span data-stu-id="394ab-181">The verbosity of the tracking records emitted by the host is determined by configuration settings within the tracking profile.</span></span> <span data-ttu-id="394ab-182">Ein Überwachungsteilnehmer abonniert Überwachungsdatensätze, indem einem Überwachungsprofil Abfragen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="394ab-182">A tracking participant subscribes to tracking records by adding queries to a tracking profile.</span></span> <span data-ttu-id="394ab-183">Um alle Tracking-Datensätze zu abonnieren, muss das Überwachungsprofil alle Tracking-Abfragen angeben, die "\*in den Namensfeldern in jeder Abfrage verwenden.</span><span class="sxs-lookup"><span data-stu-id="394ab-183">To subscribe to all tracking records, the tracking profile needs to specify all tracking queries using "\*" in the name fields in each of the queries.</span></span>

<span data-ttu-id="394ab-184">Es folgen einige häufige Beispiele für Überwachungsprofile.</span><span class="sxs-lookup"><span data-stu-id="394ab-184">Here are some of the common examples of tracking profiles.</span></span>

- <span data-ttu-id="394ab-185">Ein Überwachungsprofil zum Abfragen von Workflowinstanz-Datensätzen und -fehlern</span><span class="sxs-lookup"><span data-stu-id="394ab-185">A tracking profile to obtain workflow instance records and faults.</span></span>

  ```xml
  <trackingProfile name="Instance and Fault Records">
    <workflow activityDefinitionId="*">
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="*" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
      <activityStateQueries>
        <activityStateQuery activityName="*">
          <states>
            <state name="Faulted"/>
          </states>
        </activityStateQuery>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
  ```

- <span data-ttu-id="394ab-186">Ein Überwachungsprofil zum Abfragen aller benutzerdefinierten Überwachungsdatensätze</span><span class="sxs-lookup"><span data-stu-id="394ab-186">A tracking profile to obtain all custom tracking records.</span></span>

  ```xml
  <trackingProfile name="Instance_And_Custom_Records">
    <workflow activityDefinitionId="*">
      <customTrackingQueries>
        <customTrackingQuery name="*" activityName="*" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
  ```

## <a name="see-also"></a><span data-ttu-id="394ab-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="394ab-187">See also</span></span>

- [<span data-ttu-id="394ab-188">SQL-Nachverfolgung</span><span class="sxs-lookup"><span data-stu-id="394ab-188">SQL Tracking</span></span>](./samples/sql-tracking.md)
- <span data-ttu-id="394ab-189">[Windows Server App Fabric-Überwachung](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="394ab-189">[Windows Server App Fabric Monitoring](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="394ab-190">[Überwachen von Anwendungen mit App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="394ab-190">[Monitoring Applications with App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
