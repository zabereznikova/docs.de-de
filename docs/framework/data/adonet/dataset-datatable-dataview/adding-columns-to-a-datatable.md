---
title: Hinzufügen von Spalten zu einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 2e7008f6693d7d76520a7ff6ae9172e28e4990c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207005"
---
# <a name="adding-columns-to-a-datatable"></a>Hinzufügen von Spalten zu einer "DataTable"
Ein <xref:System.Data.DataTable> enthält eine Auflistung von <xref:System.Data.DataColumn> -Objekten verwiesen wird, durch die **Spalten** Eigenschaft der Tabelle. Diese Auflistung von Spalten, zusammen mit allen Einschränkungen, definiert das Schema oder die Struktur der Tabelle.  
  
 Erstellen Sie **DataColumn** Objekte innerhalb einer Tabelle mithilfe der **DataColumn** Konstruktor oder durch Aufrufen der **hinzufügen** -Methode der der **Spalten**Eigenschaft der Tabelle, die ist eine <xref:System.Data.DataColumnCollection>. Die **hinzufügen** -Methode akzeptiert optionale **ColumnName**, **DataType**, und **Ausdruck** Argumente und erstellt einen neuen  **DataColumn** als Member der Auflistung. Er akzeptiert auch eine vorhandene **DataColumn** -Objekt und fügt es der Collection hinzu und gibt einen Verweis auf die hinzugefügte **DataColumn** gegebenenfalls. Da **DataTable** Objekte sind nicht spezifisch für jede Datenquelle, die .NET Framework-Typen werden verwendet, wenn Sie den Datentyp der angeben einer **DataColumn**.  
  
 Im folgenden Beispiel wird die vier Spalten zu einer **DataTable**.  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 Im Beispiel beachten Sie, dass die Eigenschaften für die **CustID** -Spalte darauf festgelegt sind, die nicht **DBNull** Werte und begrenzen die Werte eindeutig sein. Jedoch wenn Sie definieren die **CustID** Spalte als die Primärschlüsselspalte der Tabelle, die **AllowDBNull** -Eigenschaft wird auf automatisch festgelegt werden **"false"** und die **Unique** Eigenschaft wird automatisch festgelegt werden, um **"true"**. Weitere Informationen finden Sie unter [Definieren von Primärschlüsseln](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
> [!CAUTION]
>  Wenn ein Spaltenname nicht für eine Spalte angegeben wird, erhält die Spalte einen Standardnamen der Spalte*N,* beginnend mit "Column1", wenn es hinzugefügt wird die **DataColumnCollection**. Es wird empfohlen, dass Sie die Benennungskonvention "Spalte*N*" Wenn Sie einen Spaltennamen angeben, daran, dass der Name, die Sie bereitstellen steht in Konflikt mit einem bereits vorhandenen Standardspaltennamen in der **DataColumnCollection**. Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.  
  
 Wenn Sie das <xref:System.Xml.Linq.XElement>-Element als <xref:System.Data.DataColumn.DataType%2A> einer <xref:System.Data.DataColumn> in der <xref:System.Data.DataTable> verwenden, funktioniert die XML-Serialisierung beim Einlesen von Daten nicht. Wenn Sie beispielsweise ein <xref:System.Xml.XmlDocument> mit der `DataTable.WriteXml`-Methode schreiben, wird bei der Serialisierung in XML ein zusätzlicher übergeordneter Knoten im <xref:System.Xml.Linq.XElement>-Element hinzugefügt. Um dieses Problem zu umgehen, verwenden Sie den <xref:System.Data.SqlTypes.SqlXml>-Typ statt des <xref:System.Xml.Linq.XElement>-Elements. `ReadXml` und `WriteXml` funktionieren ordnungsgemäß mit <xref:System.Data.SqlTypes.SqlXml>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [DataTable-Schemadefinition](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- ["DataTables"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
