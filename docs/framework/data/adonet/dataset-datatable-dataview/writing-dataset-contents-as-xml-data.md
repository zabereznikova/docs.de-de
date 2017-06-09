---
title: "Schreiben von DataSet-Inhalten als XML-Daten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Schreiben von DataSet-Inhalten als XML-Daten
In ADO.NET können Sie schreiben eine XML-Darstellung einer <xref:System.Data.DataSet>mit oder ohne dessen Schema. Wenn das XML-Dokument Inlineschemainformationen enthält, werden diese mit XSD (XML Schema Definition Language) geschrieben. Das Schema enthält die Definitionen für die <xref:System.Data.DataSet> sowie der Beziehung und Einschränkungsdefinitionen.  
  
 Wenn ein <xref:System.Data.DataSet> wird geschrieben, als XML-Daten, die Zeilen in der <xref:System.Data.DataSet> werden die aktuellen Versionen geschrieben. Allerdings die <xref:System.Data.DataSet> kann auch als DiffGram geschrieben werden, sodass die aktuellen und ursprünglichen Werte der Zeilen aufgenommen werden.  
  
 Die XML-Darstellung der <xref:System.Data.DataSet> in eine Datei, einen Stream geschrieben werden kann ein **XmlWriter**, oder eine Zeichenfolge. Diese Auswahl sind Sie äußerst flexibel bei der Übertragung der XML-Darstellung der <xref:System.Data.DataSet>. Zum Abrufen der XML-Darstellung der <xref:System.Data.DataSet> als Zeichenfolge verwenden die **GetXml** -Methode wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXml** gibt die XML-Darstellung der <xref:System.Data.DataSet> ohne Schemainformationen. Schreiben Sie die Schemainformationen aus der <xref:System.Data.DataSet> (als XML-Schema) verwenden, um eine Zeichenfolge **GetXmlSchema**.  
  
 Schreiben einer <xref:System.Data.DataSet> in eine Datei, Stream oder **XmlWriter**, verwenden die **WriteXml** Methode. Der erste Parameter übergeben Sie an **WriteXml** ist das Ziel der XML-Ausgabe. Übergeben Sie eine Zeichenfolge mit einem Dateinamen, z. B. ein **System.IO.TextWriter** Objekt und So weiter. Sie können einen optionalen zweiten Parameter des übergeben ein **XmlWriteMode** , wie die XML-Ausgabe geschrieben werden.  
  
 Die folgende Tabelle zeigt die Optionen für **XmlWriteMode**.  
  
|"XmlWriteMode"-Option|Beschreibung|  
|-------------------------|-----------------|  
|**IgnoreSchema**|Schreibt den aktuellen Inhalt der <xref:System.Data.DataSet> als XML-Daten ohne ein XML-Schema. Dies ist die Standardeinstellung.|  
|**WriteSchema fest**|Schreibt den aktuellen Inhalt der <xref:System.Data.DataSet> als XML-Daten mit der relationalen Struktur als XML-Inlineschema.|  
|**DiffGram-Objekt**|Schreibt das gesamte <xref:System.Data.DataSet> als DiffGram, einschließlich der ursprünglichen und aktuellen Werte. Weitere Informationen finden Sie unter [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
  
 Beim Schreiben einer XML-Darstellung einer <xref:System.Data.DataSet> , enthält **DataRelation** Objekte, die Sie wahrscheinlich die resultierenden XML-Daten an die untergeordneten Zeilen jede Beziehung, die innerhalb ihrer zugehörigen übergeordneten Elemente geschachtelt sind. Um dies zu erreichen, legen die **geschachtelte** Eigenschaft der **DataRelation** zu **true** beim Hinzufügen der **DataRelation** auf der <xref:System.Data.DataSet>. Weitere Informationen finden Sie unter [schachteln DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
 Es folgen zwei Beispiele für das Schreiben die XML-Darstellung einer <xref:System.Data.DataSet> in eine Datei. Das erste Beispiel übergibt den Dateinamen für das resultierende XML als Zeichenfolge an **WriteXml**. Das zweite Beispiel übergibt eine **System.IO.StreamWriter** Objekt.  
  
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
 Können Sie angeben, wie eine Spalte einer Tabelle in XML dargestellt wird mithilfe der **ColumnMapping** Eigenschaft der **DataColumn** Objekt. In der folgenden Tabelle werden die verschiedenen **MappingType** Werte für die **ColumnMapping** -Eigenschaft einer Tabellenspalte und das resultierende XML.  
  
|"MappingType"-Wert|Beschreibung|  
|-----------------------|-----------------|  
|**Element**|Dies ist die Standardeinstellung. Die Spalte wird als XML-Element geschrieben, wobei ColumnName der Name des Elements ist und der Inhalt der Spalte als Text des Elements geschrieben wird. Zum Beispiel:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**Attribut**|Die Spalte wird als XML-Attribut des XML-Elements für die aktuelle Zeile geschrieben, wobei ColumnName der Name des Attributs ist und der Inhalt der Spalte als Wert des Attributs geschrieben wird. Beispiel:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|Der Inhalt der Spalte wird für die aktuelle Zeile als Text in das XML-Element geschrieben. Beispiel:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> Beachten Sie, dass **SimpleContent** kann nicht festgelegt werden, für eine Spalte einer Tabelle, die **Element** Spalten oder geschachtelte Beziehungen besitzt.|  
|**Ausgeblendet**|Die Spalte wird in der XML-Ausgabe nicht geschrieben.|  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)   
 [Verschachteln von "DataRelations"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)   
 [Schreiben von DataSet-Schemainformationen als XSD](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)   
 [DataSets, "DataTables" und "DataViews"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET verwaltete Anbieter und DataSet-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)