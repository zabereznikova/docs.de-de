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
# <a name="custom-tracking"></a>Benutzerdefinierte Nachverfolgung
Anhand dieses Beispiels wird veranschaulicht, wie eine benutzerdefinierte Nachverfolgungskomponente erstellt und der Inhalt der Nachverfolgungsdaten in die Konsole geschrieben wird. Außerdem wird veranschaulicht, wie mit benutzerdefinierten Daten aufgefüllte <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekte ausgegeben werden. Die konsolenbasierte Nachverfolgungskomponente filtert die vom Workflow ausgegebenen <xref:System.Activities.Tracking.TrackingRecord>-Objekte mit einem im Code erstellten Nachverfolgungsprofilobjekt.

## <a name="sample-details"></a>Beispieldetails
 Windows Workflow Foundation (WF) stellt eine Überwachungsinfrastruktur bereit, um die Ausführung einer Workflowinstanz nachzuverfolgen. Die Nachverfolgungslaufzeit implementiert eine Workflowinstanz, um Ereignisse in Verbindung mit dem Workflowlebenszyklus, Ereignisse aus den Workflowaktivitäten sowie benutzerdefinierte Nachverfolgungsereignisse auszugeben. In der folgenden Tabelle sind die primären Komponenten der Überwachungsinfrastruktur aufgeführt.

|Komponente|Beschreibung|
|---------------|-----------------|
|Überwachungslaufzeit|Stellt die Infrastruktur bereit, um Überwachungsdatensätze auszugeben.|
|Überwachungsteilnehmer|Verarbeitet die Nachverfolgungsdatensätze. .NET Framework 4 wird mit einem Tracking-Teilnehmer ausgeliefert, der Tracking-Datensätze als ETW-Ereignisse (Event Tracing for Windows) schreibt.|
|Überwachungsprofil|Ein Filtermechanismus, der einem Überwachungsteilnehmer das Abonnieren einer Teilmenge der Überwachungsdatensätze ermöglicht, die von einer Workflowinstanz ausgegeben werden.|

 In der folgenden Tabelle sind die Überwachungsdatensätze aufgeführt, die von der Workflowlaufzeit ausgegeben werden.

|Nachverfolgungsdatensatz|Beschreibung|
|---------------------|-----------------|
|Überwachungsdatensätze zur Workflowinstanz.|Beschreiben den Lebenszyklus der Workflowinstanz. Wenn der Workflow gestartet oder abgeschlossen wird, wird beispielsweise ein Instanzdatensatz ausgegeben.|
|Nachverfolgungsdatensätze zum Aktivitätszustand.|Führen Einzelheiten zur Aktivitätsausführung auf. Diese Datensätze geben den Zustand einer Workflowaktivität an, z. B. wenn eine Aktivität geplant oder abgeschlossen wird oder wenn ein Fehler ausgelöst wird.|
|Datensatz zur Wiederaufnahme von Lesezeichen.|Wird immer dann ausgegeben, wenn ein Lesezeichen in einer Workflowinstanz wieder aufgenommen wird.|
|Benutzerdefinierte Nachverfolgungsdatensätze.|Ein Workflowautor kann benutzerdefinierte Nachverfolgungsdatensätze erstellen und in einer benutzerdefinierten Aktivität ausgeben.|

 Die Nachverfolgungskomponente abonniert eine Teilmenge der ausgegebenen <xref:System.Activities.Tracking.TrackingRecord>-Objekte mit Nachverfolgungsprofilen. Ein Überwachungsprofil enthält Überwachungsabfragen, die das Abonnieren eines bestimmten Typs von Überwachungsdatensätzen ermöglichen. Überwachungsprofile können im Code oder in der Konfiguration angegeben werden.

### <a name="custom-tracking-participant"></a>Benutzerdefinierte Nachverfolgungskomponente
 Die API der Nachverfolgungskomponente ermöglicht eine Erweiterung der Nachverfolgungslaufzeit mit einer vom Benutzer bereitgestellten Nachverfolgungskomponente. Diese kann benutzerdefinierte Logik enthalten, mit der von der Workflowlaufzeit ausgegebene <xref:System.Activities.Tracking.TrackingRecord>-Objekte behandelt werden.

 Zum Schreiben einer Nachverfolgungskomponente muss der Benutzer <xref:System.Activities.Tracking.TrackingParticipant> implementieren. Die <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>-Methode muss von der benutzerdefinierten Komponente implementiert werden. Diese Methode wird aufgerufen, wenn ein <xref:System.Activities.Tracking.TrackingRecord>-Objekt von der Workflowlaufzeit ausgegeben wird.

```csharp
public abstract class TrackingParticipant
{
    protected TrackingParticipant();

    public virtual TrackingProfile TrackingProfile { get; set; }
    public abstract void Track(TrackingRecord record, TimeSpan timeout);
}
```

 Der vollständige Tracking-Teilnehmer wird in der ConsoleTrackingParticipant.cs-Datei implementiert. Das folgende Codebeispiel <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> ist die Methode für den benutzerdefinierten Nachverfolgungsteilnehmer.

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

 Im folgenden Codebeispiel wird die Konsolenkomponente der Workflowaufrufinstanz hinzugefügt.

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

### <a name="emitting-custom-tracking-records"></a>Ausgeben von benutzerdefinierten Nachverfolgungsdatensätzen
 In diesem Beispiel wird auch die Fähigkeit zur Ausgabe von <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekten aus einer benutzerdefinierten Workflowaktivität veranschaulicht:

- Die <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekte werden erstellt und mit benutzerdefinierten Daten aufgefüllt, die mit dem Datensatz ausgegeben werden sollen.

- Der <xref:System.Activities.Tracking.CustomTrackingRecord> wird durch Aufrufen der Track-Methode der <xref:System.Activities.ActivityContext>emittiert.

 Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekte innerhalb einer benutzerdefinierten Aktivität ausgegeben werden.

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

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie mit Visual Studio 2010 die Lösungsdatei CustomTrackingSample.sln.

2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

3. Drücken Sie STRG+F5, um die Projektmappe auszuführen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Überwachungsbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
