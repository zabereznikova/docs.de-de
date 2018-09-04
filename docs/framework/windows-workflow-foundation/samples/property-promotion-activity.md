---
title: Aktivität zur Höherstufung einer Eigenschaft
ms.date: 03/30/2017
ms.assetid: 802196b7-1159-4c05-b41b-d3bfdfcc88d9
ms.openlocfilehash: 6e059a0d344e6c62833feaa890c459c141a49673
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43559104"
---
# <a name="property-promotion-activity"></a>Aktivität zur Höherstufung einer Eigenschaft
In diesem Beispiel wird eine End-to-End-Projektmappe bereitgestellt, mit der die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Funktion zur Höherstufung direkt in die Workflowerstellung integriert wird. Eine Auflistung von Konfigurationselementen, Workflowaktivitäten und Workflowerweiterungen wird bereitgestellt, um die Verwendung der Funktion zur Höherstufung zu vereinfachen. Außerdem enthält das Beispiel einen einfachen Workflow, mit dem die Verwendung dieser Auflistung veranschaulicht wird.  
  
> [!NOTE]
>  Die Beispiele dienen nur zu Lernzwecken. Sie sollten nicht in einer Produktionsumgebung eingesetzt werden und wurden vorher nicht in einer Produktionsumgebung getestet. Microsoft bietet keinen technischen Support für diese Beispiele.  
  
## <a name="prerequisites"></a>Voraussetzungen  
  
-   <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Datenbank (initialisiert)  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]  
  
## <a name="sample-projects"></a>Beispielprojekte  
  
-   Die **PropertyPromotionActivity** -Projekt enthält Dateien, die die heraufstufung spezifischen Konfigurationselementen, Workflowaktivitäten und workflowerweiterungen angehören.  
  
-   Die **CounterServiceApplication** Projekt enthält einen Beispielworkflow, der verwendet die **SqlWorkflowInstanceStorePromotion** Projekt.  
  
-   Ein SQL-Skript (PropertyPromotionActivitySQLSample.sql), das für die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Datenbank ausgeführt werden muss.  
  
-   Eine Projektmappendatei, mit der die beiden [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Projekte verknüpft werden (`PropertyPromotionActivity.sln`).  
  
## <a name="to-set-up-and-run-the-sample"></a>So richten Sie das Beispiel ein und führen es aus  
  
1.  Initialisieren Sie eine Workflowpersistenzdatenbank.  
  
    1.  Navigieren Sie zum Beispielverzeichnis (\WF\Basic\Persistence\PropertyPromotionActivity), und führen Sie CreateInstanceStore.cmd aus.  
  
    2.  Wenn Sie nicht über Administratorberechtigungen verfügen, erstellen Sie eine SQL Server-Anmeldung. Wechseln Sie in SQL Server Management Studio zu **Sicherheit**, **Anmeldungen**. Mit der rechten Maustaste **Anmeldungen** und eine neue Anmeldung erstellen. Der SQL-Rolle Ihr ACL-Benutzerkonto hinzufügen, indem öffnen **Datenbanken**, **InstanceStore**, **Sicherheit**. Mit der rechten Maustaste **Benutzer** , und wählen Sie **neuer Benutzer**. Legen Sie die **Anmeldename** auf den vorherigen Schritt erstellten Benutzer. Fügen Sie den Benutzer der Datenbankrollenmitgliedschaft System.Activities.DurableInstancing.InstanceStoreUsers (und anderen) hinzu. Beachten Sie, dass der Benutzer möglicherweise bereits vorhanden ist (z. B. als DBO).  
  
2.  Öffnen Sie die Projektmappendatei PropertyPromotionActivity.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Wenn Sie den Instanzspeicher nicht in der lokalen Installation von SQL Server Express, sondern in einer anderen Datenbank erstellt haben, müssen Sie die Datenbankverbindungszeichenfolge aktualisieren. Ändern Sie die Datei "App.config", unter der **CounterServiceApplication** durch Festlegen des Werts von der `connectionString` -Attribut für die `sqlWorkflowInstanceStorePromotion` Knoten, damit er mit der persistenten Datenbank verweist, der initialisiert wurde in Schritt 1.  
  
4.  Erstellen Sie die Projektmappe, und führen Sie sie aus. Dadurch wird der WF-Zählerdienst gestartet und automatisch eine Workflowinstanz aufgerufen.  
  
5.  Wählen Sie alle Zeilen in der Sicht [dbo].[CounterService] in der Persistenzdatenbank aus (die Sicht wurde durch Ausführen von CreateInstanceStore.cmd in Schritt 1 hinzugefügt). Es wird ein Resultset ähnlich dem folgenden angezeigt:  
  
    |InstanceId|CounterValue|CounterValueLastUpdated|  
    |----------------|------------------|-----------------------------|  
    |2FA2C302-929E-4C0D-8C25-768A3DA20CE5|12|2010-02-18 22:48:01.740|  
  
     Wenn Sie die Sicht fortlaufend aktualisieren, werden Sie feststellen, dass sich der Wert von CounterValue und CounterValueLastUpdated alle zwei Sekunden ändert. Dies ist der Zeitabstand, in dem der Zähler automatisch aktualisiert wird. CounterValue und CounterValueLastUpdated entsprechen den höher gestuften Eigenschaften für diesen Workflow.  
  
## <a name="to-remove-the-sample"></a>So entfernen Sie das Beispiel  
  
-   Führen Sie RemoveInstanceStore.cmd im Beispielverzeichnis (\WF\Basic\Persistence\PropertyPromotionActivity) aus.  
  
## <a name="understanding-this-sample"></a>Grundlagen dieses Beispiels  
 Das Beispiel enthält zwei Projekte und eine SQL-Datei:  
  
-   **CounterServiceApplication** ist eine Konsolenanwendung, die einen einfachen WF-zählerdienst fungiert. Nach dem Erhalt einer unidirektionalen Nachricht über den `Start`-Endpunkt inkrementiert der Workflow alle zwei Sekunden eine Zählervariable und zählt so von 0 bis 29. Der Workflow wird nach jeder Erhöhung des Zählerwerts beibehalten, und die höher gestuften Eigenschaften werden in der Sicht [dbo].[CounterService] aktualisiert. Wenn Sie die Konsolenanwendung ausführen, wird der WF-Dienst gehostet. Eine Nachricht wird an den `Start`-Endpunkt gesendet, und es wird eine WF-Zählerinstanz erstellt.  
  
-   **PropertyPromotionActivity** ist eine Klassenbibliothek, die den Konfigurationselementen, Workflowaktivitäten und workflowerweiterungen enthält, die die **CounterServiceApplication** verwendet.  
  
-   **PropertyPromotionActivitySQLSample.sql** erstellt und fügt Sie die Sicht [Dbo]. [ CounterService] in der Datenbank.  
  
### <a name="counterserviceapplication"></a>CounterServiceApplication  
  
#### <a name="using-the-sqlworkflowinstancestorepromotion-configuration-element"></a>Verwenden des SqlWorkflowInstanceStorePromotion-Konfigurationselements  
 Das `SqlWorkflowInstanceStorePromotion`-Konfigurationselement erbt vom `SqlWorkflowInstanceStore`-Konfigurationselement, fügt jedoch das `promotionSets`-Konfigurationselement hinzu. Das `promotionSets`-Element ermöglicht es dem Benutzer, höher gestufte Eigenschaften über die Konfiguration anzugeben. Die folgende Konfigurationsdatei wird im Beispiel verwendet:  
  
```xml  
<sqlWorkflowInstanceStorePromotion connectionString ="Data Source=.;Initial Catalog=SqlWorkflowInstanceStoreTest;Integrated Security=True;">  
  <promotionSets>  
    <promotionSet name="CounterService">  
      <promotedValue propertyName="Count"/>  
      <promotedValue propertyName="LastIncrementedAt"/>  
    </promotionSet>  
  </promotionSets>  
</sqlWorkflowInstanceStorePromotion>  
```  
  
 Überprüfen Sie die Definition für die Sicht [dbo].[CounterService].  
  
```sql  
create view [dbo].[CounterService] as  
      select [InstanceId],  
 [Value1] as [CounterValue],  
 [Value2] as [CounterValueLastUpdated]  
      from [System.Activities.DurableInstancing].[InstancePromotedProperties]  
      where [PromotionName] = 'CounterService'  
go  
```  
  
 Wenn eine Workflowinstanz beibehalten wird, wird in der `InstancePromotedProperties`-Sicht eine Zeile für jeden `PromotionSet` eingefügt, der in der Konfiguration definiert wurde. Diese Zeile enthält alle höher gestuften Eigenschaften des `PromotionSet` (eine höher gestufte Eigenschaft pro Spalte). Dieser `PromotionSet` wird nach folgendem Tupel sortiert: `InstanceId, PromotionName`. In diesem Beispiel wurde ein `PromotionSet` mit dem Namensattribut `CounterService` in der Konfiguration definiert. Beachten Sie, dass der Wert der `PromotionName`-Spalte dem Namensattribut des `PromotionSet`-Elements entspricht.  
  
 Die Reihenfolge der `promotedValue`-Elemente korreliert mit der Platzierung der höher gestuften Eigenschaften in der `InstancePromotedProperties`-Sicht. `Count` stellt das erste `promotedValue`-Element dar. Es wird daher der `Value1`-Spalte in der `InstancePromotedProperties`-Sicht zugeordnet. `LastIncrementedAt` stellt das zweite `promotedValue`-Element dar. Es wird daher der `Value2`-Spalte in der `InstancePromotedProperties`-Sicht zugeordnet.  
  
#### <a name="using-the-promotevalue-activity"></a>Verwenden der PromoteValue-Aktivität  
 Überprüfen Sie die Datei counterservice.xamlx im Windows Workflow Foundation-Designer. Beachten Sie, dass die WF-Definition zwei spezielle Aktivitäten enthält: `PromoteValue<DateTime>` und `PromoteValue<Int32>`.  
  
 Der `PromoteValue<Int32>`-Member der `Name`-Aktivität wurde als `Count` definiert. Dies entspricht dem ersten `promotedValue`-Element in der Konfiguration. `Value` wurde als `Counter`-Workflowvariable definiert. Wenn der Workflow gespeichert wird, wird die `Counter`-Workflowvariable als höher gestufte Eigenschaft in der `Value1`-Spalte der `InstancePromotedProperties`-Sicht gespeichert.  
  
 Der `PromoteValue<DateTime>`-Member der `Name`-Aktivität wurde als `LastIncrementedAt` definiert. Dies entspricht dem zweiten `promotedValue`-Element in der Konfiguration. `Value` wurde als `TimeLastIncremented`-Workflowvariable definiert. Wenn der Workflow beibehalten wird, wird daher der Wert für die `TimeLastIncremented`-Workflowvariable als höher gestufte Eigenschaft in der `Value2`-Spalte der `InstancePromotedProperties`-Sicht beibehalten.  
  
 Beachten Sie, dass die `PromotedValue`-Aktivität außerdem über den booleschen Member `ClearExistingPromotedData` verfügt. Wenn dieser Member auf `true` festgelegt wird, werden alle höher gestuften Eigenschaftswerte bis zu diesem Punkt im Workflow bereinigt. Beispielsweise ist eine Sequence-Aktivität wie folgt definiert:  
  
1.  PromoteValue {Name = "Count", Wert = 3}  
  
2.  PromoteValue {Name = "LastIncrementedAt", Wert = 1-1-2000}  
  
3.  Beibehalten  
  
4.  PromoteValue {Name = "Count", Wert = 4 "," ClearExistingPromotedData = "true"}  
  
5.  Beibehalten  
  
 Bei der zweiten persistenten Speicherung wird der Wert für `Count` auf 4 erhöht. Allerdings die höher gestufte Wert für `LastIncrementedAt` werden `NULL`. Wenn `ClearExistingPromotedData` in Schritt 4 nicht auf `true` festgelegt worden wäre, würde der höher gestufte Wert für Count nach der zweiten persistenten Speicherung 4 lauten. Demzufolge wäre der höher gestufte Wert für `LastIncrementedAt` weiterhin 1-1-2000.  
  
### <a name="propertypromotionactivity"></a>PropertyPromotionActivity  
 Diese Klassenbibliothek enthält die folgenden öffentlichen Klassen, um die Verwendung der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Funktion zur Höherstufung zu vereinfachen.  
  
#### <a name="promotevalue-class"></a>PromoteValue-Klasse  
 Mit dieser Klasse wird eine Eigenschaft höher gestuft. Der Name der höher gestuften Eigenschaft sollte mit dem Namensattribut eines `promotedValue`-Elements in der Konfiguration übereinstimmen. Diese Aktivität kann im Workflow-Designer verwendet werden. Ein Beispiel zur Verwendung finden Sie in der CounterServiceApplication.  
  
```csharp  
public class PromoteValue<T> : CodeActivity  
{  
    public PromoteValue()  
    {  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public string Name { get; set; }  
    public InArgument<T> Value { get; set; }  
}  
```  
  
 ClearExistingPromotedData (Boolescher Wert)  
 Löscht alle Werte, die vor dieser Aktivität höher gestuft wurden.  
  
 Name (Zeichenfolge)  
 Der Name, der diese Eigenschaft darstellt. Dies sollte das Name-Attribut entsprechen einem \<PromotedValue >-Elements in der Konfigurationsdatei.  
  
 Wert (InArgument\<T >)  
 Die Variable/der Wert, die bzw. der in der Spalte gespeichert werden soll.  
  
#### <a name="promotevalues-class"></a>PromoteValues-Klasse  
 Stuft mehrere Eigenschaften hoch. Die Namen der höher gestuften Eigenschaften sollten mit allen Namensattributen der `promotedValue`-Elemente in der Konfiguration übereinstimmen. Die Verwendung erfolgt analog zur `PromoteValue`-Aktivität, mit dem Unterschied, dass mehrere Eigenschaften auf einmal höher gestuft werden können. Diese Aktivität kann nicht im Workflow-Designer verwendet werden.  
  
```  
public class PromoteValues : CodeActivity  
{  
    public PromoteValues()  
    {  
        this.ValuesToPromote = new Dictionary<string, InArgument>();  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public IDictionary<string, InArgument> ValuesToPromote { get; set; }  
}  
```  
  
#### <a name="sqlworkflowinstancestorepromotionbehavior"></a>SqlWorkflowInstanceStorePromotionBehavior  
 Wird von `SqlWorkflowInstanceStoreBehavior` abgeleitet. Mit dieser abgeleiteten Klasse wird ein benutzerdefinierter Persistenzteilnehmer (ebenfalls Teil dieser Bibliothek) als Workflowerweiterung hinzugefügt. Die Implementierung der beiden vorherigen Workflowaktivitäten ist von diesem benutzerdefinierten Persistenzteilnehmer abhängig.  
  
```  
public class SqlWorkflowInstanceStorePromotionBehavior :  
             SqlWorkflowInstanceStoreBehavior, IServiceBehavior  
{  
        public void Promote(string name, IEnumerable<string> promoteAsSqlVariant,  
                            IEnumerable<string> promoteAsBinary)  
  
}  
```  
  
 Diese Klassenbibliothek enthält auch die `ConfigurationElement`-Implementierung für das `SqlWorkflowInstanceStorePromotionElement` sowie einen benutzerdefinierten Persistenzteilnehmer, der von den vorherigen Aktivitäten zur Höherstufung verwendet wird.  
  
### <a name="propertypromotionactivitysqlsample"></a>PropertyPromotionActivitySQLSample  
 Mit dieser SQL-Datei wird eine `[dbo].[CounterService]`-Sicht zusätzlich zur `[InstancePromotedProperties]`-Sicht erstellt, um alle Instanzen mit einem CounterService-Satz für die Höherstufung abzufragen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\PropertyPromotionActivity`  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting- und-persistenzbeispiele](https://go.microsoft.com/fwlink/?LinkId=193961)
