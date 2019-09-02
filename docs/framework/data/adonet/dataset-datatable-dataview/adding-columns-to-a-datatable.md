---
title: Hinzufügen von Spalten zu einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 105537a5fccef6de7266407c78cc915f8c5d8678
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204057"
---
# <a name="adding-columns-to-a-datatable"></a>Hinzufügen von Spalten zu einer "DataTable"
Eine <xref:System.Data.DataTable> enthält eine Auflistung von <xref:System.Data.DataColumn> -Objekten, auf die von der **Columns** -Eigenschaft der Tabelle verwiesen wird. Diese Auflistung von Spalten, zusammen mit allen Einschränkungen, definiert das Schema oder die Struktur der Tabelle.  
  
 Sie erstellen **datacolenn** -Objekte innerhalb einer Tabelle mithilfe des **datacolumschlag** -Konstruktors oder durch Aufrufen der **Add** -Methode der **Columns** -Eigenschaft der Tabelle, bei der es sich <xref:System.Data.DataColumnCollection>um eine handelt. Die **Add** -Methode akzeptiert optionale **ColumnName**-, **DataType**-und **Expression** -Argumente und erstellt eine neue **datacolenn** als Member der Auflistung. Außerdem akzeptiert Sie ein vorhandenes **datacolenumn** -Objekt und fügt es der Collection hinzu und gibt bei Bedarf einen Verweis auf die hinzugefügte **datacolenn** zurück. Da Datentabelle nicht spezifisch für Datenquellen ist, werden .NET Framework Typen beim Angeben des Datentyps einer **datacolenumn**verwendet.  
  
 Im folgenden Beispiel werden vier Spalten zu einer **Daten**Tabelle hinzugefügt.  
  
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
  
 Beachten Sie im Beispiel, dass die Eigenschaften für die **CustId-** Spalte so festgelegt sind, dass **DBNull** -Werte nicht zulässig sind, und dass die Werte als eindeutig festgelegt werden. Wenn Sie die **CustId-** Spalte jedoch als Primärschlüssel Spalte der Tabelle definieren, wird die **AllowDBNull** -Eigenschaft automatisch auf **false** festgelegt, und die **Unique** -Eigenschaft wird automatisch auf **true**festgelegt. Weitere Informationen finden Sie unter [Definieren von primär Schlüsseln](defining-primary-keys.md).  
  
> [!CAUTION]
> Wenn für eine Spalte kein Spaltenname angegeben wird, erhält die Spalte einen inkrementellen Standardnamen von Spalte*N,* beginnend mit "Column1", wenn Sie der **datacolenncollection**hinzugefügt wird. Es wird empfohlen, dass Sie die Benennungs Konvention "Column*N*" vermeiden, wenn Sie einen Spaltennamen angeben, da der von Ihnen bereitgestellte Name möglicherweise mit einem vorhandenen Standard Spaltennamen in der **datacolenncollection**in Konflikt steht. Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.  
  
 Wenn Sie das <xref:System.Xml.Linq.XElement>-Element als <xref:System.Data.DataColumn.DataType%2A> einer <xref:System.Data.DataColumn> in der <xref:System.Data.DataTable> verwenden, funktioniert die XML-Serialisierung beim Einlesen von Daten nicht. Wenn Sie beispielsweise ein <xref:System.Xml.XmlDocument> mit der `DataTable.WriteXml`-Methode schreiben, wird bei der Serialisierung in XML ein zusätzlicher übergeordneter Knoten im <xref:System.Xml.Linq.XElement>-Element hinzugefügt. Um dieses Problem zu umgehen, verwenden Sie den <xref:System.Data.SqlTypes.SqlXml>-Typ statt des <xref:System.Xml.Linq.XElement>-Elements. `ReadXml` und `WriteXml` funktionieren mit <xref:System.Data.SqlTypes.SqlXml> ordnungsgemäß.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [DataTable-Schemadefinition](datatable-schema-definition.md)
- [DataTables](datatables.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
