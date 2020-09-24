---
title: DataTable-Einschränkungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 1224518a9a16f48f770b6839317b9787da97377b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153273"
---
# <a name="datatable-constraints"></a>DataTable-Einschränkungen

Mithilfe von Einschränkungen können Sie die in einer <xref:System.Data.DataTable> enthaltenen Daten einschränken, um die Datenintegrität zu erhalten. Eine Einschränkung ist eine automatische Regel, die auf eine Spalte oder zugehörige Spalten angewendet wird und die die Vorgehensweise beim Ändern des Werts einer Spalte festlegt. Einschränkungen werden erzwungen, wenn die- `System.Data.DataSet.EnforceConstraints` Eigenschaft von den Wert <xref:System.Data.DataSet> **true**hat. Ein Codebeispiel, in dem das Festlegen der `EnforceConstraints`-Eigenschaft veranschaulicht wird, finden Sie im <xref:System.Data.DataSet.EnforceConstraints%2A>-Referenzthema.  
  
 Es gibt zwei Arten von Einschränkungen in ADO.NET: die <xref:System.Data.ForeignKeyConstraint> und die <xref:System.Data.UniqueConstraint>. Standardmäßig werden beide Einschränkungen automatisch erstellt, wenn Sie eine Beziehung zwischen zwei oder mehr Tabellen erstellen, indem Sie <xref:System.Data.DataRelation> dem **DataSet**eine hinzufügen. Sie können dieses Verhalten jedoch deaktivieren, indem Sie **createConstraints**  =  **false** beim Erstellen der Beziehung die Angabe von "beim Erstellen von" "" "beim Erstellen von"  
  
## <a name="foreignkeyconstraint"></a>ForeignKeyConstraint  

 Eine fremd **Schlüssel Einschränkung** erzwingt Regeln für die Weitergabe von Updates und Löschungen in verknüpften Tabellen. Wenn z. b. ein Wert in einer Zeile einer Tabelle aktualisiert oder gelöscht wird und derselbe Wert auch in einer oder mehreren verknüpften Tabellen verwendet wird, bestimmt eine fremd **Schlüssel Einschränkung** , was in den verknüpften Tabellen passiert.  
  
 Die <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> -Eigenschaft und die-Eigenschaft <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> der fremd **Schlüssel Einschränkung** definieren die Aktion, die durchgeführt werden soll, wenn der Benutzer versucht, eine Zeile in einer verknüpften Tabelle zu löschen oder zu aktualisieren. In der folgenden Tabelle werden die verschiedenen Einstellungen beschrieben, die für die **DeleteRule** -Eigenschaft und die **UpdateRule** -Eigenschaft der fremd **Schlüssel Einschränkung**verfügbar sind.  
  
|Festgelegte Regel|Beschreibung|  
|------------------|-----------------|  
|**Cascade**|Verknüpfte Zeilen werden gelöscht oder aktualisiert.|  
|**SetNull**|Legen Sie Werte in verknüpften Zeilen auf **DBNull**fest.|  
|**SetDefault**|Für die Werte in verknüpften Zeilen wird der Standardwert festgelegt.|  
|**None**|In verknüpften Zeilen wird keine Aktion ausgeführt. Dies ist die Standardeinstellung.|  
  
 Eine fremd **Schlüssel Einschränkung** kann die Änderungen an verknüpften Spalten einschränken und übertragen. Abhängig von den Eigenschaften, die für die fremd **Schlüssel Einschränkung** einer Spalte festgelegt sind, führt die Ausführung bestimmter Vorgänge in der übergeordneten Zeile zu einer Ausnahme, wenn die **EnforceConstraints** -Eigenschaft des **DataSets** auf **true**festgelegt ist. Wenn z. b. die **DeleteRule** -Eigenschaft der fremd **Schlüssel Einschränkung** **None**ist, kann eine übergeordnete Zeile nicht gelöscht werden, wenn Sie über untergeordnete Zeilen verfügt.  
  
 Sie können eine FOREIGN KEY-Einschränkung zwischen einzelnen Spalten oder zwischen einem Spalten Array erstellen, indem Sie den Foreign **nkeyeinschränkung** -Konstruktor verwenden. Übergeben Sie das resultierende **fremdkeyeinschränkungs** -Objekt an die **Add** **-Methode** der Einschränkungs Eigenschaft der Tabelle, bei der es sich um eine **Einschränkungs**Auflistung handelt. Sie können auch Konstruktorargumente an mehrere über Ladungen der **Add** -Methode einer **Einschränkungs** Auflistung übergeben, um eine fremd **Schlüssel Einschränkung**zu erstellen.  
  
 Wenn Sie eine fremd **Schlüssel Einschränkung**erstellen, können Sie die **DeleteRule** -und **UpdateRule** -Werte als Argumente an den Konstruktor übergeben, oder Sie können Sie als Eigenschaften festlegen, wie im folgenden Beispiel dargestellt (wobei der **DeleteRule** -Wert auf " **None**" festgelegt ist).  
  
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

 Änderungen an Zeilen können mithilfe der **akzeptchanges** -Methode akzeptiert oder mit der **RejectChanges** -Methode des **DataSets**, **Datable**oder **DataRow**abgebrochen werden. Wenn ein **DataSet** fremd **Schlüssel Einschränkungen**enthält, erzwingt das Aufrufen der Methoden " **akzeptchanges** " oder " **RejectChanges** " das " **akzeptrejectrule**". Die Eigenschaft " **Accept trejectrule** " der fremd **Schlüssel Einschränkung** bestimmt, welche Aktion für die untergeordneten Zeilen ausgeführt wird, wenn " **Accept Changes** " oder " **RejectChanges** " in der übergeordneten Zeile aufgerufen wird.  
  
 In der folgenden Tabelle sind die verfügbaren Einstellungen für " **akzeptrejectrule**" aufgeführt.  
  
|Festgelegte Regel|Beschreibung|  
|------------------|-----------------|  
|**Cascade**|Änderungen in untergeordneten Zeilen werden akzeptiert oder zurückgewiesen.|  
|**None**|In den untergeordneten Zeilen wird keine Aktion ausgeführt. Dies ist die Standardeinstellung.|  
  
### <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird ein <xref:System.Data.ForeignKeyConstraint>-Objekt erstellt, und es werden einige seiner Eigenschaften festgelegt (einschließlich der <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>-Regel) und dem <xref:System.Data.ConstraintCollection>-Objekt eines <xref:System.Data.DataTable>-Objekts hinzugefügt.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>UniqueConstraint  

 Das **UniqueConstraint** -Objekt, das entweder einer einzelnen Spalte oder einem Array von Spalten in einer **Daten**Tabelle zugewiesen werden kann, stellt sicher, dass alle Daten in den angegebenen Spalten pro Zeile eindeutig sind. Sie können eine Unique-Einschränkung für eine Spalte oder ein Array von Spalten erstellen, indem Sie den **UniqueConstraint** -Konstruktor verwenden. Übergeben Sie das **sich ergebende** **UniqueConstraint** -Objekt an die **Add** -Methode der Einschränkungs Eigenschaft der Tabelle, bei der es sich um eine **Einschränkungs**Auflistung handelt. Sie können auch Konstruktorargumente an mehrere über Ladungen der **Add** -Methode einer **Einschränkungs** Auflistung übergeben, um **UniqueConstraint**zu erstellen. Beim Erstellen eines **UniqueConstraint** für eine Spalte oder Spalten können Sie optional angeben, ob es sich bei der Spalte oder den Spalten um einen Primärschlüssel handelt.  
  
 Sie können auch eine Unique-Einschränkung für eine Spalte erstellen, indem Sie die **Unique** -Eigenschaft der Spalte auf **true**festlegen. Wenn Sie die **Unique** -Eigenschaft einer einzelnen Spalte auf **false** festlegen, werden alle ggf. vorhandenen eindeutigen Einschränkungen entfernt. Durch das Definieren einer oder mehrerer Spalten als Primärschlüssel für eine Tabelle wird automatisch eine eindeutige Einschränkung für die angegebene(n) Spalte(n) erstellt. Wenn Sie eine Spalte aus der **PrimaryKey** -Eigenschaft einer **Daten**Tabelle entfernen, wird **UniqueConstraint** entfernt.  
  
 Im folgenden Beispiel wird eine **UniqueConstraint** für zwei Spalten einer **Daten**Tabelle erstellt.  
  
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
