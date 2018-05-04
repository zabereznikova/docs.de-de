---
title: DataTable-Einschränkungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 95bbba30bc9cd75d1694d7d8062bc9a6e6105084
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="datatable-constraints"></a>DataTable-Einschränkungen
Mithilfe von Einschränkungen können Sie die in einer <xref:System.Data.DataTable> enthaltenen Daten einschränken, um die Datenintegrität zu erhalten. Eine Einschränkung ist eine automatische Regel, die auf eine Spalte oder zugehörige Spalten angewendet wird und die die Vorgehensweise beim Ändern des Werts einer Spalte festlegt. Einschränkungen werden erzwungen, wenn die `System.Data.DataSet.EnforceConstraints` Eigenschaft der <xref:System.Data.DataSet> ist **"true"**. Ein Codebeispiel, in dem das Festlegen der `EnforceConstraints`-Eigenschaft veranschaulicht wird, finden Sie im <xref:System.Data.DataSet.EnforceConstraints%2A>-Referenzthema.  
  
 Es gibt zwei Arten von Einschränkungen in ADO.NET: die <xref:System.Data.ForeignKeyConstraint> und die <xref:System.Data.UniqueConstraint>. Standardmäßig beide Einschränkungen automatisch erstellt, wenn Sie eine Beziehung zwischen zwei oder mehr Tabellen durch Hinzufügen von erstellen eine <xref:System.Data.DataRelation> auf die **DataSet**. Sie können dieses Verhalten jedoch deaktivieren, durch Angabe **CreateConstraints** = **"false"** beim Erstellen der Beziehung.  
  
## <a name="foreignkeyconstraint"></a>ForeignKeyConstraint  
 Ein **ForeignKeyConstraint** festgelegten Regeln wie Updates und Löschvorgänge an zugehörige Tabellen weitergegeben werden. Wenn ein Wert in einer Zeile einer Tabelle aktualisiert oder gelöscht, ist dieser Wert wird auch verwendet, in einem oder mehreren zugehörigen Tabellen, z. B. eine **ForeignKeyConstraint** bestimmt, was in den zugehörigen Tabellen geschieht.  
  
 Die <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> und <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> Eigenschaften der **ForeignKeyConstraint** definieren die Aktion, die ausgeführt werden, wenn der Benutzer versucht, löschen oder Aktualisieren einer Zeile in einer verknüpften Tabelle. Die folgende Tabelle beschreibt die verschiedenen Einstellungen für die **DeleteRule** und **UpdateRule** Eigenschaften der **ForeignKeyConstraint**.  
  
|Festgelegte Regel|Beschreibung|  
|------------------|-----------------|  
|**Cascade**|Verknüpfte Zeilen werden gelöscht oder aktualisiert.|  
|**SetNull**|Legen Sie Werte in verknüpften Zeilen **DBNull**.|  
|**SetDefault**|Für die Werte in verknüpften Zeilen wird der Standardwert festgelegt.|  
|**Keine**|In verknüpften Zeilen wird keine Aktion ausgeführt. Dies ist die Standardeinstellung.|  
  
 Ein **ForeignKeyConstraint** einschränken können, als auch weitergeben, Änderungen an verknüpften Spalten. Je nach den Eigenschaften für die **ForeignKeyConstraint** einer Spalte, wenn der **EnforceConstraints** Eigenschaft von der **DataSet** ist **"true"**, bestimmte Vorgänge in der übergeordneten Zeile eine Ausnahme ausgelöst wird. Z. B. wenn die **DeleteRule** Eigenschaft von der **ForeignKeyConstraint** ist **keine**, eine übergeordnete Zeile kann nicht gelöscht werden, wenn es über untergeordnete Zeilen verfügt.  
  
 Sie können eine fremdschlüsseleinschränkung zwischen einzelnen Spalten oder ein Array von Spalten mit Erstellen der **ForeignKeyConstraint** Konstruktor. Übergeben Sie das resultierende **ForeignKeyConstraint** -Objekt an die **hinzufügen** -Methode der tabellenspezifischen **Einschränkungen** Eigenschaft, die eine **ConstraintCollection**. Sie können auch Konstruktorargumente an mehrere Überladungen der übergeben der **hinzufügen** Methode eine **ConstraintCollection** zum Erstellen einer **ForeignKeyConstraint**.  
  
 Beim Erstellen einer **ForeignKeyConstraint**, können Sie übergeben die **DeleteRule** und **UpdateRule** Werte an den Konstruktor als Argumente an, oder Sie können als Eigenschaften wie in Festlegen der Beispiel (wobei der **DeleteRule** Wert wird festgelegt, um **keine**).  
  
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
  
### <a name="acceptrejectrule"></a>AcceptRejectRule  
 Änderungen an Zeilen können angenommen werden, mithilfe der **AcceptChanges** Methode oder abgebrochenen mithilfe der **RejectChanges** Methode der **DataSet**, **DataTable**, oder **DataRow**. Wenn eine **DataSet** enthält **ForeignKeyConstraints**, wird durch Aufrufen der **AcceptChanges** oder **RejectChanges** Methoden erzwingt die  **AcceptRejectRule**. Die **AcceptRejectRule** Eigenschaft von der **ForeignKeyConstraint** bestimmt, welche Aktion ergriffen wird, auf dem untergeordneten Element Datenzeilen **AcceptChanges** oder  **RejectChanges** wird in der übergeordneten Zeile aufgerufen.  
  
 Die folgende Tabelle enthält die verfügbaren Einstellungen für die **AcceptRejectRule**.  
  
|Festgelegte Regel|Beschreibung|  
|------------------|-----------------|  
|**Cascade**|Änderungen in untergeordneten Zeilen werden akzeptiert oder zurückgewiesen.|  
|**Keine**|In den untergeordneten Zeilen wird keine Aktion ausgeführt. Dies ist die Standardeinstellung.|  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Data.ForeignKeyConstraint>-Objekt erstellt, und es werden einige seiner Eigenschaften festgelegt (einschließlich der <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>-Regel) und dem <xref:System.Data.ConstraintCollection>-Objekt eines <xref:System.Data.DataTable>-Objekts hinzugefügt.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>UniqueConstraint  
 Die **UniqueConstraint** -Objekt, das auf eine einzelne Spalte oder in ein Array von Spalten in zugewiesen werden, kann eine **DataTable**, wird sichergestellt, dass alle Daten in der angegebenen Spalte oder Spalten pro Zeile eindeutig ist. Sie können eine unique-Einschränkung für eine Spalte oder ein Array aus Spalten erstellen, mit der **UniqueConstraint** Konstruktor. Übergeben Sie das resultierende **UniqueConstraint** -Objekt an die **hinzufügen** -Methode der tabellenspezifischen **Einschränkungen** Eigenschaft, die eine **ConstraintCollection**. Sie können auch Konstruktorargumente an mehrere Überladungen der übergeben der **hinzufügen** Methode eine **ConstraintCollection** zum Erstellen einer **UniqueConstraint**. Beim Erstellen einer **UniqueConstraint** für eine Spalte oder Spalten, Sie können optional angeben, ob die Spalte(n) einen Primärschlüssel darstellen.  
  
 Sie können auch eine unique-Einschränkung für eine Spalte erstellen, durch Festlegen der **Unique** Eigenschaft der Spalte, die **"true"**. Alternativ können Sie festlegen der **Unique** Eigenschaft von einer einzelnen Spalte auf **"false"** entfernt unique-Einschränkung, die möglicherweise vorhanden. Durch das Definieren einer oder mehrerer Spalten als Primärschlüssel für eine Tabelle wird automatisch eine eindeutige Einschränkung für die angegebene(n) Spalte(n) erstellt. Wenn Sie eine Spalte aus Entfernen der **PrimaryKey** Eigenschaft eine **DataTable**, die **UniqueConstraint** wird entfernt.  
  
 Das folgende Beispiel erstellt eine **UniqueConstraint** für zwei Spalten mit einem **DataTable**.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataRelation>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.ForeignKeyConstraint>  
 <xref:System.Data.UniqueConstraint>  
 [DataTable-Schemadefinition](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
