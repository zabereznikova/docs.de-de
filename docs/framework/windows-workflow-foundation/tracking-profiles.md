---
title: "&#220;berwachungsprofile | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 22682566-1cd9-4672-9791-fb3523638e18
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# &#220;berwachungsprofile
Überwachungsprofile enthalten Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.  
  
## Überwachungsprofile  
 Mithilfe von Nachverfolgungsprofilen wird angegeben, welche Nachverfolgungsinformationen für eine Workflowinstanz ausgegeben werden.Wenn kein Profil angegeben wird, dann werden alle Nachverfolgungsereignisse ausgegeben.Wenn ein Profil angegeben ist, werden die Nachverfolgungsereignisse, die im Profil angegeben sind, ausgegeben.Je nach Überwachungsanforderungen können Sie ein Profil schreiben, das sehr allgemein gehalten ist und einen kleinen Satz von unspezifischen Zustandsänderungen eines Workflows abonniert.Umgekehrt ist es möglich, ein sehr ausführliches Profil zu erstellen, dessen resultierende Ereignisse umfangreich genug sind, um später einen detaillierten Ausführungsfluss zu rekonstruieren.  
  
 Überwachungsprofile sind XML\-Elemente, die innerhalb einer standardmäßigen [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]\-Konfigurationsdatei oder in Code angegeben werden.Das folgende Beispiel ist einem [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]\-Überwachungsprofil in einer Konfigurationsdatei entnommen, die es einem Überwachungsteilnehmer ermöglicht, `Started`\-Workflowereignisse und `Completed`\-Workflowereignisse zu abonnieren.  
  
```  
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
  
 Überwachungsdatensätze werden innerhalb eines Überwachungsprofils mit dem <xref:System.Activities.Tracking.ImplementationVisibility>\-Attribut über den Sichtbarkeitsmodus gefiltert.Eine zusammengesetzte Aktivität ist eine allgemeine Aktivität mit weiteren Aktivitäten, die ihre Implementierung bilden.Der Sichtbarkeitsmodus gibt die von zusammengesetzten Aktivitäten in einer Workflowaktivität ausgegebenen Überwachungsdatensätze an. Damit wird bestimmt, ob Aktivitäten, aus denen die Implementierung besteht, nachverfolgt werden.Der Sichtbarkeitsmodus gilt für die Ebene des Überwachungsprofils.Die Filterung von Nachverfolgungsdatensätzen für einzelne Aktivitäten eines Workflows wird von den Abfragen im Nachverfolgungsprofil gesteuert.Weitere Informationen finden Sie im Abschnitt**Abfragetypen für Überwachungsprofile** in diesem Dokument.  
  
 Die zwei Sichtbarkeitsmodi, die vom `implementationVisibility`\-Attribut im Überwachungsprofil angegeben werden, sind `RootScope` und `All`.Durch Verwendung des `RootScope`\-Modus werden Überwachungsdatensätze für Aktivitäten, die die Implementierung einer Aktivität bilden, unterdrückt, wenn der Stamm eines Workflows keine zusammengesetzte Aktivität ist.Dies bedeutet, dass nur die allgemeine Aktivität innerhalb der zusammengesetzten Aktivität nachverfolgt wird, wenn einem Workflow eine Aktivität hinzugefügt wird, die mit anderen Aktivitäten implementiert wird, und `implementationVisibility` auf RootScope festgelegt ist.Wenn eine Aktivität der Stamm des Workflows ist, stellt die Implementierung der Aktivität den Workflow selbst dar, und Überwachungsdatensätze werden für Aktivitäten ausgegeben, die die Implementierung bilden.Bei Verwendung des All\-Modus werden die Überwachungsdatensätze für die Stammaktivität und alle zugehörigen zusammengesetzten Aktivitäten ausgegeben.  
  
 Beispiel: *MyActivity* ist eine zusammengesetzte Aktivität, deren Implementierung die zwei Aktivitäten *Activity1* und *Activity2* enthält.Wenn diese Aktivität einem Workflow hinzugefügt wird und die Nachverfolgung mit einem Überwachungsprofil aktiviert wird, bei dem `implementationVisibility` zu `RootScope` festgelegt wurde, werden Überwachungsdatensätze nur für *MyActivity* ausgegeben.Für die Aktivitäten *Activity1* und *Activity2* werden jedoch keine Datensätze ausgegeben.  
  
 Wurde das `implementationVisisbility`\-Attribut hingegen für das Überwachungsprofil auf `All` festgelegt, werden Überwachungsdatensätze nicht nur für *MyActivity* ausgegeben, sondern auch für die Aktivitäten *Activity1* und *Activity2*.  
  
 Das `implementationVisibility`\-Flag gilt für folgende Datensatztypen für die Nachverfolgung:  
  
-   ActivityStateRecord  
  
-   FaultPropagationRecord  
  
-   CancelRequestedRecord  
  
-   ActivityScheduledRecord  
  
> [!NOTE]
>  Von der Aktivitätsimplementierung ausgegebene CustomTrackingRecords werden von der implementationVisibility\-Einstellung nicht herausgefiltert.  
  
 Die `implementationVisibility`\-Funktionalität wird für das Nachverfolgungsprofil im Code als <xref:System.Activities.Tracking.ImplementationVisibility> wie folgt angegeben:  
  
```  
TrackingProfile sampleTrackingProfile = new TrackingProfile()  
{  
    Name = "Sample Tracking Profile",  
    ImplementationVisibility = ImplementationVisibility.RootScope  
};  
  
```  
  
 Die `implementationVisibility`\-Funktionalität wird als <xref:System.Activities.Tracking.ImplementationVisibility> für das Nachverfolgungsprofil in einer Konfigurationsdatei wie folgt angegeben:  
  
```  
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
  
 Die `ImplementationVisibility`\-Einstellung ist für das Überwachungsprofil optional.Standardmäßig ist der Wert auf `RootScope` festgelegt.Bei den Werten für dieses Attribut muss die Groß\-\/Kleinschreibung beachtet werden.  
  
### Abfragetypen für Überwachungsprofile  
 Überwachungsprofile werden als deklarative Abonnements für Überwachungsdatensätze angeordnet, die es Ihnen ermöglichen, bestimmte Überwachungsdatensätze aus der Workflowlaufzeit abzufragen.Es gibt mehrere Abfragetypen, mit denen Sie andere Klassen von <xref:System.Activities.Tracking.TrackingRecord>\-Objekten abonnieren können.Überwachungsprofile können in der Konfiguration oder durch Code angegeben werden.Im Folgenden werden die häufigsten Abfragetypen aufgeführt:  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceQuery> – Hiermit können Sie Änderungen am Workflowinstanz\-Lebenszyklus nachverfolgen, z. B. die bereits erwähnten Optionen `Started` und `Completed`.<xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>\-Objekte verwendet:  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
     Jeder Zustand, der abonniert werden kann, ist in der <xref:System.Activities.Tracking.WorkflowInstanceStates>\-Klasse angegeben.  
  
     Die Konfiguration bzw. der Code zum Abonnieren von Überwachungsdatensätzen auf Workflowinstanzebene für den `Started`\-Instanzzustand mit dem <xref:System.Activities.Tracking.WorkflowInstanceQuery>\-Objekt wird im folgenden Beispiel gezeigt.  
  
    ```  
    <workflowInstanceQueries>  
        <workflowInstanceQuery>  
          <states>  
            <state name="Started"/>  
          </states>  
        </workflowInstanceQuery>  
    </workflowInstanceQueries>  
  
    ```  
  
    ```  
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
  
-   <xref:System.Activities.Tracking.ActivityStateQuery> – Hiermit können Sie die Lebenszyklusänderungen der Aktivitäten nachverfolgen, aus denen eine Workflowinstanz besteht.Beispielsweise könnten Sie jede abgeschlossene Aktivität der Art "E\-Mail senden" innerhalb einer Workflowinstanz nachverfolgen.Diese Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>\-Objekt <xref:System.Activities.Tracking.ActivityStateRecord>\-Objekte abonnieren kann.Die verfügbaren Zustände, die abonniert werden können, werden im <xref:System.Activities.Tracking.ActivityStates>\-Objekt angegeben.  
  
     Die Konfiguration und der Code zum Abonnieren von Überwachungsdatensätzen für den Aktivitätszustand, die das  <xref:System.Activities.Tracking.ActivityStateQuery>\-Objekt für die `SendEmailActivity`\-Aktivität verwenden, werden im folgenden Beispiel gezeigt.  
  
    ```  
    <activityStateQueries>  
      <activityStateQuery activityName="SendEmailActivity">  
        <states>  
          <state name="Closed"/>  
        </states>  
      </activityStateQuery>  
    </activityStateQueries>  
  
    ```  
  
    ```  
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
    >  Wenn mehrere activityStateQuery\-Elemente denselben Namen haben, werden nur die Zustände im letzten Element im Nachverfolgungsprofil verwendet.  
  
-   <xref:System.Activities.Tracking.ActivityScheduledQuery> – Mit dieser Abfrage können Sie eine Aktivität nachverfolgen, die von einer übergeordneten Aktivität ausgeführt werden soll.Die Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>\-Objekt <xref:System.Activities.Tracking.ActivityScheduledRecord>\-Objekte abonnieren kann.  
  
     Die Konfiguration und der Code zum Abonnieren von Datensätzen, die mit der untergeordneten `SendEmailActivity`\-Aktivität verknüpft sind, deren Planung mit dem <xref:System.Activities.Tracking.ActivityScheduledQuery>\-Objekt erfolgt, wird im folgenden Beispiel gezeigt.  
  
    ```  
    <activityScheduledQueries>  
      <activityScheduledQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />  
     </activityScheduledQueries>  
  
    ```  
  
    ```  
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
  
-   <xref:System.Activities.Tracking.FaultPropagationQuery> – Hiermit können Sie die Behandlung von Fehlern nachverfolgen, die in einer Aktivität auftreten.Die Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>\-Objekt <xref:System.Activities.Tracking.FaultPropagationRecord>\-Objekte abonnieren kann.  
  
     Die Konfiguration und der Code zum Abonnieren von mit der Fehlerweitergabe verknüpften Datensätzen mithilfe von <xref:System.Activities.Tracking.FaultPropagationQuery> werden im folgenden Beispiel gezeigt.  
  
    ```  
    <faultPropagationQueries>  
      <faultPropagationQuery faultSourceActivityName="SendEmailActivity" faultHandlerActivityName="NotificationsFaultHandler" />  
    </faultPropagationQueries>  
  
    ```  
  
    ```  
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
  
-   <xref:System.Activities.Tracking.CancelRequestedQuery> – Hiermit können Sie Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachverfolgen.Die Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>\-Objekt <xref:System.Activities.Tracking.CancelRequestedRecord>\-Objekte abonnieren kann.  
  
     Die Konfiguration und der Code zum Abonnieren von mit dem Aktivitätenabbruch verknüpften Datensätzen mithilfe von <xref:System.Activities.Tracking.CancelRequestedQuery> werden im folgenden Beispiel gezeigt.  
  
    ```  
    <cancelRequestedQueries>  
      <cancelRequestedQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />  
    </cancelRequestedQueries>  
  
    ```  
  
    ```  
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
  
-   <xref:System.Activities.Tracking.CustomTrackingQuery> – Hiermit können Sie Ereignisse nachverfolgen, die Sie in den Codeaktivitäten definieren.Die Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>\-Objekt <xref:System.Activities.Tracking.CustomTrackingRecord>\-Objekte abonnieren kann.  
  
     Die Konfiguration und der Code zum Abonnieren von mit der benutzerdefinierten Nachverfolgung verknüpften Datensätzen mit <xref:System.Activities.Tracking.CustomTrackingQuery> werden im folgenden Beispiel gezeigt.  
  
    ```  
    <customTrackingQueries>  
      <customTrackingQuery name="EmailAddress" activityName="SendEmailActivity" />  
    </customTrackingQueries>  
    ```  
  
    ```  
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
  
-   <xref:System.Activities.Tracking.BookmarkResumptionQuery> – Hiermit können Sie die Wiederaufnahme eines Lesezeichens in einer Workflowinstanz nachverfolgen.Diese Abfrage ist notwendig, damit ein <xref:System.Activities.Tracking.TrackingParticipant>\-Objekt <xref:System.Activities.Tracking.BookmarkResumptionRecord>\-Objekte abonnieren kann.  
  
     Die Konfiguration und der Code zum Abonnieren von mit der Wiederaufnahme von Lesezeichen verknüpften Datensätzen mithilfe von <xref:System.Activities.Tracking.BookmarkResumptionQuery> werden im folgenden Beispiel gezeigt.  
  
    ```  
    <bookmarkResumptionQueries>  
      <bookmarkResumptionQuery name="SentEmailBookmark" />  
    </bookmarkResumptionQueries>  
  
    ```  
  
    ```  
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
  
### Anmerkungen  
 Anmerkungen ermöglichen es Ihnen, Nachverfolgungsdatensätze mit einem beliebigen Wert zu markieren, der nach der Erstellung konfiguriert werden kann.Sie könnten z. B. mehrere Überwachungsdatensätze in mehreren Workflows mit "Mail Server" \=\= "Mail Server1" markieren.Auf diese Weise können alle Datensätze mit diesem Tag einfach gefunden werden, wenn zu einem späteren Zeitpunkt Überwachungsdatensätze abgefragt werden.  
  
 Damit dies funktioniert, wird einer Überwachungsabfrage eine Anmerkung hinzugefügt, wie im folgenden Beispiel gezeigt.  
  
```  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
  
```  
  
### Vorgehensweise für das Erstellen eines Überwachungsprofils  
 Mit Überwachungsabfrageelementen wird ein Überwachungsprofil erstellt. Dazu wird entweder eine XML\-Konfigurationsdatei oder [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]\-Code verwendet.Im Folgenden finden Sie ein Beispiel für ein mit einer Konfigurationsdatei erstelltes Überwachungsprofil.  
  
```  
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
>  Bei WF mit dem Workflowdiensthost wird das Überwachungsprofil in der Regel mit einer Konfigurationsdatei erstellt.Es ist auch möglich, ein Überwachungsprofil mit Code zu erstellen. Dazu wird die API für Überwachungsprofile und Überwachungsabfragen verwendet.  
  
 Ein Profil, das als XML\-Konfigurationsdatei konfiguriert ist, wird mit einer Verhaltenserweiterung auf einen Überwachungsteilnehmer angewendet.Dies wird einem WorkflowServiceHost hinzugefügt, wie weiter unten im Abschnitt [Konfigurieren der Nachverfolgung für einen Workflow](../../../docs/framework/windows-workflow-foundation//configuring-tracking-for-a-workflow.md) beschrieben.  
  
 Der Detailliertheitsgrad der Überwachungsdatensätze, die vom Host ausgegeben werden, wird von den Konfigurationseinstellungen im Überwachungsprofil bestimmt.Ein Überwachungsteilnehmer abonniert Überwachungsdatensätze, indem einem Überwachungsprofil Abfragen hinzugefügt werden.Zum Abonnieren aller Überwachungsdatensätze müssen im Überwachungsprofil alle Überwachungsabfragen mit "\*" in den Namensfeldern der einzelnen Abfragen angegeben werden.  
  
 Es folgen einige häufige Beispiele für Überwachungsprofile.  
  
-   Ein Überwachungsprofil zum Abfragen von Workflowinstanz\-Datensätzen und \-fehlern  
  
```  
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
  
1.  Ein Überwachungsprofil zum Abfragen aller benutzerdefinierten Überwachungsdatensätze  
  
```  
<trackingProfile name="Instance_And_Custom_Records">  
  <workflow activityDefinitionId="*">  
    <customTrackingQueries>  
      <customTrackingQuery name="*" activityName="*" />  
    </customTrackingQueries>  
  </workflow>  
</trackingProfile>  
  
```  
  
## Siehe auch  
 [SQL\-Nachverfolgung](../../../docs/framework/windows-workflow-foundation/samples/sql-tracking.md)   
 [Überwachung mit Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201273)   
 [Überwachen von Anwendungen mit AppFabric](http://go.microsoft.com/fwlink/?LinkId=201275)