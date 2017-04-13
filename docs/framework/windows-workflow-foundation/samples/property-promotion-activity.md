---
title: "Aktivit&#228;t zur H&#246;herstufung einer Eigenschaft | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 802196b7-1159-4c05-b41b-d3bfdfcc88d9
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Aktivit&#228;t zur H&#246;herstufung einer Eigenschaft
In diesem Beispiel wird eine End\-to\-End\-Projektmappe bereitgestellt, mit der die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>\-Funktion zur Höherstufung direkt in die Workflowerstellung integriert wird.Eine Auflistung von Konfigurationselementen, Workflowaktivitäten und Workflowerweiterungen wird bereitgestellt, um die Verwendung der Funktion zur Höherstufung zu vereinfachen.Außerdem enthält das Beispiel einen einfachen Workflow, mit dem die Verwendung dieser Auflistung veranschaulicht wird.  
  
> [!NOTE]
>  Die Beispiele werden nur zu Lehrzwecken zur Verfügung gestellt.Sie sollten nicht in einer Produktionsumgebung eingesetzt werden und wurden vorher nicht in einer Produktionsumgebung getestet.Microsoft bietet keinen technischen Support für diese Beispiele.  
  
## Erforderliche Komponenten  
  
-   <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>\-Datenbank \(initialisiert\)  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]  
  
## Beispielprojekte  
  
-   Das Projekt **PropertyPromotionActivity** enthält Dateien mit den spezifischen Konfigurationselementen, Workflowaktivitäten und Workflowerweiterungen für die Funktion zur Höherstufung.  
  
-   Das Projekt **CounterServiceApplication** enthält einen Beispielworkflow, in dem das Projekt **SqlWorkflowInstanceStorePromotion** verwendet wird.  
  
-   Ein SQL\-Skript \(PropertyPromotionActivitySQLSample.sql\), das für die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>\-Datenbank ausgeführt werden muss.  
  
-   Eine Projektmappendatei, mit der die beiden [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]\-Projekte verknüpft werden \(`PropertyPromotionActivity.sln`\).  
  
## So richten Sie das Beispiel ein und führen es aus  
  
1.  Initialisieren Sie eine Workflowpersistenzdatenbank.  
  
    1.  Navigieren Sie zum Beispielverzeichnis \(\\WF\\Basic\\Persistence\\PropertyPromotionActivity\), und führen Sie CreateInstanceStore.cmd aus.  
  
    2.  Wenn Sie nicht über Administratorberechtigungen verfügen, erstellen Sie eine SQL Server\-Anmeldung.Wechseln Sie in SQL Server Management Studio zu **Sicherheit** und zu **Anmeldungen**.Klicken Sie mit der rechten Maustaste auf **Anmeldungen**, und erstellen Sie eine neue Anmeldung.Fügen Sie der SQL\-Rolle Ihr ACL\-Benutzerkonto hinzu, indem Sie **Datenbanken**, **InstanceStore** und **Sicherheit** öffnen.Klicken Sie mit der rechten Maustaste auf **Benutzer**, und wählen Sie **Neuer Benutzer** aus.Wählen Sie unter **Anmeldename** den im vorherigen Schritt erstellten Benutzer aus.Fügen Sie den Benutzer der Datenbankrollenmitgliedschaft System.Activities.DurableInstancing.InstanceStoreUsers \(und anderen\) hinzu.Beachten Sie, dass der Benutzer möglicherweise bereits vorhanden ist \(z. B. als DBO\).  
  
2.  Öffnen Sie die Projektmappendatei PropertyPromotionActivity.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Wenn Sie den Instanzspeicher nicht in der lokalen Installation von SQL Server Express, sondern in einer anderen Datenbank erstellt haben, müssen Sie die Datenbankverbindungszeichenfolge aktualisieren.Ändern Sie die Datei App.config unter **CounterServiceApplication**, indem Sie das `connectionString`\-Attribut im `sqlWorkflowInstanceStorePromotion`\-Knoten auf einen Wert festlegen, der auf die Persistenzdatenbank zeigt, die in Schritt 1 erstellt wurde.  
  
4.  Erstellen Sie die Projektmappe, und führen Sie sie aus.Dadurch wird der WF\-Zählerdienst gestartet und automatisch eine Workflowinstanz aufgerufen.  
  
5.  Wählen Sie alle Zeilen in der Sicht \[dbo\].\[CounterService\] in der Persistenzdatenbank aus \(die Sicht wurde durch Ausführen von CreateInstanceStore.cmd in Schritt 1 hinzugefügt\).Es wird ein Resultset ähnlich dem folgenden angezeigt:  
  
    |InstanceId|CounterValue|CounterValueLastUpdated|  
    |----------------|------------------|-----------------------------|  
    |2FA2C302\-929E\-4C0D\-8C25\-768A3DA20CE5|12|2010\-02\-18 22:48:01.740|  
  
     Wenn Sie die Sicht fortlaufend aktualisieren, werden Sie feststellen, dass sich der Wert von CounterValue und CounterValueLastUpdated alle zwei Sekunden ändert.Dies ist der Zeitabstand, in dem der Zähler automatisch aktualisiert wird.CounterValue und CounterValueLastUpdated entsprechen den höher gestuften Eigenschaften für diesen Workflow.  
  
## So entfernen Sie das Beispiel  
  
-   Führen Sie RemoveInstanceStore.cmd im Beispielverzeichnis \(\\WF\\Basic\\Persistence\\PropertyPromotionActivity\) aus.  
  
## Grundlagen dieses Beispiels  
 Das Beispiel enthält zwei Projekte und eine SQL\-Datei:  
  
-   **CounterServiceApplication** ist eine Konsolenanwendung, die als Host für einen einfachen WF\-Zählerdienst fungiert.Nach dem Erhalt einer unidirektionalen Nachricht über den `Start`\-Endpunkt inkrementiert der Workflow alle zwei Sekunden eine Zählervariable und zählt so von 0 bis 29.Der Workflow wird nach jeder Erhöhung des Zählerwerts beibehalten, und die höher gestuften Eigenschaften werden in der Sicht \[dbo\].\[CounterService\] aktualisiert.Wenn Sie die Konsolenanwendung ausführen, wird der WF\-Dienst gehostet. Eine Nachricht wird an den `Start`\-Endpunkt gesendet, und es wird eine WF\-Zählerinstanz erstellt.  
  
-   **PropertyPromotionActivity** stellt eine Klassenbibliothek mit den Konfigurationselementen, Workflowaktivitäten und Workflowerweiterungen dar, die von der **CounterServiceApplication** verwendet werden.  
  
-   **PropertyPromotionActivitySQLSample.sql** erstellt die Sicht \[dbo\].\[CounterService\] und fügt sie der Datenbank hinzu.  
  
### CounterServiceApplication  
  
#### Verwenden des SqlWorkflowInstanceStorePromotion\-Konfigurationselements  
 Das `SqlWorkflowInstanceStorePromotion`\-Konfigurationselement erbt vom `SqlWorkflowInstanceStore`\-Konfigurationselement, fügt jedoch das `promotionSets`\-Konfigurationselement hinzu.Das `promotionSets`\-Element ermöglicht es dem Benutzer, höher gestufte Eigenschaften über die Konfiguration anzugeben.Die folgende Konfigurationsdatei wird im Beispiel verwendet:  
  
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
  
 Überprüfen Sie die Definition für die Sicht \[dbo\].\[CounterService\].  
  
```sql  
create view [dbo].[CounterService] as  
      select [InstanceId],  
 [Value1] as [CounterValue],  
 [Value2] as [CounterValueLastUpdated]  
      from [System.Activities.DurableInstancing].[InstancePromotedProperties]  
      where [PromotionName] = 'CounterService'  
go  
  
```  
  
 Wenn eine Workflowinstanz beibehalten wird, wird in der `InstancePromotedProperties`\-Sicht eine Zeile für jeden `PromotionSet` eingefügt, der in der Konfiguration definiert wurde.Diese Zeile enthält alle höher gestuften Eigenschaften des `PromotionSet` \(eine höher gestufte Eigenschaft pro Spalte\).Dieser `PromotionSet` wird nach folgendem Tupel sortiert: `InstanceId, PromotionName`.In diesem Beispiel wurde ein `PromotionSet` mit dem Namensattribut `CounterService` in der Konfiguration definiert.Beachten Sie, dass der Wert der `PromotionName`\-Spalte dem Namensattribut des `PromotionSet`\-Elements entspricht.  
  
 Die Reihenfolge der `promotedValue`\-Elemente korreliert mit der Platzierung der höher gestuften Eigenschaften in der `InstancePromotedProperties`\-Sicht.`Count` stellt das erste `promotedValue`\-Element dar.Es wird daher der `Value1`\-Spalte in der `InstancePromotedProperties`\-Sicht zugeordnet.`LastIncrementedAt` stellt das zweite `promotedValue`\-Element dar.Es wird daher der `Value2`\-Spalte in der `InstancePromotedProperties`\-Sicht zugeordnet.  
  
#### Verwenden der PromoteValue\-Aktivität  
 Untersuchen Sie die Datei CounterService.xamlx im [!INCLUDE[wf2](../../../../includes/wf2-md.md)]\-Designer.Beachten Sie, dass die WF\-Definition zwei spezielle Aktivitäten enthält: `PromoteValue<DateTime>` und `PromoteValue<Int32>`.  
  
 Der `Name`\-Member der `PromoteValue<Int32>`\-Aktivität wurde als `Count` definiert.Dies entspricht dem ersten `promotedValue`\-Element in der Konfiguration. `Value` wurde als `Counter`\-Workflowvariable definiert.Wenn der Workflow gespeichert wird, wird die `Counter`\-Workflowvariable als höher gestufte Eigenschaft in der `Value1`\-Spalte der `InstancePromotedProperties`\-Sicht gespeichert.  
  
 Der `Name`\-Member der `PromoteValue<DateTime>`\-Aktivität wurde als `LastIncrementedAt` definiert.Dies entspricht dem zweiten `promotedValue`\-Element in der Konfiguration. `Value` wurde als `TimeLastIncremented`\-Workflowvariable definiert.Wenn der Workflow beibehalten wird, wird daher der Wert für die `TimeLastIncremented`\-Workflowvariable als höher gestufte Eigenschaft in der `Value2`\-Spalte der `InstancePromotedProperties`\-Sicht beibehalten.  
  
 Beachten Sie, dass die `PromotedValue`\-Aktivität außerdem über den booleschen Member `ClearExistingPromotedData` verfügt.Wenn dieser Member auf `true` festgelegt wird, werden alle höher gestuften Eigenschaftswerte bis zu diesem Punkt im Workflow bereinigt.Beispielsweise ist eine Sequence\-Aktivität wie folgt definiert:  
  
1.  PromoteValue {Name \= “Count”, Value \= 3}  
  
2.  PromoteValue {Name \= “LastIncrementedAt”, Value \= 1\-1\-2000 }  
  
3.  Persist  
  
4.  PromoteValue {Name \= “Count”, Value \= 4, ClearExistingPromotedData \= true}  
  
5.  Persist  
  
 Bei der zweiten persistenten Speicherung wird der Wert für `Count` auf 4 erhöht.Der höher gestufte Wert für `LastIncrementedAt` ist jedoch `NULL`.Wenn `ClearExistingPromotedData` in Schritt 4 nicht auf `true` festgelegt worden wäre, würde der höher gestufte Wert für Count nach der zweiten persistenten Speicherung 4 lauten.Demzufolge wäre der höher gestufte Wert für `LastIncrementedAt` weiterhin 1\-1\-2000.  
  
### PropertyPromotionActivity  
 Diese Klassenbibliothek enthält die folgenden öffentlichen Klassen, um die Verwendung der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>\-Funktion zur Höherstufung zu vereinfachen.  
  
#### PromoteValue\-Klasse  
 Mit dieser Klasse wird eine Eigenschaft höher gestuft.Der Name der höher gestuften Eigenschaft sollte mit dem Namensattribut eines `promotedValue`\-Elements in der Konfiguration übereinstimmen.Diese Aktivität kann im Workflow\-Designer verwendet werden.Ein Beispiel zur Verwendung finden Sie in der CounterServiceApplication.  
  
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
  
 ClearExistingPromotedData \(Boolescher Wert\)  
 Löscht alle Werte, die vor dieser Aktivität höher gestuft wurden.  
  
 Name \(Zeichenfolge\)  
 Der Name, der diese Eigenschaft darstellt.Dieser sollte mit dem Namensattribut eines \<promotedValue\>\-Elements in der Konfiguration übereinstimmen.  
  
 Value \(InArgument\<T\>\)  
 Die Variable\/der Wert, die bzw. der in der Spalte gespeichert werden soll.  
  
#### PromoteValues\-Klasse  
 Stuft mehrere Eigenschaften hoch.Die Namen der höher gestuften Eigenschaften sollten mit allen Namensattributen der `promotedValue`\-Elemente in der Konfiguration übereinstimmen.Die Verwendung erfolgt analog zur `PromoteValue`\-Aktivität, mit dem Unterschied, dass mehrere Eigenschaften auf einmal höher gestuft werden können.Diese Aktivität kann nicht im Workflow\-Designer verwendet werden.  
  
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
  
#### SqlWorkflowInstanceStorePromotionBehavior  
 Wird von `SqlWorkflowInstanceStoreBehavior` abgeleitet.Mit dieser abgeleiteten Klasse wird ein benutzerdefinierter Persistenzteilnehmer \(ebenfalls Teil dieser Bibliothek\) als Workflowerweiterung hinzugefügt.Die Implementierung der beiden vorherigen Workflowaktivitäten ist von diesem benutzerdefinierten Persistenzteilnehmer abhängig.  
  
```  
public class SqlWorkflowInstanceStorePromotionBehavior :  
             SqlWorkflowInstanceStoreBehavior, IServiceBehavior  
{  
        public void Promote(string name, IEnumerable<string> promoteAsSqlVariant,  
                            IEnumerable<string> promoteAsBinary)  
  
}  
  
```  
  
 Diese Klassenbibliothek enthält auch die `ConfigurationElement`\-Implementierung für das `SqlWorkflowInstanceStorePromotionElement` sowie einen benutzerdefinierten Persistenzteilnehmer, der von den vorherigen Aktivitäten zur Höherstufung verwendet wird.  
  
### PropertyPromotionActivitySQLSample  
 Mit dieser SQL\-Datei wird eine `[dbo].[CounterService]`\-Sicht zusätzlich zur `[InstancePromotedProperties]`\-Sicht erstellt, um alle Instanzen mit einem CounterService\-Satz für die Höherstufung abzufragen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren:  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\PropertyPromotionActivity`  
  
## Siehe auch  
 [AppFabric\-Hosting\- und \-Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)