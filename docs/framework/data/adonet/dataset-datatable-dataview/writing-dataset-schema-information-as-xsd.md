---
title: Schreiben von DataSet-Schemainformationen als XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 7634dfc8415b6f73fc60f2ebe59c92a0c31f83a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173730"
---
# <a name="writing-dataset-schema-information-as-xsd"></a>Schreiben von DataSet-Schemainformationen als XSD

Sie können das Schema eines <xref:System.Data.DataSet> als XSD-Schema (XML Schema Definition Language) schreiben, sodass Sie es mit oder ohne zugehörige Daten in ein XML-Dokument übertragen können. Das XML-Schema kann in eine Datei, einen Stream, einen <xref:System.Xml.XmlWriter> oder eine Zeichenfolge geschrieben werden. es ist nützlich, um ein stark typisiertes **DataSet**zu erzeugen. Weitere Informationen zu stark typisierten **DataSet** -Objekten finden Sie unter [typisierte Datasets](typed-datasets.md).  
  
 Mithilfe der **ColumnMapping** -Eigenschaft des-Objekts können Sie angeben, wie eine Spalte einer Tabelle im XML-Schema dargestellt wird <xref:System.Data.DataColumn> . Weitere Informationen finden Sie unter "Mapping von Spalten zu XML-Elementen,-Attributen und-Text" unter [Schreiben von DataSet-Inhalten als XML-Daten](writing-dataset-contents-as-xml-data.md).  
  
 Um das Schema eines **DataSets** als XML-Schema in eine Datei, einen Stream oder einen **XmlWriter**zu schreiben, verwenden Sie die Schreib **texmlschema** -Methode des **DataSets**. " **Write texmlschema** " nimmt einen Parameter an, der das Ziel des resultierenden XML-Schemas angibt. Die folgenden Codebeispiele veranschaulichen, wie das XML-Schema eines **DataSets** in eine Datei geschrieben wird, indem eine Zeichenfolge mit einem Dateinamen und einem-Objekt übergeben wird <xref:System.IO.StreamWriter> .  
  
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
  
 Wenn Sie das Schema eines **DataSets** abrufen und als XML-Schema Zeichenfolge schreiben möchten, verwenden Sie die **GetXmlSchema** -Methode, wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a>Siehe auch

- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- [Schreiben von DataSet-Inhalten als XML-Daten](writing-dataset-contents-as-xml-data.md)
- [Typisierte "DataSets"](typed-datasets.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
