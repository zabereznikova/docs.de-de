---
title: Schreiben von DataSet-Inhalten als XML-Daten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: b8a8656bb68832a09490e656903fd68788bdeb1d
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203100"
---
# <a name="writing-dataset-contents-as-xml-data"></a>Schreiben von DataSet-Inhalten als XML-Daten
Sie können in ADO.NET die XML-Darstellung eines <xref:System.Data.DataSet> mit oder ohne dessen Schema schreiben. Wenn das XML-Dokument Inlineschemainformationen enthält, werden diese mit XSD (XML Schema Definition Language) geschrieben. Das Schema enthält die Tabellendefinitionen des <xref:System.Data.DataSet> sowie die Beziehungs- und Einschränkungsdefinitionen.  
  
 Beim Schreiben eines <xref:System.Data.DataSet> als XML-Daten werden die aktuellen Versionen der Zeilen im <xref:System.Data.DataSet> geschrieben. Das <xref:System.Data.DataSet> kann jedoch auch als DiffGram geschrieben werden, sodass die aktuellen und die ursprünglichen Werte der Zeilen aufgenommen werden.  
  
 Die XML-Darstellung <xref:System.Data.DataSet> der kann in eine Datei, einen Stream, einen **XmlWriter**oder eine Zeichenfolge geschrieben werden. Durch diese Auswahl sind Sie äußerst flexibel bei der Übertragung der XML-Darstellung des <xref:System.Data.DataSet>. Um die XML-Darstellung des <xref:System.Data.DataSet> als Zeichenfolge zu erhalten, verwenden Sie die **GetXml** -Methode, wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXml** gibt die XML-Darstellung <xref:System.Data.DataSet> der ohne Schema Informationen zurück. Verwenden Sie **GetXmlSchema**, <xref:System.Data.DataSet> um die Schema Informationen aus dem (als XML-Schema) in eine Zeichenfolge zu schreiben.  
  
 Um einen in <xref:System.Data.DataSet> eine Datei, einen Stream oder einen **XmlWriter**zu schreiben, verwenden Sie die Methode " **Write texml** ". Der erste Parameter, den Sie an " **Write texml** " übergeben, ist das Ziel der XML-Ausgabe. Übergeben Sie z. b. eine Zeichenfolge mit einem Dateinamen, einem **System. IO. TextWriter** -Objekt usw. Sie können einen optionalen zweiten Parameter eines **xmlschreitemode** -Parameters übergeben, um anzugeben, wie die XML-Ausgabe geschrieben werden soll.  
  
 In der folgenden Tabelle sind die Optionen für **xmlschreitemode**aufgeführt.  
  
|"XmlWriteMode"-Option|Beschreibung|  
|-------------------------|-----------------|  
|**IgnoreSchema**|Schreibt den aktuellen Inhalt des <xref:System.Data.DataSet> ohne XML-Schema als XML-Daten. Dies ist die Standardeinstellung.|  
|**WriteSchema**|Schreibt den aktuellen Inhalt des <xref:System.Data.DataSet> als XML-Daten mit der relationalen Struktur als XML-Inlineschema.|  
|**DiffGram**|Schreibt das gesamte <xref:System.Data.DataSet> als DiffGram, einschließlich der ursprünglichen und aktuellen Werte. Weitere Informationen finden Sie unter [DiffGrams](diffgrams.md).|  
  
 Beim Schreiben einer XML-Darstellung eines <xref:System.Data.DataSet> -Objekts, das **DataRelations** -Objekte enthält, möchten Sie wahrscheinlich, dass der resultierende XML-Code die untergeordneten Zeilen jeder Beziehung innerhalb der zugehörigen übergeordneten Elemente geschachtelt hat. Um dies zu erreichen, legen Sie die-Eigenschaft der Eigenschaft " **DataRelations** " auf " **true** " fest, wenn Sie die <xref:System.Data.DataSet> **DataRelations** -Eigenschaft hinzufügen. Weitere Informationen finden Sie unter Schachteln von [DataRelations](nesting-datarelations.md)-Elementen.  
  
 Im Folgenden sind zwei Beispiele aufgeführt, die zeigen, wie die XML-Darstellung eines <xref:System.Data.DataSet> in eine Datei geschrieben wird. Im ersten Beispiel wird der Dateiname für den resultierenden XML-Code als Zeichenfolge an " **Write texml**" weitergeleitet. Im zweiten Beispiel wird ein **System. IO. StreamWriter** -Objekt weitergeleitet.  
  
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
 Mithilfe der **ColumnMapping** -Eigenschaft des **datacolenn** -Objekts können Sie angeben, wie eine Spalte einer Tabelle in XML dargestellt wird. In der folgenden Tabelle werden die verschiedenen **MappingType** -Werte für die **ColumnMapping** -Eigenschaft einer Tabellenspalte und die resultierende XML-Datei angezeigt.  
  
|"MappingType"-Wert|Beschreibung|  
|-----------------------|-----------------|  
|**Element**|Dies ist die Standardeinstellung. Die Spalte wird als XML-Element geschrieben, wobei ColumnName der Name des Elements ist und der Inhalt der Spalte als Text des Elements geschrieben wird. Beispiel:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**Attribut**|Die Spalte wird als XML-Attribut des XML-Elements für die aktuelle Zeile geschrieben, wobei ColumnName der Name des Attributs ist und der Inhalt der Spalte als Wert des Attributs geschrieben wird. Beispiel:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|Der Inhalt der Spalte wird für die aktuelle Zeile als Text in das XML-Element geschrieben. Beispiel:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> Beachten Sie, dass " **simpleContent** " nicht für eine Spalte einer Tabelle festgelegt werden kann, die über **Element** Spalten oder Beziehungen verfügt.|  
|**Verbirgt**|Die Spalte wird in der XML-Ausgabe nicht geschrieben.|  
  
## <a name="see-also"></a>Siehe auch

- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- [DiffGrams](diffgrams.md)
- [Schachteln von DataRelations](nesting-datarelations.md)
- [Schreiben von DataSet-Schemainformationen als XSD](writing-dataset-schema-information-as-xsd.md)
- [DataSets, DataTables und DataViews](index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
