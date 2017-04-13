---
title: "Laden eines DataSet aus XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Laden eines DataSet aus XML
Der Inhalt eines ADO.NET\-<xref:System.Data.DataSet> kann aus einem XML\-Stream oder einem XML\-Dokument erstellt werden.  Außerdem können Sie mit .NET Framework größtenteils festlegen, welche Informationen aus der XML\-Quelle geladen werden sollen und wie das Schema oder die relationale Struktur des <xref:System.Data.DataSet> erstellt werden soll.  
  
 Verwenden Sie zum Füllen eines <xref:System.Data.DataSet> mit Daten aus einer XML\-Quelle die **ReadXml**\-Methode des <xref:System.Data.DataSet>\-Objekts.  Die **ReadXml**\-Methode liest Daten aus einer Datei, einem Stream oder einem **XmlReader** und verwendet die Quelle der XML\-Daten sowie ein optionales **XmlReadMode**\-Argument als Argumente.  \(Weitere Informationen zum **XmlReader** finden Sie unter [NIB: Reading XML Data with XmlTextReader](http://msdn.microsoft.com/de-de/762c069b-b50c-41b8-936e-39eacfb0d540).\) Die **ReadXml**\-Methode liest den Inhalt des XML\-Streams oder des XML\-Dokuments und füllt das <xref:System.Data.DataSet> mit Daten.  In Abhängigkeit vom angegebenen **XmlReadMode** und vom Vorhandensein eines relationalen Schemas erstellt die Methode außerdem das relationale Schema des <xref:System.Data.DataSet>.  
  
 In der folgenden Tabelle werden die Optionen für das **XmlReadMode**\-Argument beschrieben.  
  
|Option|Beschreibung|  
|------------|------------------|  
|**Auto**|Dies ist die Standardeinstellung.  Prüft die XML\-Daten und wählt die am besten geeignete Option in der folgenden Reihenfolge aus:<br /><br /> -   Wenn die XML\-Daten im DiffGram\-Format vorliegen, wird **DiffGram** verwendet.<br />-   Wenn das <xref:System.Data.DataSet> ein Schema enthält oder die XML\-Daten ein Inlineschema besitzen, wird **ReadSchema** verwendet.<br />-   Wenn das <xref:System.Data.DataSet> kein Schema enthält und die XML\-Daten kein Inlineschema besitzen, wird **InferSchema** verwendet.<br /><br /> Wenn Sie das Format der gelesenen XML\-Daten kennen, besteht die effizienteste Methode darin, anstelle der Standardeinstellung **Auto** ein explizites **XmlReadMode**\-Argument anzugeben.|  
|**ReadSchema**|Liest beliebige Inlineschemata und lädt Daten und Schemata.<br /><br /> Wenn das <xref:System.Data.DataSet> bereits ein Schema enthält, werden neue Tabellen aus dem Inlineschema zum vorhandenen Schema im <xref:System.Data.DataSet> hinzugefügt.  Wenn bereits Tabellen im Inlineschema des <xref:System.Data.DataSet> vorhanden sind, wird eine Ausnahme ausgelöst.  Sie können das Schema einer vorhandenen Tabelle nicht mit **XmlReadMode.ReadSchema** ändern.<br /><br /> Wenn das <xref:System.Data.DataSet> kein Schema enthält und kein Inlineschema vorhanden ist, werden keine Daten gelesen.<br /><br /> Ein Inlineschema kann mit dem XSD\-Schema \(XML Schema Definition Language\) definiert werden.  Ausführliche Informationen zum Schreiben eines Inlineschemas als XML\-Schema finden Sie unter [Ableiten einer relationalen 'DataSet'\-Struktur aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Ignoriert alle Inlineschemata und lädt die Daten in das vorhandene <xref:System.Data.DataSet>\-Schema.  Daten, die nicht mit dem vorhandenen Schema übereinstimmen, werden gelöscht.  Wenn kein Schema im <xref:System.Data.DataSet> vorhanden ist, werden keine Daten geladen.<br /><br /> Wenn es sich bei den Daten um DiffGram\-Daten handelt, hat **IgnoreSchema** dieselbe Funktion wie **DiffGram**|  
|**InferSchema**|Ignoriert alle Inlineschemata, leitet das Schema aus der Struktur der XML\-Daten ab und lädt anschließend die Daten.<br /><br /> Wenn das <xref:System.Data.DataSet> bereits ein Schema enthält, wird das aktuelle Schema durch Hinzufügen von Spalten zu den vorhandenen Tabellen erweitert.  Wenn keine Tabellen vorhanden sind, werden keine zusätzlichen Tabellen hinzugefügt.  Eine Ausnahme wird ausgelöst, wenn bereits eine hergeleitete Tabelle mit einem anderen Namespace vorhanden ist oder wenn hergeleitete Spalten mit vorhandenen Spalten kollidieren.<br /><br /> Ausführliche Informationen zum Herleiten eines Schemas aus einem XML\-Dokument durch **ReadXmlSchema** finden Sie unter [Herleiten der relationalen DataSet\-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).|  
|**DiffGram**|Liest ein DiffGram und fügt die Daten dem aktuellen Schema hinzu.  **DiffGram** führt neue Zeilen mit vorhandenen Zeilen zusammen, wenn die eindeutigen Bezeichnerwerte übereinstimmen.  Informationen hierzu finden Sie unter "Zusammenführen von Daten aus XML\-Dokumenten" am Ende dieses Themas.  Weitere Informationen zu DiffGrams finden Sie unter [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
|**Fragment**|Setzt den Lesevorgang für mehrere XML\-Fragmente fort, bis das Ende des Streams erreicht ist.  Fragmente, die mit dem <xref:System.Data.DataSet>\-Schema übereinstimmen, werden an die entsprechenden Tabellen angehängt.  Fragmente, die nicht mit dem <xref:System.Data.DataSet>\-Schema übereinstimmen, werden gelöscht.|  
  
> [!NOTE]
>  Wenn Sie einen **XmlReader** an die **ReadXml**\-Methode übergeben, die sich innerhalb eines XML\-Dokuments befindet, liest **ReadXml** bis zum nächsten Elementknoten, behandelt diesen als Stammelement und liest dann nur bis zum Ende des Elementknotens.  Dies trifft nicht zu, wenn Sie **XmlReadMode.Fragment** verwenden.  
  
## DTD\-Entitäten  
 Bei einem XML\-Dokument mit Entitäten, die in einem DTD\-Schema \(Document Type Definition\) definiert sind, wird eine Ausnahme ausgelöst, wenn Sie versuchen, ein <xref:System.Data.DataSet> zu laden, indem Sie einen Dateinamen, einen Stream oder einen nicht validierten **XmlReader** an **ReadXml** übergeben.  Erstellen Sie stattdessen einen **XmlValidatingReader**, bei dem **EntityHandling** auf **EntityHandling.ExpandEntities** festgelegt ist, und übergeben Sie anschließend den **XmlValidatingReader** an **ReadXml**.  Der **XmlValidatingReader** erweitert die Entitäten, bevor er vom <xref:System.Data.DataSet> gelesen wird.  
  
 In den folgenden Codebeispielen wird dargestellt, wie ein <xref:System.Data.DataSet> aus einem XML\-Stream geladen wird.  Im ersten Beispiel wird ein Dateiname an die **ReadXml**\-Methode übergeben.  Im zweiten Beispiel wird eine Zeichenfolge mit XML\-Daten mithilfe eines <xref:System.IO.StringReader> geladen.  
  
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
>  Wenn für das Laden einer sehr großen Datei **ReadXml** aufgerufen wird, führt dies möglicherweise zu einem Leistungsabfall.  Damit **ReadXml** mit optimaler Effizienz verwendet werden kann, rufen Sie bei einer großen Datei zunächst die <xref:System.Data.DataTable.BeginLoadData%2A>\-Methode für jede Tabelle im <xref:System.Data.DataSet> auf, und rufen Sie anschließend **ReadXml** auf.  Rufen Sie zum Schluss <xref:System.Data.DataTable.EndLoadData%2A> für jede Tabelle im <xref:System.Data.DataSet> auf. Dies wird im folgenden Beispiel dargestellt.  
  
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
>  Wenn zum XSD\-Schema für das <xref:System.Data.DataSet> ein **targetNamespace** gehört, werden die Daten möglicherweise nicht gelesen. Außerdem können Ausnahmen ausgelöst werden, wenn Sie **ReadXml** zum Laden des <xref:System.Data.DataSet> mit XML aufrufen, das Elemente ohne qualifizierenden Namespace enthält.  Damit in diesem Fall nicht qualifizierte Elemente gelesen werden können, legen Sie im XSD\-Schema **elementFormDefault** auf "qualified" fest.  Beispiel:  
  
```  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## Zusammenführen von Daten aus XML\-Dokumenten  
 Wenn das <xref:System.Data.DataSet> bereits Daten enthält, werden die neuen Daten aus der XML\-Quelle den im <xref:System.Data.DataSet> bereits vorhandenen Daten hinzugefügt.  **ReadXml** fügt keine Zeileninformationen mit übereinstimmenden Primärschlüsseln aus dem XML\-Dokument in das <xref:System.Data.DataSet> ein.  Wenn vorhandene Zeileninformationen mit neuen XML\-Informationen überschrieben werden sollen, müssen Sie mit **ReadXml** zunächst ein neues <xref:System.Data.DataSet> erstellen. Führen Sie anschließend einen <xref:System.Data.DataSet.Merge%2A>\-Vorgang aus, um das neue <xref:System.Data.DataSet> mit dem vorhandenen <xref:System.Data.DataSet> zusammenzuführen.  Wenn Sie ein DiffGram mit **ReadXML** laden und **XmlReadMode** auf **DiffGram** festgelegt ist, werden die Zeilen mit identischem Bezeichner zusammengeführt.  
  
## Siehe auch  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=fullName>   
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)   
 [Ableiten einer relationalen 'DataSet'\-Struktur aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)   
 [Herleiten der relationalen DataSet\-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Laden von DataSet\-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)