---
title: "Schreiben von &#39;DataSet&#39;-Schema-Informationen als XSD | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Schreiben von &#39;DataSet&#39;-Schema-Informationen als XSD
Sie können das Schema eines <xref:System.Data.DataSet> als XSD\-Schema \(XML Schema Definition Language\) schreiben, sodass Sie es mit oder ohne zugehörige Daten in ein XML\-Dokument übertragen können.  Das XML\-Schema kann in eine Datei, einen Stream, einen <xref:System.Xml.XmlWriter> oder eine Zeichenfolge geschrieben werden und eignet sich zum Generieren eines **DataSet** mit strikter Typbindung.  Weitere Informationen zu **DataSet**\-Objekten mit strikter Typbindung finden Sie unter [Typisierte 'DataSets'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 Mit der **ColumnMapping**\-Eigenschaft des <xref:System.Data.DataColumn>\-Objekts kann festgelegt werden, wie eine Tabellenspalte im XML\-Schema dargestellt wird.  Weitere Informationen finden Sie unter "Zuordnen von Spalten zu XML\-Elementen, \-Attributen und \-Text" im Abschnitt [Schreiben von 'DataSet'\-Inhalt als XML\-Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Verwenden Sie zum Schreiben eines **DataSet** als XML\-Schema in eine Datei, einen Stream oder **XmlWriter** die **WriteXmlSchema**\-Methode des **DataSet**.  **WriteXmlSchema** verwendet einen Parameter, der das Ziel des resultierenden XML\-Schemas angibt.  In den folgenden Codebeispielen wird veranschaulicht, wie das XML\-Schema eines **DataSet** in eine Datei geschrieben wird. Hierzu wird eine Zeichenfolge übergeben, die einen Dateinamen und ein <xref:System.IO.StreamWriter>\-Objekt enthält.  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 Verwenden Sie die **GetXmlSchema**\-Methode, um das Schema eines **DataSet**abzurufen und es als XML\-Schemazeichenfolge zu schreiben. Dies wird im folgenden Beispiel veranschaulicht.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## Siehe auch  
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Schreiben von 'DataSet'\-Inhalt als XML\-Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)   
 [Typisierte 'DataSets'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)