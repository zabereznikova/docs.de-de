---
title: Überwachungsprofile
ms.date: 03/30/2017
ms.assetid: 22682566-1cd9-4672-9791-fb3523638e18
ms.openlocfilehash: 9217f25ba4499e7ff75020642be387aa79ba27bf
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837622"
---
# <a name="tracking-profiles"></a>Überwachungsprofile

Überwachungsprofile enthalten Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.

## <a name="tracking-profiles"></a>Überwachungsprofile

Mithilfe von Nachverfolgungsprofilen wird angegeben, welche Nachverfolgungsinformationen für eine Workflowinstanz ausgegeben werden. Wenn kein Profil angegeben wird, dann werden alle Nachverfolgungsereignisse ausgegeben. Wenn ein Profil angegeben ist, werden die Nachverfolgungsereignisse, die im Profil angegeben sind, ausgegeben. Je nach Überwachungsanforderungen können Sie ein Profil schreiben, das sehr allgemein gehalten ist und einen kleinen Satz von unspezifischen Zustandsänderungen eines Workflows abonniert. Umgekehrt ist es möglich, ein sehr ausführliches Profil zu erstellen, dessen resultierende Ereignisse umfangreich genug sind, um später einen detaillierten Ausführungsfluss zu rekonstruieren.

Überwachungs Profile werden als XML-Elemente in einer Standard-.NET Framework Konfigurationsdatei oder im Code angegeben. Das folgende Beispiel ist einem [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]-Überwachungsprofil in einer Konfigurationsdatei entnommen, die es einem Überwachungsteilnehmer ermöglicht, `Started`-Workflowereignisse und `Completed`-Workflowereignisse zu abonnieren.

```xml
<system.serviceModel>
    ...
    <tracking>
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

Im folgenden Beispiel wird das entsprechende Nachverfolgungsprofil dargestellt, das mithilfe von Code erstellt wurde.

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

Überwachungsdatensätze werden innerhalb eines Überwachungsprofils mit dem <xref:System.Activities.Tracking.ImplementationVisibility>-Attribut über den Sichtbarkeitsmodus gefiltert. Eine zusammengesetzte Aktivität ist eine allgemeine Aktivität mit weiteren Aktivitäten, die ihre Implementierung bilden. Der Sichtbarkeitsmodus gibt die von zusammengesetzten Aktivitäten in einer Workflowaktivität ausgegebenen Überwachungsdatensätze an. Damit wird bestimmt, ob Aktivitäten, aus denen die Implementierung besteht, nachverfolgt werden. Der Sichtbarkeitsmodus gilt für die Ebene des Überwachungsprofils. Die Filterung von Überwachungsdatensätzen für einzelne Aktivitäten eines Workflows wird von den Abfragen im Überwachungsprofil gesteuert. Weitere Informationen finden Sie im Abschnitt " **Überwachungs Profil-Abfrage Typen** " in diesem Dokument.

Die zwei Sichtbarkeitsmodi, die vom `implementationVisibility`-Attribut im Überwachungsprofil angegeben werden, sind `RootScope` und `All`. Durch Verwendung des `RootScope`-Modus werden Überwachungsdatensätze für Aktivitäten, die die Implementierung einer Aktivität bilden, unterdrückt, wenn der Stamm eines Workflows keine zusammengesetzte Aktivität ist. Dies bedeutet, dass nur die allgemeine Aktivität innerhalb der zusammengesetzten Aktivität nachverfolgt wird, wenn einem Workflow eine Aktivität hinzugefügt wird, die mit anderen Aktivitäten implementiert wird, und `implementationVisibility` auf RootScope festgelegt ist. Wenn eine Aktivität der Stamm des Workflows ist, stellt die Implementierung der Aktivität den Workflow selbst dar, und Überwachungsdatensätze werden für Aktivitäten ausgegeben, die die Implementierung bilden. Bei Verwendung des All-Modus werden die Überwachungsdatensätze für die Stammaktivität und alle zugehörigen zusammengesetzten Aktivitäten ausgegeben.

Beispiel: " *MyActivity* " ist eine zusammengesetzte Aktivität, deren Implementierung zwei Aktivitäten enthält, *Activity1* und *"activity2"* . Wenn diese Aktivität zu einem Workflow hinzugefügt wird und die Nachverfolgung mit einem Überwachungs Profil aktiviert ist, `implementationVisibility` auf `RootScope`festgelegt ist, werden nach Verfolgungs Datensätze nur für *MyActivity*ausgegeben. Für Aktivitäten *Activity1* und *"activity2"* werden jedoch keine Datensätze ausgegeben.

Wenn das `implementationVisibility`-Attribut für das Verfolgungs Profil jedoch auf `All`festgelegt ist, werden nach Verfolgungs Datensätze nicht nur für *MyActivity*ausgegeben, sondern auch für Aktivitäten *Activity1* und *"activity2"* .

Das `implementationVisibility`-Flag gilt für folgende Datensatztypen für die Nachverfolgung:

- ActivityStateRecord

- FaultPropagationRecord

- CancelRequestedRecord

- ActivityScheduledRecord

> [!NOTE]
> Von der Aktivitätsimplementierung ausgegebene CustomTrackingRecords werden von der implementationVisibility-Einstellung nicht herausgefiltert.

Die `implementationVisibility`-Funktionalität wird für das Überwachungsprofil auf folgende Weise als <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> in Code angegeben:

```csharp
TrackingProfile sampleTrackingProfile = new TrackingProfile()
{
    Name = "Sample Tracking Profile",
    ImplementationVisibility = ImplementationVisibility.RootScope
};
```

Die `implementationVisibility`-Funktionalität kann für das Überwachungsprofil auf folgende Weise als <xref:System.Activities.Tracking.ImplementationVisibility.All> in einer Konfigurationsdatei angegeben werden:

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

Die `ImplementationVisibility`-Einstellung ist für das Überwachungsprofil optional. Standardmäßig ist der Wert auf `RootScope` festgelegt. Bei den Werten für dieses Attribut muss die Groß-/Kleinschreibung beachtet werden.

### <a name="tracking-profile-query-types"></a>Abfragetypen für Überwachungsprofile

Überwachungsprofile werden als deklarative Abonnements für Überwachungsdatensätze angeordnet, die es Ihnen ermöglichen, bestimmte Überwachungsdatensätze aus der Workflowlaufzeit abzufragen. Es gibt mehrere Abfragetypen, mit denen Sie andere Klassen von <xref:System.Activities.Tracking.TrackingRecord>-Objekten abonnieren können. Überwachungsprofile können in der Konfiguration oder durch Code angegeben werden. Im Folgenden werden die häufigsten Abfragetypen aufgeführt:

- <xref:System.Activities.Tracking.WorkflowInstanceQuery> – Hiermit können Sie Änderungen am Workflowinstanz-Lebenszyklus nachverfolgen, z. B. die bereits erwähnten Optionen `Started` und `Completed`. <xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:

  - <xref:System.Activities.Tracking.WorkflowInstanceRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>

  Jeder Zustand, der abonniert werden kann, ist in der <xref:System.Activities.Tracking.WorkflowInstanceStates>-Klasse angegeben.

  Die Konfiguration bzw. der Code zum Abonnieren von Überwachungsdatensätzen auf Workflowinstanzebene für den `Started`-Instanzzustand mit dem <xref:System.Activities.Tracking.WorkflowInstanceQuery>-Objekt wird im folgenden Beispiel gezeigt.

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

- <xref:System.Activities.Tracking.ActivityStateQuery> – Hiermit können Sie die Lebenszyklusänderungen der Aktivitäten nachverfolgen, aus denen eine Workflowinstanz besteht. Beispielsweise können Sie nachverfolgen, wann die "E-Mail senden"-Aktivität innerhalb einer Workflow Instanz abgeschlossen wird. Diese Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt <xref:System.Activities.Tracking.ActivityStateRecord>-Objekte abonnieren kann. Die verfügbaren Zustände, die abonniert werden können, werden im <xref:System.Activities.Tracking.ActivityStates>-Objekt angegeben.

  Die Konfiguration und der Code zum Abonnieren von Überwachungsdatensätzen für den Aktivitätszustand, die das  <xref:System.Activities.Tracking.ActivityStateQuery>-Objekt für die `SendEmailActivity`-Aktivität verwenden, werden im folgenden Beispiel gezeigt.

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
  > Wenn mehrere activityStateQuery-Elemente denselben Namen haben, werden nur die Zustände im letzten Element im Nachverfolgungsprofil verwendet.

- <xref:System.Activities.Tracking.ActivityScheduledQuery> – Mit dieser Abfrage können Sie eine Aktivität nachverfolgen, die von einer übergeordneten Aktivität ausgeführt werden soll. Die Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt <xref:System.Activities.Tracking.ActivityScheduledRecord>-Objekte abonnieren kann.

  Die Konfiguration und der Code zum Abonnieren von Datensätzen, die mit der untergeordneten `SendEmailActivity`-Aktivität verknüpft sind, deren Planung mit dem <xref:System.Activities.Tracking.ActivityScheduledQuery>-Objekt erfolgt, wird im folgenden Beispiel gezeigt.

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

- <xref:System.Activities.Tracking.FaultPropagationQuery> – Hiermit können Sie die Behandlung von Fehlern nachverfolgen, die in einer Aktivität auftreten. Die Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt <xref:System.Activities.Tracking.FaultPropagationRecord>-Objekte abonnieren kann.

  Die Konfiguration und der Code zum Abonnieren von mit der Fehlerweitergabe verknüpften Datensätzen mithilfe von <xref:System.Activities.Tracking.FaultPropagationQuery> werden im folgenden Beispiel gezeigt.

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

- <xref:System.Activities.Tracking.CancelRequestedQuery> – Hiermit können Sie Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachverfolgen. Die Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt <xref:System.Activities.Tracking.CancelRequestedRecord>-Objekte abonnieren kann.

  Die Konfiguration und der Code zum Abonnieren von Datensätzen im Zusammenhang mit dem Aktivitäts Abbruch mithilfe von <xref:System.Activities.Tracking.CancelRequestedQuery> werden im folgenden Beispiel gezeigt.

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

- <xref:System.Activities.Tracking.CustomTrackingQuery> – Hiermit können Sie Ereignisse nachverfolgen, die Sie in den Codeaktivitäten definieren. Die Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekte abonnieren kann.

  Die Konfiguration und der Code zum Abonnieren von mit der benutzerdefinierten Nachverfolgung verknüpften Datensätzen mit <xref:System.Activities.Tracking.CustomTrackingQuery> werden im folgenden Beispiel gezeigt.

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

- <xref:System.Activities.Tracking.BookmarkResumptionQuery> – Hiermit können Sie die Wiederaufnahme eines Lesezeichens in einer Workflowinstanz nachverfolgen. Diese Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt <xref:System.Activities.Tracking.BookmarkResumptionRecord>-Objekte abonnieren kann.

  Die Konfiguration und der Code zum Abonnieren von mit der Wiederaufnahme von Lesezeichen verknüpften Datensätzen mithilfe von <xref:System.Activities.Tracking.BookmarkResumptionQuery> werden im folgenden Beispiel gezeigt.

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

### <a name="annotations"></a>Anmerkungen

Anmerkungen ermöglichen es Ihnen, Überwachungsdatensätze mit einem beliebigen Wert zu markieren, der nach der Erstellung konfiguriert werden kann. Beispielsweise kann es vorkommen, dass mehrere Überwachungsdaten Sätze in mehreren Workflows mit "Mail Server" = = "Mail Server1" gekennzeichnet werden. Auf diese Weise können alle Datensätze mit diesem Tag einfach gefunden werden, wenn zu einem späteren Zeitpunkt Überwachungsdatensätze abgefragt werden.

Damit dies funktioniert, wird einer Überwachungsabfrage eine Anmerkung hinzugefügt, wie im folgenden Beispiel gezeigt.

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

### <a name="how-to-create-a-tracking-profile"></a>Vorgehensweise für das Erstellen eines Überwachungsprofils

Mit Überwachungsabfrageelementen wird ein Überwachungsprofil erstellt. Dazu wird entweder eine XML-Konfigurationsdatei oder [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]-Code verwendet. Im Folgenden finden Sie ein Beispiel für ein mit einer Konfigurationsdatei erstelltes Überwachungsprofil.

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
> Bei WF mit dem Workflowdiensthost wird das Überwachungsprofil in der Regel mit einer Konfigurationsdatei erstellt. Es ist auch möglich, ein Überwachungsprofil mit Code zu erstellen. Dazu wird die API für Überwachungsprofile und Überwachungsabfragen verwendet.

Ein Profil, das als XML-Konfigurationsdatei konfiguriert ist, wird mit einer Verhaltenserweiterung auf einen Überwachungsteilnehmer angewendet. Dies wird einem Workflow Service Host wie im späteren Abschnitt [Konfigurieren der Überwachung für einen Workflow](configuring-tracking-for-a-workflow.md)beschrieben hinzugefügt.

Der Detailliertheitsgrad der Überwachungsdatensätze, die vom Host ausgegeben werden, wird von den Konfigurationseinstellungen im Überwachungsprofil bestimmt. Ein Überwachungsteilnehmer abonniert Überwachungsdatensätze, indem einem Überwachungsprofil Abfragen hinzugefügt werden. Um alle Überwachungsdaten Sätze zu abonnieren, muss das Überwachungs Profil alle nach Verfolgungs Abfragen mithilfe von "\*" in den namens Feldern der einzelnen Abfragen angeben.

Es folgen einige häufige Beispiele für Überwachungsprofile.

- Ein Überwachungsprofil zum Abfragen von Workflowinstanz-Datensätzen und -fehlern

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

- Ein Überwachungsprofil zum Abfragen aller benutzerdefinierten Überwachungsdatensätze

  ```xml
  <trackingProfile name="Instance_And_Custom_Records">
    <workflow activityDefinitionId="*">
      <customTrackingQueries>
        <customTrackingQuery name="*" activityName="*" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
  ```

## <a name="see-also"></a>Siehe auch

- [SQL-Nachverfolgung](./samples/sql-tracking.md)
- [Windows Server-App-Fabric-Überwachung](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [Überwachen von Anwendungen mit App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
