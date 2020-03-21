---
title: Benutzerdefinierte Nachverfolgung
ms.date: 03/30/2017
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
ms.openlocfilehash: 2b100b877bbc8c6d830f09a4a59decffde511511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182840"
---
# <a name="custom-tracking"></a><span data-ttu-id="1ebb7-102">Benutzerdefinierte Nachverfolgung</span><span class="sxs-lookup"><span data-stu-id="1ebb7-102">Custom Tracking</span></span>
<span data-ttu-id="1ebb7-103">Anhand dieses Beispiels wird veranschaulicht, wie eine benutzerdefinierte Nachverfolgungskomponente erstellt und der Inhalt der Nachverfolgungsdaten in die Konsole geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-103">This sample demonstrates how to create a custom tracking participant and write the contents of the tracking data to console.</span></span> <span data-ttu-id="1ebb7-104">Außerdem wird veranschaulicht, wie mit benutzerdefinierten Daten aufgefüllte <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekte ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-104">In addition, the sample demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects populated with user defined data.</span></span> <span data-ttu-id="1ebb7-105">Die konsolenbasierte Nachverfolgungskomponente filtert die vom Workflow ausgegebenen <xref:System.Activities.Tracking.TrackingRecord>-Objekte mit einem im Code erstellten Nachverfolgungsprofilobjekt.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-105">The console-based tracking participant filters the <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow using a tracking profile object created in code.</span></span>

## <a name="sample-details"></a><span data-ttu-id="1ebb7-106">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="1ebb7-106">Sample Details</span></span>
 <span data-ttu-id="1ebb7-107">Windows Workflow Foundation (WF) stellt eine Überwachungsinfrastruktur bereit, um die Ausführung einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-107">Windows Workflow Foundation (WF) provides a tracking infrastructure to track execution of a workflow instance.</span></span> <span data-ttu-id="1ebb7-108">Die Nachverfolgungslaufzeit implementiert eine Workflowinstanz, um Ereignisse in Verbindung mit dem Workflowlebenszyklus, Ereignisse aus den Workflowaktivitäten sowie benutzerdefinierte Nachverfolgungsereignisse auszugeben.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-108">The tracking runtime implements a workflow instance to emit events related to the workflow lifecycle, events from workflow activities and custom tracking events.</span></span> <span data-ttu-id="1ebb7-109">In der folgenden Tabelle sind die primären Komponenten der Überwachungsinfrastruktur aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-109">The following table details the primary components of the tracking infrastructure.</span></span>

|<span data-ttu-id="1ebb7-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="1ebb7-110">Component</span></span>|<span data-ttu-id="1ebb7-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ebb7-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="1ebb7-112">Überwachungslaufzeit</span><span class="sxs-lookup"><span data-stu-id="1ebb7-112">Tracking runtime</span></span>|<span data-ttu-id="1ebb7-113">Stellt die Infrastruktur bereit, um Überwachungsdatensätze auszugeben.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-113">Provides the infrastructure to emit tracking records.</span></span>|
|<span data-ttu-id="1ebb7-114">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="1ebb7-114">Tracking participants</span></span>|<span data-ttu-id="1ebb7-115">Verarbeitet die Nachverfolgungsdatensätze.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-115">Consumes the tracking records.</span></span> <span data-ttu-id="1ebb7-116">.NET Framework 4 wird mit einem Tracking-Teilnehmer ausgeliefert, der Tracking-Datensätze als ETW-Ereignisse (Event Tracing for Windows) schreibt.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-116">.NET Framework 4 ships with a tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span>|
|<span data-ttu-id="1ebb7-117">Überwachungsprofil</span><span class="sxs-lookup"><span data-stu-id="1ebb7-117">Tracking profile</span></span>|<span data-ttu-id="1ebb7-118">Ein Filtermechanismus, der einem Überwachungsteilnehmer das Abonnieren einer Teilmenge der Überwachungsdatensätze ermöglicht, die von einer Workflowinstanz ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-118">A filtering mechanism that allows a tracking participant to subscribe for a subset of the tracking records emitted from a workflow instance.</span></span>|

 <span data-ttu-id="1ebb7-119">In der folgenden Tabelle sind die Überwachungsdatensätze aufgeführt, die von der Workflowlaufzeit ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-119">The following table details the tracking records that the workflow runtime emits.</span></span>

|<span data-ttu-id="1ebb7-120">Nachverfolgungsdatensatz</span><span class="sxs-lookup"><span data-stu-id="1ebb7-120">Tracking Record</span></span>|<span data-ttu-id="1ebb7-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ebb7-121">Description</span></span>|
|---------------------|-----------------|
|<span data-ttu-id="1ebb7-122">Überwachungsdatensätze zur Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-122">Workflow instance tracking records.</span></span>|<span data-ttu-id="1ebb7-123">Beschreiben den Lebenszyklus der Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-123">Describes the life cycle of the workflow instance.</span></span> <span data-ttu-id="1ebb7-124">Wenn der Workflow gestartet oder abgeschlossen wird, wird beispielsweise ein Instanzdatensatz ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-124">For example, an instance record is emitted when the workflow starts or completes.</span></span>|
|<span data-ttu-id="1ebb7-125">Nachverfolgungsdatensätze zum Aktivitätszustand.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-125">Activity state Tracking Records.</span></span>|<span data-ttu-id="1ebb7-126">Führen Einzelheiten zur Aktivitätsausführung auf.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-126">Details activity execution.</span></span> <span data-ttu-id="1ebb7-127">Diese Datensätze geben den Zustand einer Workflowaktivität an, z. B. wenn eine Aktivität geplant oder abgeschlossen wird oder wenn ein Fehler ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-127">These records indicate the state of a workflow activity such as when an activity is scheduled or when the activity completes or when a fault is thrown.</span></span>|
|<span data-ttu-id="1ebb7-128">Datensatz zur Wiederaufnahme von Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-128">Bookmark resumption record.</span></span>|<span data-ttu-id="1ebb7-129">Wird immer dann ausgegeben, wenn ein Lesezeichen in einer Workflowinstanz wieder aufgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-129">Emitted whenever a bookmark within a workflow instance is resumed.</span></span>|
|<span data-ttu-id="1ebb7-130">Benutzerdefinierte Nachverfolgungsdatensätze.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-130">Custom Tracking Records.</span></span>|<span data-ttu-id="1ebb7-131">Ein Workflowautor kann benutzerdefinierte Nachverfolgungsdatensätze erstellen und in einer benutzerdefinierten Aktivität ausgeben.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-131">A workflow author can create Custom Tracking Records and emit them within the custom activity.</span></span>|

 <span data-ttu-id="1ebb7-132">Die Nachverfolgungskomponente abonniert eine Teilmenge der ausgegebenen <xref:System.Activities.Tracking.TrackingRecord>-Objekte mit Nachverfolgungsprofilen.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-132">The tracking participant subscribes for a subset of the emitted <xref:System.Activities.Tracking.TrackingRecord> objects using tracking profiles.</span></span> <span data-ttu-id="1ebb7-133">Ein Überwachungsprofil enthält Überwachungsabfragen, die das Abonnieren eines bestimmten Typs von Überwachungsdatensätzen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-133">A tracking profile contains tracking queries that allow subscribing for a particular tracking record type.</span></span> <span data-ttu-id="1ebb7-134">Überwachungsprofile können im Code oder in der Konfiguration angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-134">Tracking profiles can be specified in code or in configuration.</span></span>

### <a name="custom-tracking-participant"></a><span data-ttu-id="1ebb7-135">Benutzerdefinierte Nachverfolgungskomponente</span><span class="sxs-lookup"><span data-stu-id="1ebb7-135">Custom Tracking Participant</span></span>
 <span data-ttu-id="1ebb7-136">Die API der Nachverfolgungskomponente ermöglicht eine Erweiterung der Nachverfolgungslaufzeit mit einer vom Benutzer bereitgestellten Nachverfolgungskomponente. Diese kann benutzerdefinierte Logik enthalten, mit der von der Workflowlaufzeit ausgegebene <xref:System.Activities.Tracking.TrackingRecord>-Objekte behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-136">The tracking participant API allows extension of the tracking runtime with a user provided tracking participant that can include custom logic to handle <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow runtime.</span></span>

 <span data-ttu-id="1ebb7-137">Zum Schreiben einer Nachverfolgungskomponente muss der Benutzer <xref:System.Activities.Tracking.TrackingParticipant> implementieren.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-137">To write a tracking participant the user must implement <xref:System.Activities.Tracking.TrackingParticipant>.</span></span> <span data-ttu-id="1ebb7-138">Die <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>-Methode muss von der benutzerdefinierten Komponente implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-138">Specifically, the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method has to be implemented by the custom participant.</span></span> <span data-ttu-id="1ebb7-139">Diese Methode wird aufgerufen, wenn ein <xref:System.Activities.Tracking.TrackingRecord>-Objekt von der Workflowlaufzeit ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-139">This method is called when a <xref:System.Activities.Tracking.TrackingRecord> is emitted by the workflow runtime.</span></span>

```csharp
public abstract class TrackingParticipant
{
    protected TrackingParticipant();

    public virtual TrackingProfile TrackingProfile { get; set; }
    public abstract void Track(TrackingRecord record, TimeSpan timeout);
}
```

 <span data-ttu-id="1ebb7-140">Der vollständige Tracking-Teilnehmer wird in der ConsoleTrackingParticipant.cs-Datei implementiert.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-140">The complete tracking participant is implemented in the ConsoleTrackingParticipant.cs file.</span></span> <span data-ttu-id="1ebb7-141">Das folgende Codebeispiel <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> ist die Methode für den benutzerdefinierten Nachverfolgungsteilnehmer.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-141">The following code example is the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method for the custom tracking participant.</span></span>

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

 <span data-ttu-id="1ebb7-142">Im folgenden Codebeispiel wird die Konsolenkomponente der Workflowaufrufinstanz hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-142">The following code example adds the console participant to the workflow invoker.</span></span>

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

### <a name="emitting-custom-tracking-records"></a><span data-ttu-id="1ebb7-143">Ausgeben von benutzerdefinierten Nachverfolgungsdatensätzen</span><span class="sxs-lookup"><span data-stu-id="1ebb7-143">Emitting Custom Tracking Records</span></span>
 <span data-ttu-id="1ebb7-144">In diesem Beispiel wird auch die Fähigkeit zur Ausgabe von <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekten aus einer benutzerdefinierten Workflowaktivität veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1ebb7-144">This sample also demonstrates the ability to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects from a custom workflow activity:</span></span>

- <span data-ttu-id="1ebb7-145">Die <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekte werden erstellt und mit benutzerdefinierten Daten aufgefüllt, die mit dem Datensatz ausgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-145">The <xref:System.Activities.Tracking.CustomTrackingRecord> objects are created and populated with user-defined data that is desired to be emitted with the record.</span></span>

- <span data-ttu-id="1ebb7-146">Der <xref:System.Activities.Tracking.CustomTrackingRecord> wird durch Aufrufen der Track-Methode der <xref:System.Activities.ActivityContext>emittiert.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-146">The <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted by calling the track method of the <xref:System.Activities.ActivityContext>.</span></span>

 <span data-ttu-id="1ebb7-147">Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekte innerhalb einer benutzerdefinierten Aktivität ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-147">The following example demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects within a custom activity.</span></span>

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

#### <a name="to-use-this-sample"></a><span data-ttu-id="1ebb7-148">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ebb7-148">To use this sample</span></span>

1. <span data-ttu-id="1ebb7-149">Öffnen Sie mit Visual Studio 2010 die Lösungsdatei CustomTrackingSample.sln.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-149">Using Visual Studio 2010, open the CustomTrackingSample.sln solution file.</span></span>

2. <span data-ttu-id="1ebb7-150">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-150">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="1ebb7-151">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-151">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ebb7-152">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1ebb7-153">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-153">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1ebb7-154">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1ebb7-155">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1ebb7-155">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a><span data-ttu-id="1ebb7-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ebb7-156">See also</span></span>

- <span data-ttu-id="1ebb7-157">[AppFabric-Überwachungsbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="1ebb7-157">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
