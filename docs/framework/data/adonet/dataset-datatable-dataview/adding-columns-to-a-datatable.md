---
title: "Hinzuf&#252;gen von Spalten zu einer &#39;DataTable&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Hinzuf&#252;gen von Spalten zu einer &#39;DataTable&#39;
Eine <xref:System.Data.DataTable> enthält eine Auflistung von <xref:System.Data.DataColumn>\-Objekten, auf die von der **Columns**\-Eigenschaft der Tabelle verwiesen wird.  Diese Auflistung von Spalten, zusammen mit allen Einschränkungen, definiert das Schema oder die Struktur der Tabelle.  
  
 **DataColumn**\-Objekte werden innerhalb einer Tabelle mit dem **DataColumn**\-Konstruktor oder durch Aufrufen der **Add**\-Methode der **Columns**\-Eigenschaft der Tabelle erstellt, die eine <xref:System.Data.DataColumnCollection> ist.  Die **Add**\-Methode akzeptiert optional die Argumente **ColumnName**, **DataType** und **Expression** und erstellt eine neue **DataColumn** als einen Member der Auflistung.  Außerdem akzeptiert die Methode ein vorhandenes **DataColumn**\-Objekt, fügt es der Auflistung hinzu und gibt einen Verweis auf die hinzugefügte **DataColumn** zurück, wenn dieser angefordert wird.  Da **DataTable**\-Objekte nicht für eine Datenquelle spezifisch sind, werden .NET Framework\-Typen zum Angeben des Datentyps einer **DataColumn** verwendet.  
  
 Im folgenden Beispiel werden vier Spalten zu einer **DataTable** hinzugefügt.  
  
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
  
 Beachten Sie im Beispiel, dass die Eigenschaften für die **CustID**\-Spalte darauf festgelegt sind, **DBNull**\-Werte nicht zuzulassen, und Werte darauf einzuschränken, eindeutig zu sein.  Wenn Sie jedoch die **CustID**\-Spalte als die Primärschlüsselspalte der Tabelle definieren, wird die **AllowDBNull**\-Eigenschaft automatisch auf **false** festgelegt und die **Unique**\-Eigenschaft wird automatisch auf **true** festgelegt.  Weitere Informationen finden Sie unter [Definieren von Primärschlüsseln](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
> [!CAUTION]
>  Wenn für eine Spalte kein Spaltenname angegeben wird, erhält die Spalte einen Standardnamen "Column*N,*" beginnend mit "Column1", der jeweils um eins erhöht wird, wenn sie der **DataColumnCollection** hinzugefügt wird.  Es wird davon abgeraten, die Benennungskonvention "Column*N*" zum Benennen einer Spalte zu verwenden, wenn Sie einen Spaltennamen bereitstellen, da der Name u. U. einen Konflikt mit einem bereits vorhandenen Standardspaltennamen in der **DataColumnCollection** verursacht.  Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.  
  
 Wenn Sie das <xref:System.Xml.XLinq.XElement>\-Element als <xref:System.Data.DataColumn.DataType%2A> einer <xref:System.Data.DataColumn> in der <xref:System.Data.DataTable> verwenden, funktioniert die XML\-Serialisierung beim Einlesen von Daten nicht.  Wenn Sie beispielsweise ein <xref:System.Xml.XmlDocument> mit der `DataTable.WriteXml`\-Methode schreiben, wird bei der Serialisierung in XML ein zusätzlicher übergeordneter Knoten im <xref:System.Xml.XLinq.XElement>\-Element hinzugefügt.  Um dieses Problem zu umgehen, verwenden Sie den <xref:System.Data.SqlTypes.SqlXml>\-Typ statt des <xref:System.Xml.XLinq.XElement>\-Elements.  `ReadXml` und `WriteXml` funktionieren mit <xref:System.Data.SqlTypes.SqlXml> ordnungsgemäß.  
  
## Siehe auch  
 <xref:System.Data.DataColumn>   
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataTable>   
 ['DataTable'\-Schemadefinition](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)