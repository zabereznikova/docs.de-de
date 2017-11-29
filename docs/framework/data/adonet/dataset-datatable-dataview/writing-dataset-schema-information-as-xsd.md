---
title: Schreiben von DataSet-Schemainformationen als XSD
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: dde8a16ee0fbd86dacf6125c9a02209a794a5b74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="writing-dataset-schema-information-as-xsd"></a>Schreiben von DataSet-Schemainformationen als XSD
Sie können das Schema eines <xref:System.Data.DataSet> als XSD-Schema (XML Schema Definition Language) schreiben, sodass Sie es mit oder ohne zugehörige Daten in ein XML-Dokument übertragen können. XML-Schema in eine Datei, einen Stream geschrieben werden kann ein <xref:System.Xml.XmlWriter>, oder eine Zeichenfolge eignet sich zum Generieren einer stark typisierten **DataSet**. Weitere Informationen zu stark typisierten **DataSet** anzuzeigen, [typisierter DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 Können Sie angeben, wie eine Spalte einer Tabelle im XML-Schema dargestellt wird mithilfe der **ColumnMapping** Eigenschaft von der <xref:System.Data.DataColumn> Objekt. Weitere Informationen finden Sie unter "Zuordnen von Spalten zu XML-Elemente, Attribute und Text" in [Schreiben von DataSet-Inhalten als XML-Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Schreiben Sie das Schema der eine **DataSet** als XML-Schema in eine Datei Stream oder **"XmlWriter"**, verwenden die **WriteXmlSchema** Methode der **DataSet**. **WriteXmlSchema** nimmt einen Parameter an, die das Ziel des resultierenden XML-Schemas angibt. Die folgenden Codebeispiele veranschaulichen, wie das XML-Schema Schreiben einer **DataSet** in eine Datei durch die Übergabe einer Zeichenfolge mit einem Dateinamen und ein <xref:System.IO.StreamWriter> Objekt.  
  
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
  
 Das Schema der abzurufenden eine **DataSet** und als XML-Schemazeichenfolge zu schreiben, verwenden Sie die **GetXmlSchema** Methode, wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Schreiben von DataSet-Inhalten als XML-Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [Typed DataSets (Typisierte DataSets)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
