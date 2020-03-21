---
title: Laden eines "DataSets" aus XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: c21ed3bb31add285d64272040680433fff4e16fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151064"
---
# <a name="loading-a-dataset-from-xml"></a>Laden eines "DataSets" aus XML
Der Inhalt eines ADO.NET-<xref:System.Data.DataSet> kann aus einem XML-Stream oder einem XML-Dokument erstellt werden. Außerdem können Sie mit .NET Framework größtenteils festlegen, welche Informationen aus der XML-Quelle geladen werden sollen und wie das Schema oder die relationale Struktur des <xref:System.Data.DataSet> erstellt werden soll.  
  
 Um eine <xref:System.Data.DataSet> mit Daten aus XML zu füllen, verwenden Sie die **ReadXml-Methode** des <xref:System.Data.DataSet> Objekts. Die **ReadXml-Methode** liest aus einer Datei, einem Stream oder einem **XmlReader**und nimmt als Argumente die Quelle des XML-Codes plus ein optionales **XmlReadMode-Argument** an. Weitere Informationen zum **XmlReader**finden Sie unter Lesen von [XML-Daten mit XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)). Die **ReadXml-Methode** liest den Inhalt des XML-Streams oder Dokuments und lädt sie <xref:System.Data.DataSet> mit Daten. Außerdem wird das relationale Schema <xref:System.Data.DataSet> des abhängig vom angegebenen **XmlReadMode** und davon erstellt, ob bereits ein relationales Schema vorhanden ist.  
  
 In der folgenden Tabelle werden die Optionen für das **Argument XmlReadMode** beschrieben.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Automatisch**|Dies ist die Standardoption. Prüft die XML-Daten und wählt die am besten geeignete Option in der folgenden Reihenfolge aus:<br /><br /> - Wenn es sich bei xml um ein DiffGram handelt, wird **DiffGram** verwendet.<br />- Wenn <xref:System.Data.DataSet> der ein Schema oder der XML-Code ein Inlineschema enthält, wird **ReadSchema** verwendet.<br />- Wenn <xref:System.Data.DataSet> der kein Schema enthält und der XML-Code kein Inlineschema enthält, wird **InferSchema** verwendet.<br /><br /> Wenn Sie das Format des gelesenen XML kennen, wird für die beste Leistung empfohlen, einen expliziten **XmlReadMode**festzulegen, anstatt den **Auto-Standard** zu akzeptieren.|  
|**ReadSchema**|Liest beliebige Inlineschemata und lädt Daten und Schemata.<br /><br /> Wenn das <xref:System.Data.DataSet> bereits ein Schema enthält, werden neue Tabellen aus dem Inlineschema zum vorhandenen Schema im <xref:System.Data.DataSet> hinzugefügt. Wenn bereits Tabellen im Inlineschema des <xref:System.Data.DataSet> vorhanden sind, wird eine Ausnahme ausgelöst. Sie können das Schema einer vorhandenen Tabelle nicht mit **XmlReadMode.ReadSchema**ändern.<br /><br /> Wenn das <xref:System.Data.DataSet> kein Schema enthält und kein Inlineschema vorhanden ist, werden keine Daten gelesen.<br /><br /> Ein Inlineschema kann mit dem XSD-Schema (XML Schema Definition Language) definiert werden. Weitere Informationen zum Schreiben von Inlineschemas als XML-Schema finden Sie unter [Ableiten der relationalen Struktur von DataSet aus XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Ignoriert alle Inlineschemata und lädt die Daten in das vorhandene <xref:System.Data.DataSet>-Schema. Daten, die nicht mit dem vorhandenen Schema übereinstimmen, werden gelöscht. Wenn kein Schema im <xref:System.Data.DataSet> vorhanden ist, werden keine Daten geladen.<br /><br /> Wenn es sich bei den Daten um ein DiffGram handelt, verfügt **IgnoreSchema** über die gleiche Funktionalität wie **DiffGram** *.*|  
|**InferSchema**|Ignoriert alle Inlineschemata, leitet das Schema aus der Struktur der XML-Daten ab und lädt anschließend die Daten.<br /><br /> Wenn das <xref:System.Data.DataSet> bereits ein Schema enthält, wird das aktuelle Schema durch Hinzufügen von Spalten zu den vorhandenen Tabellen erweitert. Wenn keine Tabellen vorhanden sind, werden keine zusätzlichen Tabellen hinzugefügt. Eine Ausnahme wird ausgelöst, wenn bereits eine hergeleitete Tabelle mit einem anderen Namespace vorhanden ist oder wenn hergeleitete Spalten mit vorhandenen Spalten kollidieren.<br /><br /> Weitere Informationen dazu, wie **ReadXmlSchema** ein Schema aus einem XML-Dokument ableitet, finden Sie unter [Ableiten der relationalen Struktur von DataSet aus XML](inferring-dataset-relational-structure-from-xml.md).|  
|**Diffgram**|	Liest ein DiffGram und fügt die Daten dem aktuellen Schema hinzu. **DiffGram** führt neue Zeilen mit vorhandenen Zeilen zusammen, in denen die eindeutigen Bezeichnerwerte übereinstimmen. Informationen hierzu finden Sie unter "Zusammenführen von Daten aus XML-Dokumenten" am Ende dieses Themas. Weitere Informationen zu DiffGrams finden Sie unter [DiffGrams](diffgrams.md).|  
|**Fragment**|Setzt den Lesevorgang für mehrere XML-Fragmente fort, bis das Ende des Streams erreicht ist. Fragmente, die mit dem <xref:System.Data.DataSet>-Schema übereinstimmen, werden an die entsprechenden Tabellen angehängt. Fragmente, die nicht mit dem <xref:System.Data.DataSet>-Schema übereinstimmen, werden gelöscht.|  
  
> [!NOTE]
> Wenn Sie einen **XmlReader** an **ReadXml** übergeben, der Teil des Weges in ein XML-Dokument verschoben wird, liest **ReadXml** an den nächsten Elementknoten und behandelt dies als Stammelement, das nur bis zum Ende des Elementknotens gelesen wird. Dies gilt nicht, wenn Sie **XmlReadMode.Fragment**angeben.  
  
## <a name="dtd-entities"></a>DTD-Entitäten  
 Wenn Ihr XML Entitäten enthält, die in einem DTD-Schema (Document Type <xref:System.Data.DataSet> Definition) definiert sind, wird eine Ausnahme ausgelöst, wenn Sie versuchen, einen Dateinamen, einen Stream oder eine nicht validierende **XmlReader** an **ReadXml**zu laden. Stattdessen müssen Sie einen **XmlValidatingReader**erstellen, wobei **EntityHandling** auf **EntityHandling.ExpandEntities**festgelegt ist, und Ihren **XmlValidatingReader** an **ReadXml**übergeben. Der **XmlValidatingReader** erweitert die Entitäten, <xref:System.Data.DataSet>bevor sie von der gelesen werden.  
  
 In den folgenden Codebeispielen wird dargestellt, wie ein <xref:System.Data.DataSet> aus einem XML-Stream geladen wird. Das erste Beispiel zeigt einen Dateinamen, der an die **ReadXml-Methode** übergeben wird. Im zweiten Beispiel wird eine Zeichenfolge mit XML-Daten mithilfe eines <xref:System.IO.StringReader> geladen.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema);  
```  
  
```vb  
Dim dataSet As DataSet = New DataSet  
Dim dataTable As DataTable = New DataTable("table1")  
dataTable.Columns.Add("col1", Type.GetType("System.String"))  
dataSet.Tables.Add(dataTable)  
  
Dim xmlData As String = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>"  
  
Dim xmlSR As System.IO.StringReader = New System.IO.StringReader(xmlData)  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
DataTable dataTable = new DataTable("table1");  
dataTable.Columns.Add("col1", typeof(string));  
dataSet.Tables.Add(dataTable);  
  
string xmlData = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>";  
  
System.IO.StringReader xmlSR = new System.IO.StringReader(xmlData);  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema);  
```  
  
> [!NOTE]
> Wenn Sie **ReadXml** aufrufen, um eine sehr große Datei zu laden, kann es zu einer langsamen Leistung treten. Um die beste Leistung für **ReadXml**zu <xref:System.Data.DataTable.BeginLoadData%2A> gewährleisten, rufen Sie <xref:System.Data.DataSet>die Methode für jede Tabelle im auf, und rufen Sie dann **ReadXml**auf. Rufen Sie zum Schluss <xref:System.Data.DataTable.EndLoadData%2A> für jede Tabelle im <xref:System.Data.DataSet> auf. Dies wird im folgenden Beispiel dargestellt.  
  
```vb  
Dim dataTable As DataTable  
  
For Each dataTable In dataSet.Tables  
   dataTable.BeginLoadData()  
Next  
  
dataSet.ReadXml("file.xml")  
  
For Each dataTable in dataSet.Tables  
   dataTable.EndLoadData()  
Next  
```  
  
```csharp  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.BeginLoadData();  
  
dataSet.ReadXml("file.xml");
  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.EndLoadData();  
```  
  
> [!NOTE]
> Wenn das XSD-Schema <xref:System.Data.DataSet> für Sie einen **targetNamespace**enthält, werden Daten möglicherweise nicht gelesen, und beim Aufrufen von ReadXml zum Laden von **ReadXml** zum Laden von mit XML, das <xref:System.Data.DataSet> Elemente ohne qualifizierenden Namespace enthält, kann es zu Ausnahmen treten. Um in diesem Fall nicht qualifizierte Elemente zu lesen, legen Sie **elementFormDefault** in Ihrem XSD-Schema gleich "qualifiziert" fest. Beispiel:  
  
```xml  
<xsd:schema id="customDataSet"
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"
  xmlns="http://www.tempuri.org/customDataSet.xsd"
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a>	Zusammenführen von Daten aus XML-Dokumenten  
 Wenn das <xref:System.Data.DataSet> bereits Daten enthält, werden die neuen Daten aus der XML-Quelle den im <xref:System.Data.DataSet> bereits vorhandenen Daten hinzugefügt. **ReadXml** führt aus dem XML-Code nicht mit <xref:System.Data.DataSet> den Zeileninformationen mit übereinstimmenden Primärschlüsseln zusammen. Um vorhandene Zeileninformationen mit neuen Informationen aus XML zu überschreiben, <xref:System.Data.DataSet.Merge%2A> verwenden <xref:System.Data.DataSet> Sie <xref:System.Data.DataSet> **ReadXml,** um eine neue <xref:System.Data.DataSet>zu erstellen, und dann die neue in die vorhandene . Beachten Sie, dass beim Laden eines DiffGram mit **ReadXML** mit einem **XmlReadMode** von **DiffGram** Zeilen mit demselben eindeutigen Bezeichner zusammengeführt werden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [Verwenden von XML in einem "DataSet"](using-xml-in-a-dataset.md)
- [DiffGrams](diffgrams.md)
- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](inferring-dataset-relational-structure-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](loading-dataset-schema-information-from-xml.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
