---
title: Laden eines "DataSets" aus XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 3a781f17ac3cabebce17955b9a7e2edda4d4fd4b
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44338817"
---
# <a name="loading-a-dataset-from-xml"></a>Laden eines "DataSets" aus XML
Der Inhalt eines ADO.NET-<xref:System.Data.DataSet> kann aus einem XML-Stream oder einem XML-Dokument erstellt werden. Außerdem können Sie mit .NET Framework größtenteils festlegen, welche Informationen aus der XML-Quelle geladen werden sollen und wie das Schema oder die relationale Struktur des <xref:System.Data.DataSet> erstellt werden soll.  
  
 Zum Füllen einer <xref:System.Data.DataSet> anhand der Daten aus XML-Code, der **ReadXml** -Methode der der <xref:System.Data.DataSet> Objekt. Die **ReadXml** Methode liest aus einer Datei, einen Stream oder ein **"XmlReader"**, und verwendet als Argumente die Quelle des der XML-Code sowie ein optionales **XmlReadMode** Argument. (Weitere Informationen zu den **"XmlReader"**, finden Sie unter [NIB: Lesen von XML-Daten mit "XmlTextReader"](https://msdn.microsoft.com/library/762c069b-b50c-41b8-936e-39eacfb0d540).) Die **ReadXml** Methode liest den Inhalt der XML-Stream oder das Dokument und lädt die <xref:System.Data.DataSet> mit Daten. Es wird auch das relationale Schema erstellen, die <xref:System.Data.DataSet> abhängig der **XmlReadMode** angegeben und davon, ob ein relationales Schema bereits vorhanden ist.  
  
 Die folgende Tabelle beschreibt die Optionen für die **XmlReadMode** Argument.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Auto**|Dies ist die Standardeinstellung. Prüft die XML-Daten und wählt die am besten geeignete Option in der folgenden Reihenfolge aus:<br /><br /> – Wenn der XML-Code ein DiffGram handelt, ist **DiffGram** verwendet wird.<br />-If die <xref:System.Data.DataSet> enthält ein Schema oder der XML-Code enthält ein Inlineschema **ReadSchema** verwendet wird.<br />-If die <xref:System.Data.DataSet> enthält kein Schema und der XML-Code enthält ein Inlineschema keine **InferSchema** wird verwendet.<br /><br /> Wenn Sie das Format der gelesenen XML-Codes kennen, für eine optimale Leistung wird empfohlen, ein explizites **XmlReadMode**, sondern als akzeptieren die **automatisch** Standard.|  
|**ReadSchema**|Liest beliebige Inlineschemata und lädt Daten und Schemata.<br /><br /> Wenn das <xref:System.Data.DataSet> bereits ein Schema enthält, werden neue Tabellen aus dem Inlineschema zum vorhandenen Schema im <xref:System.Data.DataSet> hinzugefügt. Wenn bereits Tabellen im Inlineschema des <xref:System.Data.DataSet> vorhanden sind, wird eine Ausnahme ausgelöst. Sie werden nicht in der Lage, das eine vorhandene Tabelle mit Schema ändern **XmlReadMode.ReadSchema**.<br /><br /> Wenn das <xref:System.Data.DataSet> kein Schema enthält und kein Inlineschema vorhanden ist, werden keine Daten gelesen.<br /><br /> Ein Inlineschema kann mit dem XSD-Schema (XML Schema Definition Language) definiert werden. Weitere Informationen zum Schreiben eines Inlineschemas als XML-Schema finden Sie unter [ableiten relationalen DataSet-Struktur von XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Ignoriert alle Inlineschemata und lädt die Daten in das vorhandene <xref:System.Data.DataSet>-Schema. Daten, die nicht mit dem vorhandenen Schema übereinstimmen, werden gelöscht. Wenn kein Schema im <xref:System.Data.DataSet> vorhanden ist, werden keine Daten geladen.<br /><br /> Wenn die Daten ein DiffGram handelt, sind **IgnoreSchema** hat die gleiche Funktion wie **DiffGram** *.*|  
|**InferSchema**|Ignoriert alle Inlineschemata, leitet das Schema aus der Struktur der XML-Daten ab und lädt anschließend die Daten.<br /><br /> Wenn das <xref:System.Data.DataSet> bereits ein Schema enthält, wird das aktuelle Schema durch Hinzufügen von Spalten zu den vorhandenen Tabellen erweitert. Wenn keine Tabellen vorhanden sind, werden keine zusätzlichen Tabellen hinzugefügt. Eine Ausnahme wird ausgelöst, wenn bereits eine hergeleitete Tabelle mit einem anderen Namespace vorhanden ist oder wenn hergeleitete Spalten mit vorhandenen Spalten kollidieren.<br /><br /> Weitere Informationen dazu, wie **ReadXmlSchema** leitet ein Schema aus einem XML-Dokument finden Sie unter [Ableiten von relationalen DataSet-Struktur von XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).|  
|**DiffGram**|	Liest ein DiffGram und fügt die Daten dem aktuellen Schema hinzu. **DiffGram** führt neue Zeilen mit vorhandenen Zeilen, bei denen die eindeutigen Bezeichnerwerte übereinstimmen. Informationen hierzu finden Sie unter "Zusammenführen von Daten aus XML-Dokumenten" am Ende dieses Themas. Weitere Informationen zu DiffGrams finden Sie unter [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
|**Fragment**|Setzt den Lesevorgang für mehrere XML-Fragmente fort, bis das Ende des Streams erreicht ist. Fragmente, die mit dem <xref:System.Data.DataSet>-Schema übereinstimmen, werden an die entsprechenden Tabellen angehängt. Fragmente, die nicht mit dem <xref:System.Data.DataSet>-Schema übereinstimmen, werden gelöscht.|  
  
> [!NOTE]
>  Übergeben einer **"XmlReader"** zu **ReadXml** während eines in eine XML-Dokument, d. h. positionierte Teils **ReadXml** wird zum nächsten Elementknoten gelesen und behandelt, der als Stamm -Element, bis zum Ende des Elementknotens nur lesen. Dies gilt nicht, wenn Sie angeben, **XmlReadMode.Fragment**.  
  
## <a name="dtd-entities"></a>DTD-Entitäten  
 Wenn Ihr XML in einem Dokument Type Definition (DTD)-Schema definierte Entitäten enthält, wird eine Ausnahme ausgelöst, wenn Sie versuchen, Sie laden eine <xref:System.Data.DataSet> durch Übergeben einer Datei Namen, diesen Stream oder ohne Validierung **"XmlReader"** zu  **ReadXml**. Stattdessen müssen Sie erstellen ein **XmlValidatingReader**, mit **EntityHandling** festgelegt **EntityHandling.ExpandEntities**, und übergeben Sie Ihre  **XmlValidatingReader** zu **ReadXml**. Die **XmlValidatingReader** wird erweitert, die Entitäten, bevor Sie gelesen wird, durch die <xref:System.Data.DataSet>.  
  
 In den folgenden Codebeispielen wird dargestellt, wie ein <xref:System.Data.DataSet> aus einem XML-Stream geladen wird. Das erste Beispiel zeigt einen Dateinamen ein, die übergeben werden, um die **ReadXml** Methode. Im zweiten Beispiel wird eine Zeichenfolge mit XML-Daten mithilfe eines <xref:System.IO.StringReader> geladen.  
  
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
>  Wenn Sie aufrufen **ReadXml** um eine sehr große Datei zu laden, können Leistungsprobleme auftreten. Um sicherzustellen, dass beste Leistung für **ReadXml**, rufen Sie bei einer großen Datei, die <xref:System.Data.DataTable.BeginLoadData%2A> Methode für jede Tabelle in der <xref:System.Data.DataSet>, und rufen dann **ReadXml**. Rufen Sie zum Schluss <xref:System.Data.DataTable.EndLoadData%2A> für jede Tabelle im <xref:System.Data.DataSet> auf. Dies wird im folgenden Beispiel dargestellt.  
  
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
>  Wenn das XSD-Schema für Ihre <xref:System.Data.DataSet> enthält eine **TargetNamespace**kann nicht gelesen werden und beim Aufrufen können Ausnahmen auftreten **ReadXml** beim Laden der <xref:System.Data.DataSet> mit XML, die enthält Elemente ohne qualifizierenden Namespace. Legen Sie zum Lesen von nicht qualifizierte Elemente in diesem Fall **ElementFormDefault** auf "qualified" im XSD-Schema entspricht. Zum Beispiel:  
  
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
 Wenn das <xref:System.Data.DataSet> bereits Daten enthält, werden die neuen Daten aus der XML-Quelle den im <xref:System.Data.DataSet> bereits vorhandenen Daten hinzugefügt. **ReadXml** nicht zusammen in der XML-Daten in die <xref:System.Data.DataSet> alle Zeileninformationen mit übereinstimmenden Primärschlüsseln. Um vorhandene Zeileninformationen mit neuen Informationen aus XML zu überschreiben, verwenden **ReadXml** zum Erstellen eines neuen <xref:System.Data.DataSet>, und klicken Sie dann <xref:System.Data.DataSet.Merge%2A> neuen <xref:System.Data.DataSet> in die vorhandenen <xref:System.Data.DataSet>. Laden ein DiffGram mit **ReadXML** mit einer **XmlReadMode** von **DiffGram** werden Zeilen mit den gleichen Bezeichner zusammengeführt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
