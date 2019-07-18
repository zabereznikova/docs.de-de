---
title: Schreiben von DataSet-Inhalten als XML-Daten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: dae044a9d7802e858f1f24dd4aa0f1de8f6cba7a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607013"
---
# <a name="writing-dataset-contents-as-xml-data"></a>Schreiben von DataSet-Inhalten als XML-Daten
Sie können in ADO.NET die XML-Darstellung eines <xref:System.Data.DataSet> mit oder ohne dessen Schema schreiben. Wenn das XML-Dokument Inlineschemainformationen enthält, werden diese mit XSD (XML Schema Definition Language) geschrieben. Das Schema enthält die Tabellendefinitionen des <xref:System.Data.DataSet> sowie die Beziehungs- und Einschränkungsdefinitionen.  
  
 Beim Schreiben eines <xref:System.Data.DataSet> als XML-Daten werden die aktuellen Versionen der Zeilen im <xref:System.Data.DataSet> geschrieben. Das <xref:System.Data.DataSet> kann jedoch auch als DiffGram geschrieben werden, sodass die aktuellen und die ursprünglichen Werte der Zeilen aufgenommen werden.  
  
 Die XML-Darstellung der <xref:System.Data.DataSet> geschrieben werden kann, in eine Datei, einen Stream, eine **"XmlWriter"**, oder eine Zeichenfolge. Durch diese Auswahl sind Sie äußerst flexibel bei der Übertragung der XML-Darstellung des <xref:System.Data.DataSet>. Zum Abrufen der XML-Darstellung der <xref:System.Data.DataSet> verwenden, als eine Zeichenfolge, die **GetXml** -Methode wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXml** gibt die XML-Darstellung der <xref:System.Data.DataSet> ohne Schemainformationen. Schreiben Sie die Schemainformationen aus der <xref:System.Data.DataSet> (als XML-Schema) verwenden, um eine Zeichenfolge, **GetXmlSchema**.  
  
 Schreiben einer <xref:System.Data.DataSet> in eine Datei, Stream oder **"XmlWriter"**, verwenden Sie die **WriteXml** Methode. Der erste Parameter, die Sie, um übergeben **WriteXml** ist das Ziel der XML-Ausgabe. Übergeben Sie eine Zeichenfolge, enthält einen Dateinamen ein, z. B. eine **System.IO.TextWriter** -Objekt, und So weiter. Sie können einen optionalen zweiten Parameter des übergeben eine **XmlWriteMode** um anzugeben, wie die XML-Ausgabe geschrieben werden.  
  
 Die folgende Tabelle zeigt die Optionen für **XmlWriteMode**.  
  
|"XmlWriteMode"-Option|Beschreibung|  
|-------------------------|-----------------|  
|**IgnoreSchema**|Schreibt den aktuellen Inhalt des <xref:System.Data.DataSet> ohne XML-Schema als XML-Daten. Dies ist die Standardeinstellung.|  
|**WriteSchema**|Schreibt den aktuellen Inhalt des <xref:System.Data.DataSet> als XML-Daten mit der relationalen Struktur als XML-Inlineschema.|  
|**DiffGram**|Schreibt das gesamte <xref:System.Data.DataSet> als DiffGram, einschließlich der ursprünglichen und aktuellen Werte. Weitere Informationen finden Sie unter [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
  
 Beim Schreiben einer XML-Darstellung einer <xref:System.Data.DataSet> , enthält **DataRelation** Objekten, die Sie in den meisten Fällen der resultierenden XML-Code die untergeordneten Zeilen jede Beziehung, die in den zugehörigen übergeordneten Elementen geschachtelt haben sollten. Zu diesem Zweck legen Sie die **geschachtelte** Eigenschaft der **DataRelation** zu **"true"** beim Hinzufügen der **DataRelation** auf die <xref:System.Data.DataSet>. Weitere Informationen finden Sie unter [Schachteln von DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
 Im Folgenden sind zwei Beispiele aufgeführt, die zeigen, wie die XML-Darstellung eines <xref:System.Data.DataSet> in eine Datei geschrieben wird. Das erste Beispiel übergibt den Dateinamen für das XML-Ergebnis als Zeichenfolge an **WriteXml**. Das zweite Beispiel übergibt eine **System.IO.StreamWriter** Objekt.  
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a>Zuordnen von Spalten zu XML-Elementen, -Attributen und -Text  
 Können Sie angeben, wie eine Spalte einer Tabelle im XML-Format dargestellt wird mithilfe der **ColumnMapping** Eigenschaft der **DataColumn** Objekt. In der folgende Tabelle werden die verschiedenen **MappingType** Werte für die **ColumnMapping** Eigenschaft einer Spalte der Tabelle und die resultierenden XML-Code.  
  
|"MappingType"-Wert|Beschreibung|  
|-----------------------|-----------------|  
|**Element**|Dies ist die Standardeinstellung. Die Spalte wird als XML-Element geschrieben, wobei ColumnName der Name des Elements ist und der Inhalt der Spalte als Text des Elements geschrieben wird. Zum Beispiel:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**Attribut**|Die Spalte wird als XML-Attribut des XML-Elements für die aktuelle Zeile geschrieben, wobei ColumnName der Name des Attributs ist und der Inhalt der Spalte als Wert des Attributs geschrieben wird. Zum Beispiel:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|Der Inhalt der Spalte wird für die aktuelle Zeile als Text in das XML-Element geschrieben. Zum Beispiel:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> Beachten Sie, dass **SimpleContent** kann nicht festgelegt werden, für eine Spalte einer Tabelle, die **Element** Spalten oder geschachtelte Beziehungen besitzt.|  
|**Hidden**|Die Spalte wird in der XML-Ausgabe nicht geschrieben.|  
  
## <a name="see-also"></a>Siehe auch

- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)
- [Schachteln von DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)
- [Schreiben von DataSet-Schemainformationen als XSD](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)
- [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
