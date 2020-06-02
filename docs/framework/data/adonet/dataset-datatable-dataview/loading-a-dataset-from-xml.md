---
title: Laden eines "DataSets" aus XML
description: Erfahren Sie, wie Sie Inhalte zu einem ADO.NET-DataSet aus XML hinzufügen. Der .NET Framework bietet Flexibilität für das, was zu laden ist, und die Struktur des Datasets.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 8c81e6e29678fe2e30af7c15d8d6e90f23dd0762
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286882"
---
# <a name="loading-a-dataset-from-xml"></a>Laden eines "DataSets" aus XML
Der Inhalt eines ADO.NET-<xref:System.Data.DataSet> kann aus einem XML-Stream oder einem XML-Dokument erstellt werden. Außerdem können Sie mit .NET Framework größtenteils festlegen, welche Informationen aus der XML-Quelle geladen werden sollen und wie das Schema oder die relationale Struktur des <xref:System.Data.DataSet> erstellt werden soll.  
  
 <xref:System.Data.DataSet>Verwenden Sie die Methode "read **XML** " des-Objekts, um eine mit Daten aus XML auszufüllen <xref:System.Data.DataSet> . Die Read **XML** -Methode liest aus einer Datei, einem Stream oder einem **XmlReader**-Objekt und übernimmt die Quelle des XML-Codes sowie ein optionales **xmllesemode** -Argument als Argumente. Weitere Informationen zum **XmlReader**finden Sie unter [Lesen von XML-Daten mit XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)). Die Read **XML** -Methode liest den Inhalt des XML-Streams oder-Dokuments und lädt den <xref:System.Data.DataSet> mit Daten. Außerdem wird das relationale Schema von erstellt, <xref:System.Data.DataSet> abhängig vom angegebenen **xmllesemode** und davon, ob ein relationales Schema bereits vorhanden ist.  
  
 In der folgenden Tabelle werden die Optionen für das **xmllesemode** -Argument beschrieben.  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**Auto**|Dies ist die Standardeinstellung. Prüft die XML-Daten und wählt die am besten geeignete Option in der folgenden Reihenfolge aus:<br /><br /> -Wenn das XML ein DiffGram ist, wird **DiffGram** verwendet.<br />Wenn das <xref:System.Data.DataSet> ein Schema enthält oder das XML ein Inline Schema enthält, wird "read **Schema** " verwendet.<br />Wenn das <xref:System.Data.DataSet> kein Schema enthält und das XML kein Inline Schema enthält, wird das **InferSchema** verwendet.<br /><br /> Wenn Sie das Format des gelesenen XML-Codes kennen, empfiehlt es sich, einen expliziten **xmllesemode**festzulegen, anstatt den **automatischen** Standardwert zu akzeptieren.|  
|**ReadSchema**|Liest beliebige Inlineschemata und lädt Daten und Schemata.<br /><br /> Wenn das <xref:System.Data.DataSet> bereits ein Schema enthält, werden neue Tabellen aus dem Inlineschema zum vorhandenen Schema im <xref:System.Data.DataSet> hinzugefügt. Wenn bereits Tabellen im Inlineschema des <xref:System.Data.DataSet> vorhanden sind, wird eine Ausnahme ausgelöst. Das Schema einer vorhandenen Tabelle kann nicht mithilfe von **xmllesemode. Read Schema**geändert werden.<br /><br /> Wenn das <xref:System.Data.DataSet> kein Schema enthält und kein Inlineschema vorhanden ist, werden keine Daten gelesen.<br /><br /> Ein Inlineschema kann mit dem XSD-Schema (XML Schema Definition Language) definiert werden. Ausführliche Informationen zum Schreiben eines Inline Schemas als XML-Schema finden Sie unter [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Ignoriert alle Inlineschemata und lädt die Daten in das vorhandene <xref:System.Data.DataSet>-Schema. Daten, die nicht mit dem vorhandenen Schema übereinstimmen, werden gelöscht. Wenn kein Schema im <xref:System.Data.DataSet> vorhanden ist, werden keine Daten geladen.<br /><br /> Wenn es sich bei den Daten um ein DiffGram-DataSet handelt, hat **ignoreschema** die gleiche Funktionalität wie **DiffGram** *.*|  
|**InferSchema**|Ignoriert alle Inlineschemata, leitet das Schema aus der Struktur der XML-Daten ab und lädt anschließend die Daten.<br /><br /> Wenn das <xref:System.Data.DataSet> bereits ein Schema enthält, wird das aktuelle Schema durch Hinzufügen von Spalten zu den vorhandenen Tabellen erweitert. Wenn keine Tabellen vorhanden sind, werden keine zusätzlichen Tabellen hinzugefügt. Eine Ausnahme wird ausgelöst, wenn bereits eine hergeleitete Tabelle mit einem anderen Namespace vorhanden ist oder wenn hergeleitete Spalten mit vorhandenen Spalten kollidieren.<br /><br /> Ausführliche Informationen dazu, wie " **infoxmlschema** " ein Schema aus einem XML-Dokument ableitet, finden Sie unter [ableiten der relationalen DataSet-Struktur aus XML](inferring-dataset-relational-structure-from-xml.md).|  
|**DiffGram**|	Liest ein DiffGram und fügt die Daten dem aktuellen Schema hinzu. **DiffGram** führt neue Zeilen mit vorhandenen Zeilen zusammen, bei denen die eindeutigen Bezeichnerwerte entsprechen. Informationen hierzu finden Sie unter "Zusammenführen von Daten aus XML-Dokumenten" am Ende dieses Themas. Weitere Informationen zu DiffGrams finden Sie unter [DiffGrams](diffgrams.md).|  
|**Fragment**|Setzt den Lesevorgang für mehrere XML-Fragmente fort, bis das Ende des Streams erreicht ist. Fragmente, die mit dem <xref:System.Data.DataSet>-Schema übereinstimmen, werden an die entsprechenden Tabellen angehängt. Fragmente, die nicht mit dem <xref:System.Data.DataSet>-Schema übereinstimmen, werden gelöscht.|  
  
> [!NOTE]
> Wenn Sie einen **XmlReader** an **ReadXml** übergeben, der Teil der Art und Weise in ein XML-Dokument positioniert ist, liest **ReadXml** den nächsten Elementknoten und behandelt dies als Stamm Element, wobei nur bis zum Ende des Element Knotens gelesen wird. Dies trifft nicht zu, wenn Sie **xmllesemode. Fragment**angeben.  
  
## <a name="dtd-entities"></a>DTD-Entitäten  
 Wenn Ihr XML Entitäten enthält, die in einem DTD-Schema (Document Type Definition) definiert sind, wird eine Ausnahme ausgelöst, wenn Sie versuchen, ein zu laden, <xref:System.Data.DataSet> indem Sie einen Dateinamen, einen Stream oder einen nicht validierenden **XmlReader** an die Datei " **infoxml**" übergeben. Stattdessen müssen Sie einen **XmlValidatingReader**erstellen, bei dem **EntityHandling** auf **EntityHandling. ExpandEntities**festgelegt ist, und **XmlValidatingReader** an die Datei "read **XML**" übergeben. Der **XmlValidatingReader** erweitert die Entitäten, bevor Sie von gelesen werden <xref:System.Data.DataSet> .  
  
 In den folgenden Codebeispielen wird dargestellt, wie ein <xref:System.Data.DataSet> aus einem XML-Stream geladen wird. Das erste Beispiel zeigt, wie ein Dateiname an die Methode "read **XML** " übermittelt wird. Im zweiten Beispiel wird eine Zeichenfolge mit XML-Daten mithilfe eines <xref:System.IO.StringReader> geladen.  
  
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
> Wenn Sie " **infoxml** " zum Laden einer sehr großen Datei aufzurufen, kann die Leistung beeinträchtigt werden. Um die beste Leistung für " **infoxml**" zu gewährleisten, müssen Sie die <xref:System.Data.DataTable.BeginLoadData%2A> -Methode für jede Tabelle in der abrufen <xref:System.Data.DataSet> und dann " **infoxml**" aufzurufen. Rufen Sie zum Schluss <xref:System.Data.DataTable.EndLoadData%2A> für jede Tabelle im <xref:System.Data.DataSet> auf. Dies wird im folgenden Beispiel dargestellt.  
  
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
> Wenn das XSD-Schema für den <xref:System.Data.DataSet> einen **targetNamespace**enthält, werden die Daten möglicherweise nicht gelesen, und beim Aufrufen von "read **XML** " zum Laden von <xref:System.Data.DataSet> mit XML, das Elemente ohne qualifizierenden Namespace enthält, können Ausnahmen auftreten. Um nicht qualifizierte Elemente in diesem Fall zu lesen, legen Sie **Element Form default** im XSD-Schema auf "qualified" fest. Beispiel:  
  
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
 Wenn das <xref:System.Data.DataSet> bereits Daten enthält, werden die neuen Daten aus der XML-Quelle den im <xref:System.Data.DataSet> bereits vorhandenen Daten hinzugefügt. "Read **XML** " wird nicht aus dem XML-Code in die <xref:System.Data.DataSet> Zeilen Informationen mit übereinstimmenden primär Schlüsseln zusammengeführt. Um vorhandene Zeilen Informationen mit neuen Informationen aus XML zu überschreiben, verwenden Sie " **infoxml** ", um eine neue zu erstellen <xref:System.Data.DataSet> , und dann <xref:System.Data.DataSet.Merge%2A> die neue <xref:System.Data.DataSet> in die vorhandene <xref:System.Data.DataSet> . Beachten Sie, dass beim Laden eines DiffGram mithilfe von "read **XML** " mit dem **xmllesemode** " **DiffGram** " Zeilen zusammengeführt werden, die denselben eindeutigen Bezeichner aufweisen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- [DiffGrams](diffgrams.md)
- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](inferring-dataset-relational-structure-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](loading-dataset-schema-information-from-xml.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
