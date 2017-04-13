---
title: "&#39;DataTable&#39;-Einschr&#228;nkungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# &#39;DataTable&#39;-Einschr&#228;nkungen
Mithilfe von Einschränkungen können Sie die in einer <xref:System.Data.DataTable> enthaltenen Daten einschränken, um die Datenintegrität zu erhalten.  Eine Einschränkung ist eine automatische Regel, die auf eine Spalte oder zugehörige Spalten angewendet wird und die die Vorgehensweise beim Ändern des Werts einer Spalte festlegt.  Einschränkungen werden erzwungen, wenn die  `System.Data.DataSet.EnforceConstraints`\-Eigenschaft des <xref:System.Data.DataSet>\-Objekts auf **true** festgelegt wird.  Ein Codebeispiel, in dem das Festlegen der `EnforceConstraints`\-Eigenschaft veranschaulicht wird, finden Sie im <xref:System.Data.DataSet.EnforceConstraints%2A>\-Referenzthema.  
  
 Es gibt zwei Arten von Einschränkungen in ADO.NET: die <xref:System.Data.ForeignKeyConstraint> und die <xref:System.Data.UniqueConstraint>.  In der Standardeinstellung werden beide Einschränkungen automatisch erstellt, wenn Sie eine Beziehung zwischen zwei oder mehreren Tabellen herstellen, indem Sie dem **DataSet** eine <xref:System.Data.DataRelation> hinzufügen.  Dieses Verhalten kann jedoch auch deaktiviert werden, indem beim Erstellen der Beziehung **createConstraints** \= **false** festgelegt wird.  
  
## ForeignKeyConstraint  
 Mit den durch **ForeignKeyConstraint** festgelegten Regeln wird bestimmt, wie Updates und Löschvorgänge an zugehörige Tabellen weitergegeben werden.  Wenn beispielsweise ein Wert in einer Zeile einer Tabelle aktualisiert oder gelöscht und dieser Wert auch in einer oder mehreren zugehörigen Tabellen verwendet wird, wird mit einer **ForeignKeyConstraint** festgelegt, was in den zugehörigen Tabellen geschieht.  
  
 Mithilfe der <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A>\-Eigenschaft und der <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A>\-Eigenschaft der **ForeignKeyConstraint** werden die Aktionen definiert, die beim Versuch des Benutzers, eine Zeile in einer zugehörigen Tabelle zu löschen oder zu aktualisieren, ausgeführt werden.  In der folgenden Tabelle werden die verschiedenen Einstellungen beschrieben, die für die **DeleteRule**\-Eigenschaft und die **UpdateRule**\-Eigenschaft der **ForeignKeyConstraint** verfügbar sind.  
  
|Festgelegte Regel|Beschreibung|  
|-----------------------|------------------|  
|**Cascade**|Verknüpfte Zeilen werden gelöscht oder aktualisiert.|  
|**SetNull**|Für die Werte in verknüpften Zeilen wird **DBNull** festgelegt.|  
|**SetDefault**|Für die Werte in verknüpften Zeilen wird der Standardwert festgelegt.|  
|**Keine**|In verknüpften Zeilen wird keine Aktion ausgeführt.  Dies ist die Standardeinstellung.|  
  
 Eine **ForeignKeyConstraint** kann Änderungen an verknüpften Spalten sowohl einschränken als auch weitergeben.  Je nachdem, welche Eigenschaften für die **ForeignKeyConstraint** einer Spalte festgelegt werden und ob die **EnforceConstraints**\-Eigenschaft des **DataSet** auf **true** festgelegt wird, löst das Ausführen von bestimmten Operationen in der übergeordneten Zeile eine Ausnahme aus.  Wenn beispielsweise die **DeleteRule**\-Eigenschaft der **ForeignKeyConstraint** auf **None** festgelegt ist, kann eine übergeordnete Zeile nicht gelöscht werden, wenn sie über untergeordnete Zeilen verfügt.  
  
 Sie können eine Fremdschlüsseleinschränkung zwischen einzelnen Spalten oder in einem Spaltenarray erstellen, indem Sie den **ForeignKeyConstraint**\-Konstruktor verwenden.  Übergeben Sie das resultierende **ForeignKeyConstraint**\-Objekt an die **Add**\-Methode der **Constraints**\-Eigenschaft der Tabelle. Bei dieser handelt es sich um eine **ConstraintCollection**.  Sie können auch Konstruktorargumente an mehrere Überladungen der **Add**\-Methode einer **ConstraintCollection** übergeben, um eine **ForeignKeyConstraint** zu erstellen.  
  
 Beim Erstellen einer **ForeignKeyConstraint** können Sie den **DeleteRule**\-Wert und den **UpdateRule**\-Wert als Argumente an den Konstruktor übergeben oder als Eigenschaften festlegen. Dies wird im folgenden Beispiel gezeigt, bei dem der **DeleteRule**\-Wert auf **None** festgelegt wird.  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None    
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],   
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;    
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### AcceptRejectRule  
 Änderungen an Zeilen können mithilfe der **AcceptChanges**\-Methode übernommen oder mit der **RejectChanges**\-Methode des **DataSet**, der **DataTable** oder der **DataRow** abgebrochen werden.  Wenn die **ForeignKeyConstraints** in einem **DataSet** enthalten sind, wird durch Aufrufen der **AcceptChanges**\-Methode oder der **RejectChanges**\-Methode die **AcceptRejectRule** erzwungen.  Die **AcceptRejectRule**\-Eigenschaft der **ForeignKeyConstraint** bestimmt, welche Aktion in den untergeordneten Zeilen ausgeführt wird, wenn in der übergeordneten Zeile **AcceptChanges** oder **RejectChanges** aufgerufen wird.  
  
 In der folgenden Tabelle werden die für die **AcceptRejectRule** verfügbaren Einstellungen aufgeführt.  
  
|Festgelegte Regel|Beschreibung|  
|-----------------------|------------------|  
|**Cascade**|Änderungen in untergeordneten Zeilen werden akzeptiert oder zurückgewiesen.|  
|**Keine**|In den untergeordneten Zeilen wird keine Aktion ausgeführt.  Dies ist die Standardeinstellung.|  
  
### Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Data.ForeignKeyConstraint>\-Objekt erstellt, und es werden einige seiner Eigenschaften festgelegt \(einschließlich der <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>\-Regel\) und dem <xref:System.Data.ConstraintCollection>\-Objekt eines <xref:System.Data.DataTable>\-Objekts hinzugefügt.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## UniqueConstraint  
 Das **UniqueConstraint**\-Objekt, das entweder einer einzelnen Spalte oder einem Array aus Spalten in einer **DataTable** zugewiesen werden kann, stellt sicher, dass alle Daten in den angegebenen Spalten pro Zeile eindeutig sind.  Sie können eine eindeutige Einschränkung für eine Spalte oder ein Array aus Spalten erstellen, indem Sie den **UniqueConstraint**\-Konstruktor verwenden.  Übergeben Sie das resultierende **UniqueConstraint**\-Objekt an die **Add**\-Methode der **Constraints**\-Eigenschaft der Tabelle. Bei dieser handelt es sich um eine **ConstraintCollection**.  Sie können auch Konstruktorargumente an mehrere Überladungen der **Add**\-Methode einer **ConstraintCollection** übergeben, um eine **UniqueConstraint** zu erstellen.  Beim Erstellen einer **UniqueConstraint** für eine oder mehrere Spalten können Sie optional festlegen, ob die Spalte\(n\) einen Primärschlüssel darstellen.  
  
 Sie können auch eine eindeutige Einschränkung für eine Spalte erstellen, indem Sie die **Unique**\-Eigenschaft der Spalte auf **true** festlegen.  Alternativ werden alle möglicherweise vorhandenen eindeutigen Einschränkungen entfernt, wenn die **Unique**\-Eigenschaft einer einzelnen Spalte auf **false** festgelegt wird.  Durch das Definieren einer oder mehrerer Spalten als Primärschlüssel für eine Tabelle wird automatisch eine eindeutige Einschränkung für die angegebene\(n\) Spalte\(n\) erstellt.  Wenn Sie eine Spalte aus der **PrimaryKey**\-Eigenschaft einer **DataTable** entfernen, wird die **UniqueConstraint** entfernt.  
  
 Im folgenden Beispiel wird eine **UniqueConstraint** für zwei Spalten einer **DataTable** erstellt.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]   
    {custTable.Columns["CustomerID"],   
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## Siehe auch  
 <xref:System.Data.DataRelation>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.ForeignKeyConstraint>   
 <xref:System.Data.UniqueConstraint>   
 ['DataTable'\-Schemadefinition](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)