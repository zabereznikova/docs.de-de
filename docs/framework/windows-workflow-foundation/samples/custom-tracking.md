---
title: Benutzerdefinierte Nachverfolgung
ms.date: 03/30/2017
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
ms.openlocfilehash: 7e275af046013dcd76cb61c25ace1d96fd7e4b93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307622"
---
# <a name="custom-tracking"></a><span data-ttu-id="0cb60-102">Benutzerdefinierte Nachverfolgung</span><span class="sxs-lookup"><span data-stu-id="0cb60-102">Custom Tracking</span></span>
<span data-ttu-id="0cb60-103">Anhand dieses Beispiels wird veranschaulicht, wie eine benutzerdefinierte Nachverfolgungskomponente erstellt und der Inhalt der Nachverfolgungsdaten in die Konsole geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="0cb60-103">This sample demonstrates how to create a custom tracking participant and write the contents of the tracking data to console.</span></span> <span data-ttu-id="0cb60-104">Außerdem wird veranschaulicht, wie mit benutzerdefinierten Daten aufgefüllte <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekte ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0cb60-104">In addition, the sample demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects populated with user defined data.</span></span> <span data-ttu-id="0cb60-105">Die konsolenbasierte Nachverfolgungskomponente filtert die vom Workflow ausgegebenen <xref:System.Activities.Tracking.TrackingRecord>-Objekte mit einem im Code erstellten Nachverfolgungsprofilobjekt.</span><span class="sxs-lookup"><span data-stu-id="0cb60-105">The console-based tracking participant filters the <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow using a tracking profile object created in code.</span></span>

## <a name="sample-details"></a><span data-ttu-id="0cb60-106">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="0cb60-106">Sample Details</span></span>
 <span data-ttu-id="0cb60-107">Windows Workflow Foundation (WF) stellt eine Überwachungsinfrastruktur, um die Ausführung einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="0cb60-107">Windows Workflow Foundation (WF) provides a tracking infrastructure to track execution of a workflow instance.</span></span> <span data-ttu-id="0cb60-108">Die Nachverfolgungslaufzeit implementiert eine Workflowinstanz, um Ereignisse in Verbindung mit dem Workflowlebenszyklus, Ereignisse aus den Workflowaktivitäten sowie benutzerdefinierte Nachverfolgungsereignisse auszugeben.</span><span class="sxs-lookup"><span data-stu-id="0cb60-108">The tracking runtime implements a workflow instance to emit events related to the workflow lifecycle, events from workflow activities and custom tracking events.</span></span> <span data-ttu-id="0cb60-109">In der folgenden Tabelle sind die primären Komponenten der Überwachungsinfrastruktur aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0cb60-109">The following table details the primary components of the tracking infrastructure.</span></span>

|<span data-ttu-id="0cb60-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="0cb60-110">Component</span></span>|<span data-ttu-id="0cb60-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0cb60-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="0cb60-112">Überwachungslaufzeit</span><span class="sxs-lookup"><span data-stu-id="0cb60-112">Tracking runtime</span></span>|<span data-ttu-id="0cb60-113">Stellt die Infrastruktur bereit, um Überwachungsdatensätze auszugeben.</span><span class="sxs-lookup"><span data-stu-id="0cb60-113">Provides the infrastructure to emit tracking records.</span></span>|
|<span data-ttu-id="0cb60-114">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="0cb60-114">Tracking participants</span></span>|<span data-ttu-id="0cb60-115">Verarbeitet die Nachverfolgungsdatensätze.</span><span class="sxs-lookup"><span data-stu-id="0cb60-115">Consumes the tracking records.</span></span> [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] <span data-ttu-id="0cb60-116">wird mit einem Nachverfolgungsteilnehmer geliefert, der Nachverfolgungsdatensätze als Ereignisse der Ereignisablaufverfolgung für Windows (ETW) schreibt.</span><span class="sxs-lookup"><span data-stu-id="0cb60-116">ships with a tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span>|
|<span data-ttu-id="0cb60-117">Überwachungsprofil</span><span class="sxs-lookup"><span data-stu-id="0cb60-117">Tracking profile</span></span>|<span data-ttu-id="0cb60-118">Ein Filtermechanismus, der einem Überwachungsteilnehmer das Abonnieren einer Teilmenge der Überwachungsdatensätze ermöglicht, die von einer Workflowinstanz ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0cb60-118">A filtering mechanism that allows a tracking participant to subscribe for a subset of the tracking records emitted from a workflow instance.</span></span>|

 <span data-ttu-id="0cb60-119">In der folgenden Tabelle sind die Überwachungsdatensätze aufgeführt, die von der Workflowlaufzeit ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0cb60-119">The following table details the tracking records that the workflow runtime emits.</span></span>

|<span data-ttu-id="0cb60-120">Nachverfolgungsdatensatz</span><span class="sxs-lookup"><span data-stu-id="0cb60-120">Tracking Record</span></span>|<span data-ttu-id="0cb60-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0cb60-121">Description</span></span>|
|---------------------|-----------------|
|<span data-ttu-id="0cb60-122">Überwachungsdatensätze zur Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="0cb60-122">Workflow instance tracking records.</span></span>|<span data-ttu-id="0cb60-123">Beschreiben den Lebenszyklus der Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="0cb60-123">Describes the life cycle of the workflow instance.</span></span> <span data-ttu-id="0cb60-124">Wenn der Workflow gestartet oder abgeschlossen wird, wird beispielsweise ein Instanzdatensatz ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="0cb60-124">For example, an instance record is emitted when the workflow starts or completes.</span></span>|
|<span data-ttu-id="0cb60-125">Nachverfolgungsdatensätze zum Aktivitätszustand.</span><span class="sxs-lookup"><span data-stu-id="0cb60-125">Activity state Tracking Records.</span></span>|<span data-ttu-id="0cb60-126">Führen Einzelheiten zur Aktivitätsausführung auf.</span><span class="sxs-lookup"><span data-stu-id="0cb60-126">Details activity execution.</span></span> <span data-ttu-id="0cb60-127">Diese Datensätze geben den Zustand einer Workflowaktivität an, z. B. wenn eine Aktivität geplant oder abgeschlossen wird oder wenn ein Fehler ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0cb60-127">These records indicate the state of a workflow activity such as when an activity is scheduled or when the activity completes or when a fault is thrown.</span></span>|
|<span data-ttu-id="0cb60-128">Datensatz zur Wiederaufnahme von Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="0cb60-128">Bookmark resumption record.</span></span>|<span data-ttu-id="0cb60-129">Wird immer dann ausgegeben, wenn ein Lesezeichen in einer Workflowinstanz wieder aufgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="0cb60-129">Emitted whenever a bookmark within a workflow instance is resumed.</span></span>|
|<span data-ttu-id="0cb60-130">Benutzerdefinierte Nachverfolgungsdatensätze.</span><span class="sxs-lookup"><span data-stu-id="0cb60-130">Custom Tracking Records.</span></span>|<span data-ttu-id="0cb60-131">Ein Workflowautor kann benutzerdefinierte Nachverfolgungsdatensätze erstellen und in einer benutzerdefinierten Aktivität ausgeben.</span><span class="sxs-lookup"><span data-stu-id="0cb60-131">A workflow author can create Custom Tracking Records and emit them within the custom activity.</span></span>|

 <span data-ttu-id="0cb60-132">Die Nachverfolgungskomponente abonniert eine Teilmenge der ausgegebenen <xref:System.Activities.Tracking.TrackingRecord>-Objekte mit Nachverfolgungsprofilen.</span><span class="sxs-lookup"><span data-stu-id="0cb60-132">The tracking participant subscribes for a subset of the emitted <xref:System.Activities.Tracking.TrackingRecord> objects using tracking profiles.</span></span> <span data-ttu-id="0cb60-133">Ein Überwachungsprofil enthält Überwachungsabfragen, die das Abonnieren eines bestimmten Typs von Überwachungsdatensätzen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0cb60-133">A tracking profile contains tracking queries that allow subscribing for a particular tracking record type.</span></span> <span data-ttu-id="0cb60-134">Überwachungsprofile können im Code oder in der Konfiguration angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0cb60-134">Tracking profiles can be specified in code or in configuration.</span></span>

### <a name="custom-tracking-participant"></a><span data-ttu-id="0cb60-135">Benutzerdefinierte Nachverfolgungskomponente</span><span class="sxs-lookup"><span data-stu-id="0cb60-135">Custom Tracking Participant</span></span>
 <span data-ttu-id="0cb60-136">Die API der Nachverfolgungskomponente ermöglicht eine Erweiterung der Nachverfolgungslaufzeit mit einer vom Benutzer bereitgestellten Nachverfolgungskomponente. Diese kann benutzerdefinierte Logik enthalten, mit der von der Workflowlaufzeit ausgegebene <xref:System.Activities.Tracking.TrackingRecord>-Objekte behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="0cb60-136">The tracking participant API allows extension of the tracking runtime with a user provided tracking participant that can include custom logic to handle <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow runtime.</span></span>

 <span data-ttu-id="0cb60-137">Zum Schreiben einer Nachverfolgungskomponente muss der Benutzer <xref:System.Activities.Tracking.TrackingParticipant> implementieren.</span><span class="sxs-lookup"><span data-stu-id="0cb60-137">To write a tracking participant the user must implement <xref:System.Activities.Tracking.TrackingParticipant>.</span></span> <span data-ttu-id="0cb60-138">Die <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>-Methode muss von der benutzerdefinierten Komponente implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="0cb60-138">Specifically, the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method has to be implemented by the custom participant.</span></span> <span data-ttu-id="0cb60-139">Diese Methode wird aufgerufen, wenn ein <xref:System.Activities.Tracking.TrackingRecord>-Objekt von der Workflowlaufzeit ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0cb60-139">This method is called when a <xref:System.Activities.Tracking.TrackingRecord> is emitted by the workflow runtime.</span></span>

```csharp
public abstract class TrackingParticipant
{
    protected TrackingParticipant();

    public virtual TrackingProfile TrackingProfile { get; set; }
    public abstract void Track(TrackingRecord record, TimeSpan timeout);
}
```

 <span data-ttu-id="0cb60-140">Die vollständige Nachverfolgungskomponente wird in der Datei "ConsoleTrackingParticipant.cs" implementiert. Das folgende Codebeispiel enthält die <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>-Methode für die benutzerdefinierte Nachverfolgungskomponente.</span><span class="sxs-lookup"><span data-stu-id="0cb60-140">The complete tracking participant is implemented in the ConsoleTrackingParticipant.cs file.The following code example is the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method for the custom tracking participant.</span></span>

```csharp
protected override void Track(TrackingRecord record, TimeSpan timeout)
{
    ...
    WorkflowInstanceRecord workflowInstanceRecord = record as WorkflowInstanceRecord;
    if (workflowInstanceRecord != null)
    {
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " Workflow InstanceID: {0} Workflow instance state: {1}",
            record.InstanceId, workflowInstanceRecord.State));
    }

    ActivityStateRecord activityStateRecord = record as ActivityStateRecord;
    if (activityStateRecord != null)
    {
        IDictionary<String, object> variables = activityStateRecord.Variables;
        StringBuilder vars = new StringBuilder();

        if (variables.Count > 0)
        {
            vars.AppendLine("\n\tVariables:");
            foreach (KeyValuePair<string, object> variable in variables)
            {
                vars.AppendLine(String.Format(
                    "\t\tName: {0} Value: {1}", variable.Key, variable.Value));
            }
        }
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " :Activity DisplayName: {0} :ActivityInstanceState: {1} {2}",
                activityStateRecord.Activity.Name, activityStateRecord.State,
            ((variables.Count > 0) ? vars.ToString() : String.Empty)));
    }

    CustomTrackingRecord customTrackingRecord = record as CustomTrackingRecord;

    if ((customTrackingRecord != null) && (customTrackingRecord.Data.Count > 0))
    {
        ...
    }
    Console.WriteLine();

}
```

 <span data-ttu-id="0cb60-141">Im folgenden Codebeispiel wird die Konsolenkomponente der Workflowaufrufinstanz hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0cb60-141">The following code example adds the console participant to the workflow invoker.</span></span>

```csharp
ConsoleTrackingParticipant customTrackingParticipant = new ConsoleTrackingParticipant()
{
    ...
    // The tracking profile is set here, refer to Program.CS
...
}

WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
```

### <a name="emitting-custom-tracking-records"></a><span data-ttu-id="0cb60-142">Ausgeben von benutzerdefinierten Nachverfolgungsdatensätzen</span><span class="sxs-lookup"><span data-stu-id="0cb60-142">Emitting Custom Tracking Records</span></span>
 <span data-ttu-id="0cb60-143">In diesem Beispiel wird auch die Fähigkeit zur Ausgabe von <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekten aus einer benutzerdefinierten Workflowaktivität veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0cb60-143">This sample also demonstrates the ability to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects from a custom workflow activity:</span></span>

-   <span data-ttu-id="0cb60-144">Die <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekte werden erstellt und mit benutzerdefinierten Daten aufgefüllt, die mit dem Datensatz ausgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0cb60-144">The <xref:System.Activities.Tracking.CustomTrackingRecord> objects are created and populated with user-defined data that is desired to be emitted with the record.</span></span>

-   <span data-ttu-id="0cb60-145">Die <xref:System.Activities.Tracking.CustomTrackingRecord> wird durch Aufrufen der Nachverfolgungsmethode des ausgegeben, die <xref:System.Activities.ActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="0cb60-145">The <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted by calling the track method of the <xref:System.Activities.ActivityContext>.</span></span>

 <span data-ttu-id="0cb60-146">Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekte innerhalb einer benutzerdefinierten Aktivität ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0cb60-146">The following example demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects within a custom activity.</span></span>

```csharp
// Create the Custom Tracking Record
CustomTrackingRecord customRecord = new CustomTrackingRecord("OrderIn")
{
    Data =
    {
        {"OrderId", 200},
        {"OrderDate", "20 Aug 2001"}
    }
};

// Emit custom tracking record
context.Track(customRecord);
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="0cb60-147">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="0cb60-147">To use this sample</span></span>

1. <span data-ttu-id="0cb60-148">Öffnen Sie die Projektmappendatei "CustomTrackingSample.sln" mit Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="0cb60-148">Using Visual Studio 2010, open the CustomTrackingSample.sln solution file.</span></span>

2. <span data-ttu-id="0cb60-149">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0cb60-149">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="0cb60-150">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0cb60-150">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="0cb60-151">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="0cb60-151">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0cb60-152">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0cb60-152">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0cb60-153">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="0cb60-153">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0cb60-154">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0cb60-154">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a><span data-ttu-id="0cb60-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cb60-155">See also</span></span>

- [<span data-ttu-id="0cb60-156">AppFabric-Überwachungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="0cb60-156">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
