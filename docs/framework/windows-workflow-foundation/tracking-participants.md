---
title: "&#220;berwachungsteilnehmer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f13e360c-eeb7-4a49-98a0-8f6a52d64f68
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# &#220;berwachungsteilnehmer
Nachverfolgungsteilnehmer sind Erweiterungspunkte, über die ein Workflowentwickler auf <xref:System.Activities.Tracking.InteropTrackingRecord.TrackingRecord%2A>\-Objekte zugreifen und sie verarbeiten kann.  [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] enthält einen standardmäßigen Überwachungsteilnehmer, der Überwachungsdatensätze als ETW \(Ereignisablaufverfolgung für Windows\)\-Ereignisse schreibt.  Wenn dies nicht Ihren Anforderungen entspricht, können Sie auch einen benutzerdefinierten Überwachungsteilnehmer schreiben.  
  
## Überwachungsteilnehmer  
 Die Überwachungsinfrastruktur ermöglicht die Anwendung eines Filters für ausgehende Überwachungsdatensätze, sodass ein Teilnehmer eine Teilmenge der Datensätze abonnieren kann.  Die Anwendung eines Filters erfolgt durch ein Überwachungsprofil.  
  
 [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] stellt einen Überwachungsteilnehmer bereit, der die Überwachungsdatensätze in eine ETW\-Sitzung schreibt.  Der Teilnehmer wird für einen Workflowdienst konfiguriert, indem einer Konfigurationsdatei ein nachverfolgungsspezifisches Verhalten hinzugefügt wird.  Durch Aktivierung eines ETW\-Nachverfolgungsteilnehmers können Nachverfolgungsdatensätze in der Ereignisanzeige angezeigt werden.  Das SDK\-Beispiel für ETW\-basierte Überwachung ist eine gute Möglichkeit, über den ETW\-basierten Überwachungsteilnehmer mit der WF\-Überwachung vertraut zu werden.  
  
## ETW\-Überwachungsteilnehmer  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] enthält einen ETW\-Überwachungsteilnehmer, der die Überwachungsdatensätze in eine ETW\-Sitzung schreibt.  Dies geschieht auf sehr effiziente Weise mit minimalen Auswirkungen auf die Leistung der Anwendung oder den Serverdurchsatz.  Ein Vorteil der Verwendung des standardmäßigen ETW\-Überwachungsteilnehmers besteht darin, dass die empfangenen Überwachungsdatensätze mit den anderen Anwendungs\- und Systemprotokollen in der Windows\-Ereignisanzeige angezeigt werden können.  
  
 Der standardmäßige ETW\-Überwachungsteilnehmer wird, wie im folgenden Beispiel dargestellt, in der Datei "Web.config" konfiguriert.  
  
```  
<configuration>  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
   <tracking>  
      <profiles>  
        <trackingProfile name="Sample Tracking Profile">  
        ….  
       </trackingProfile>  
      </profiles>  
    </tracking>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  Wenn ein `trackingProfile`\-Name nicht angegeben wurde, z. B. nur `<etwTracking/>` oder `<etwTracking profileName=""/>`, wird das mit [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] installierte Standardüberwachungsprofil in der Datei "Machine.config" verwendet.  
  
 In der Datei "Machine.config" abonniert das Standardüberwachungsprofil Workflowinstanz\-Datensätze und \-fehler.  
  
 In der ETW werden Ereignisse mithilfe einer Anbieter\-ID in die ETW\-Sitzung geschrieben.  Die Anbieter\-ID, die der ETW\-Überwachungsteilnehmer zum Schreiben der Überwachungsdatensätze in der ETW verwendet, wird im Diagnoseabschnitt der Datei "Web.config" \(unter `<system.serviceModel><diagnostics>`\) definiert.  In der Regel verwendet der ETW\-Überwachungsteilnehmer, wie im folgenden Beispiel dargestellt, eine standardmäßige Anbieter\-ID, wenn keine angegeben wurde.  
  
```  
<system.serviceModel>  
        <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />  
```  
  
 Die folgende Abbildung zeigt den Überwachungsdatenstrom über den ETW\-Überwachungsteilnehmer.  Sobald die Überwachungsdaten die ETW\-Sitzung erreichen, kann auf unterschiedliche Weise darauf zugegriffen werden.  Eine der besten Möglichkeiten für den Zugriff auf diese Ereignisse ist die Ereignisanzeige, ein häufig verwendetes Windows\-Tool für die Anzeige von Protokollen und Ablaufverfolgungen von Anwendungen und Diensten.  
  
 ![Der Fluss für Nachverfolgung und ETW&#45;Nachverfolgungsanbieter](../../../docs/framework/windows-workflow-foundation//media/trackingdatathroughetwparticipant.gif "TrackingDatathroughETWParticipant")  
  
## Ereignisdaten von Überwachungsteilnehmern  
 Ein Überwachungsteilnehmer serialisiert verfolgte Ereignisdaten in einer ETW\-Sitzung jeweils im Format von einem Ereignis pro Überwachungsdatensatz.  Ein Ereignis wird innerhalb des Bereichs von 100 bis 199 durch eine ID identifiziert.  Definitionen der Nachverfolgungsereignis\-Datensätze, die von einem Nachverfolgungsteilnehmer ausgegeben wurden, finden Sie im Thema [Referenz zu Nachverfolgungsereignissen](../../../docs/framework/windows-workflow-foundation//tracking-events-reference.md).  
  
 Die Größe eines ETW\-Ereignisses wird durch die Größe des ETW\-Puffers oder durch die maximale Nutzlast für ein ETW\-Ereignis beschränkt, wobei jeweils der niedrigere Wert angewendet wird.  Wenn die Größe des Ereignisses beide ETW\-Grenzen überschreitet, wird das Ereignis abgeschnitten und sein Inhalt willkürlich entfernt.  Variablen, Argumente, Anmerkungen und benutzerdefinierte Daten werden nicht selektiv entfernt.  Bei abgeschnittenen Daten werden alle Daten abgeschnitten, unabhängig davon, welcher Wert zur Überschreitung der ETW\-Grenze für die Ereignisgröße geführt hat.  Die entfernten Daten werden durch `<item>..<item>` ersetzt.  
  
 Komplexe Typen in Variablen, Argumenten und benutzerdefinierten Datenelementen werden mit der [NetDataContractSerializer\-Klasse](http://go.microsoft.com/fwlink/?LinkId=177537) in den ETW\-Ereignisdatensatz serialisiert.  Diese Klasse enthält Informationen zum CLR\-Typ im serialisierten XML\-Stream.  
  
 Aufgrund der ETW\-Beschränkung abgeschnittene Nutzlastdaten können dazu führen, dass Überwachungsdatensätze mehrfach an eine ETW\-Sitzung gesendet werden.  Dies kann geschehen, wenn mehr als eine Sitzung die Ereignisse überwacht und die Sitzungen unterschiedliche Nutzlastgrenzen für die Ereignisse aufweisen.  
  
 Bei der Sitzung mit der niedrigeren Begrenzung wird das Ereignis möglicherweise abgeschnitten.  Der ETW\-Überwachungsteilnehmer hat keine Informationen zur Anzahl von Sitzungen, die die Ereignisse überwachen. Wenn ein Ereignis für eine Sitzung abgeschnitten wird, versucht der ETW\-Teilnehmer noch ein Mal, das Ereignis zu senden.  In diesem Fall empfängt die Sitzung, für die eine höhere Nutzlastgröße konfiguriert ist, das Ereignis zweimal \(das nicht abgeschnittene und das abgeschnittene Ereignis\).  Diese Duplizierung kann verhindert werden, indem für alle ETW\-Sitzungen die gleichen Begrenzungen der Puffergröße konfiguriert werden.  
  
## Zugreifen auf Überwachungsdaten über einen ETW\-Teilnehmer in der Ereignisanzeige  
 Sie können über die Ereignisanzeige auf Ereignisse zugreifen, die vom ETW\-Überwachungsteilnehmer in eine ETW\-Sitzung geschrieben werden, falls die standardmäßige Anbieter\-ID verwendet wird.  Auf diese Weise können Überwachungsdatensätze, die vom Workflow ausgegeben wurden, schnell angezeigt werden.  
  
> [!NOTE]
>  Überwachungsdatensatz\-Ereignisse, die an eine ETW\-Sitzung ausgegeben werden, verwenden Ereignis\-IDs im Bereich von 100 bis 199.  
  
#### So aktivieren Sie das Anzeigen der Überwachungsdatensätze in der Ereignisanzeige  
  
1.  Starten der Ereignisanzeige \(EVENTVWR.EXE\)  
  
2.  Wählen Sie **Ereignisanzeige, Anwendungs\- und Dienstprotokolle, Microsoft, Windows, Anwendungsserver\-Anwendungen** aus.  
  
3.  Klicken Sie mit der rechten Maustaste, und stellen Sie sicher, dass **Ansicht, Analytische und Debugprotokolle einblenden** ausgewählt ist.  Wenn dies nicht der Fall ist, aktivieren Sie die Option, sodass das Häkchen daneben angezeigt wird.  Dadurch werden die Protokolle **Analytic**, **Perf** und **Debug** angezeigt.  
  
4.  Klicken Sie mit der rechten Maustaste auf das Protokoll **Analytic**, und wählen Sie **Protokoll aktivieren** aus.  Das Protokoll befindet sich in der Datei unter "%SystemRoot%\\System32\\Winevt\\Logs\\Microsoft\-Windows\-Application Server\-Applications%4Analytic.etl".  
  
## Benutzerdefinierte Nachverfolgungskomponente  
 Die Überwachungsteilnehmer\-API ermöglicht eine Erweiterung der Überwachungslaufzeit mit einem vom Benutzer bereitgestellten Überwachungsteilnehmer. Dieser kann benutzerdefinierte Logik enthalten, mit der von der Workflowlaufzeit ausgegebene Überwachungsdatensätze behandelt werden.  Zum Schreiben eines benutzerdefinierten Überwachungsteilnehmers muss der Entwickler die `Track`\-Methode für die <xref:System.Activities.Tracking.TrackingParticipant>\-Klasse implementieren.  Diese Methode wird aufgerufen, wenn ein Überwachungsdatensatz von der Workflowlaufzeit ausgegeben wird.  
  
 Überwachungsteilnehmer sind von der <xref:System.Activities.Tracking.TrackingParticipant>\-Klasse abgeleitet.  Das vom System bereitgestellte <xref:System.Activities.Tracking.EtwTrackingParticipant>\-Objekt gibt ein ETW \(Ereignisablaufverfolgung für Windows\)\-Ereignis für jeden empfangenen Überwachungsdatensatz aus.  Zum Erstellen eines benutzerdefinierten Überwachungsteilnehmers wird eine Klasse erstellt, die von <xref:System.Activities.Tracking.TrackingParticipant> abgeleitet ist.  Um grundlegende Funktionen für Nachverfolgung bereitzustellen, überschreiben Sie <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>.  <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> wird aufgerufen, wenn ein Nachverfolgungsdatensatz von der Laufzeit gesendet wird und wie gewünscht verarbeitet werden kann.  Im folgenden Beispiel wird eine benutzerdefinierte Überwachungsteilnehmer\-Klasse definiert, die alle Überwachungsdatensätze an das Konsolenfenster ausgibt.  Sie können auch ein <xref:System.Activities.Tracking.TrackingParticipant>\-Objekt implementieren, das die Überwachungsdatensätze mit der `BeginTrack`\-Methode und der `EndTrack`\-Methode asynchron verarbeitet.  
  
```csharp  
class ConsoleTrackingParticipant : TrackingParticipant  
{  
    protected override void Track(TrackingRecord record, TimeSpan timeout)  
    {  
        if (record != null)  
        {  
            Console.WriteLine("=================================");  
            Console.WriteLine(record);  
        }  
    }  
}  
```  
  
 Wenn Sie einen bestimmten Überwachungsteilnehmer verwenden möchten, registrieren Sie diesen, wie im folgenden Beispiel gezeigt, für die Workflowinstanz, die Sie überwachen möchten.  
  
```csharp  
myInstance.Extensions.Add(new ConsoleTrackingParticipant());  
```  
  
 Im folgenden Beispiel wird ein Workflow erstellt, der aus einer <xref:System.Activities.Statements.Sequence>\-Aktivität mit einer <xref:System.Activities.Statements.WriteLine>\-Aktivität besteht.  Der `ConsoleTrackingParticipant` wird den Erweiterungen hinzugefügt, und der Workflow wird aufgerufen.  
  
```csharp  
Activity activity= new Sequence()  
{  
    Activities =  
    {  
        new WriteLine()  
        {  
            Text = "Hello World."  
        }  
    }  
};  
  
WorkflowApplication instance = new WorkflowApplication(activity);  
  
instance.Extensions.Add(new ConsoleTrackingParticipant());  
  instance.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
            {  
                Console.WriteLine("workflow instance completed, Id = " + instance.Id);  
                resetEvent.Set();  
            };  
            instance.Run();  
            Console.ReadLine();  
  
```  
  
## Siehe auch  
 [Überwachung mit Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201273)   
 [Überwachen von Anwendungen mit AppFabric](http://go.microsoft.com/fwlink/?LinkId=201275)