---
title: DataTable-Einschränkungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 4b7972c281786a4e36d0e9c1e455776a293423ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151285"
---
# <a name="datatable-constraints"></a>DataTable-Einschränkungen
Mithilfe von Einschränkungen können Sie die in einer <xref:System.Data.DataTable> enthaltenen Daten einschränken, um die Datenintegrität zu erhalten. Eine Einschränkung ist eine automatische Regel, die auf eine Spalte oder zugehörige Spalten angewendet wird und die die Vorgehensweise beim Ändern des Werts einer Spalte festlegt. Einschränkungen werden erzwungen, `System.Data.DataSet.EnforceConstraints` wenn die <xref:System.Data.DataSet> Eigenschaft des **true**ist. Ein Codebeispiel, in dem das Festlegen der `EnforceConstraints`-Eigenschaft veranschaulicht wird, finden Sie im <xref:System.Data.DataSet.EnforceConstraints%2A>-Referenzthema.  
  
 Es gibt zwei Arten von Einschränkungen in ADO.NET: die <xref:System.Data.ForeignKeyConstraint> und die <xref:System.Data.UniqueConstraint>. Standardmäßig werden beide Einschränkungen automatisch erstellt, wenn Sie eine Beziehung zwischen <xref:System.Data.DataRelation> zwei oder mehr Tabellen erstellen, indem Sie dem **DataSet**eine hinzufügen. Sie können dieses Verhalten jedoch deaktivieren, indem Sie beim Erstellen der Beziehung **createConstraints** = **false** angeben.  
  
## <a name="foreignkeyconstraint"></a>ForeignKeyConstraint  
 Eine **ForeignKeyConstraint** erzwingt Regeln, wie Aktualisierungen und Löschungen für verknüpfte Tabellen weitergegeben werden. Wenn z. B. ein Wert in einer Zeile einer Tabelle aktualisiert oder gelöscht wird und derselbe Wert auch in einer oder mehreren verknüpften Tabellen verwendet wird, bestimmt eine **ForeignKeyConstraint,** was in den verknüpften Tabellen geschieht.  
  
 Die <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> und Eigenschaften der **ForeignKeyConstraint** definieren die Aktion, die ausgeführt werden soll, wenn der Benutzer versucht, eine Zeile in einer verknüpften Tabelle zu löschen oder zu aktualisieren. In der folgenden Tabelle werden die verschiedenen Einstellungen beschrieben, die für die **Eigenschaften DeleteRule** und **UpdateRule** der **ForeignKeyConstraint**verfügbar sind.  
  
|Festgelegte Regel|Beschreibung|  
|------------------|-----------------|  
|**Cascade**|Verknüpfte Zeilen werden gelöscht oder aktualisiert.|  
|**SetNull**|Legen Sie Werte in verknüpften Zeilen auf **DBNull**fest.|  
|**SetDefault**|Für die Werte in verknüpften Zeilen wird der Standardwert festgelegt.|  
|**Keine**|In verknüpften Zeilen wird keine Aktion ausgeführt. Dies ist die Standardoption.|  
  
 Eine **ForeignKeyConstraint** kann Änderungen an verwandten Spalten einschränken und weitergeben. Abhängig von den Eigenschaften, die für die **ForeignKeyConstraint** einer Spalte festgelegt sind, führt das Ausführen bestimmter Vorgänge in der übergeordneten Zeile zu einer Ausnahme, wenn die **EnforceConstraints-Eigenschaft** des **DataSet** **true**ist. Wenn z. B. die **DeleteRule-Eigenschaft** der **ForeignKeyConstraint** **Keine**ist, kann eine übergeordnete Zeile nicht gelöscht werden, wenn sie untergeordnete Zeilen enthält.  
  
 Sie können eine Fremdschlüsseleinschränkung zwischen einzelnen Spalten oder zwischen einem Array von Spalten erstellen, indem Sie den **ForeignKeyConstraint-Konstruktor** verwenden. Übergeben Sie das resultierende **ForeignKeyConstraint-Objekt** an die **Add-Methode** der **Constraints-Eigenschaft** der Tabelle, die eine **ConstraintCollection**ist. Sie können Konstruktorargumente auch an mehrere Überladungen der **Add-Methode** einer **ConstraintCollection** übergeben, um eine **ForeignKeyConstraint**zu erstellen.  
  
 Beim Erstellen einer **ForeignKeyConstraint**können Sie die **Werte DeleteRule** und **UpdateRule** als Argumente an den Konstruktor übergeben oder sie als Eigenschaften festlegen, wie im folgenden Beispiel (wobei der **DeleteRule-Wert** auf **Keine**festgelegt ist).  
  
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
 Änderungen an Zeilen können mit der **AcceptChanges-Methode** akzeptiert oder mit der **RejectChanges-Methode** des **DataSet**, **DataTable**oder **DataRow**abgebrochen werden. Wenn ein **DataSet** **ForeignKeyConstraints**enthält, erzwingt das Aufrufen der **AcceptChanges-** oder **RejectChanges-Methoden** die **AcceptRejectRule**. Die **AcceptRejectRule-Eigenschaft** der **ForeignKeyConstraint** bestimmt, welche Aktion für die untergeordneten Zeilen ausgeführt wird, wenn **AcceptChanges** oder **RejectChanges** für die übergeordnete Zeile aufgerufen wird.  
  
 In der folgenden Tabelle sind die verfügbaren Einstellungen für **acceptRejectRule**aufgeführt.  
  
|Festgelegte Regel|Beschreibung|  
|------------------|-----------------|  
|**Cascade**|Änderungen in untergeordneten Zeilen werden akzeptiert oder zurückgewiesen.|  
|**Keine**|In den untergeordneten Zeilen wird keine Aktion ausgeführt. Dies ist die Standardoption.|  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Data.ForeignKeyConstraint>-Objekt erstellt, und es werden einige seiner Eigenschaften festgelegt (einschließlich der <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>-Regel) und dem <xref:System.Data.ConstraintCollection>-Objekt eines <xref:System.Data.DataTable>-Objekts hinzugefügt.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>UniqueConstraint  
 Das **UniqueConstraint-Objekt,** das entweder einer einzelnen Spalte oder einem Array von Spalten in einer **DataTable**zugewiesen werden kann, stellt sicher, dass alle Daten in der angegebenen Spalte oder spalten pro Zeile eindeutig sind. Sie können eine eindeutige Einschränkung für eine Spalte oder ein Array von Spalten erstellen, indem Sie den **UniqueConstraint-Konstruktor** verwenden. Übergeben Sie das resultierende **UniqueConstraint-Objekt** an die **Add-Methode** der **Constraints-Eigenschaft** der Tabelle, die eine **ConstraintCollection**ist. Sie können Konstruktorargumente auch an mehrere Überladungen der **Add-Methode** einer **ConstraintCollection** übergeben, um eine **UniqueConstraint**zu erstellen. Beim Erstellen einer **UniqueConstraint** für eine Spalte oder Spalten können Sie optional angeben, ob es sich bei der Spalte oder den Spalten um einen Primärschlüssel handelt.  
  
 Sie können auch eine eindeutige Einschränkung für eine Spalte erstellen, indem Sie die **Unique-Eigenschaft** der Spalte auf **true**festlegen. Alternativ wird durch Festlegen der **Unique-Eigenschaft** einer einzelnen Spalte auf **false** alle eindeutigen Einschränkungen entfernt, die möglicherweise vorhanden sind. Durch das Definieren einer oder mehrerer Spalten als Primärschlüssel für eine Tabelle wird automatisch eine eindeutige Einschränkung für die angegebene(n) Spalte(n) erstellt. Wenn Sie eine Spalte aus der **PrimaryKey-Eigenschaft** einer **DataTable**entfernen, wird die **UniqueConstraint** entfernt.  
  
 Im folgenden Beispiel wird eine **UniqueConstraint** für zwei Spalten einer **DataTable**erstellt.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [DataTable-Schemadefinition](datatable-schema-definition.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
