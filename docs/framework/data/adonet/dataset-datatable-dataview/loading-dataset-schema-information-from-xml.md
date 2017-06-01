---
title: "Laden von DataSet-Schemainformationen aus XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Laden von DataSet-Schemainformationen aus XML
Das Schema eines <xref:System.Data.DataSet> \(seine Tabellen, Spalten, Beziehungen und Einschränkungen\) kann programmgesteuert definiert, von der **Fill**\-Methode oder der **FillSchema**\-Methode eines <xref:System.Data.Common.DataAdapter> erstellt oder aus einem XML\-Dokument geladen werden.  Zum Laden von **DataSet**\-Schemainformationen aus einem XML\-Dokument können Sie entweder die **ReadXmlSchema**\-Methode oder die **InferXmlSchema**\-Methode des **DataSet** verwenden.  Mit **ReadXmlSchema** können Sie **DataSet**\-Schemainformationen aus dem Dokument mit dem XSD\-Schema \(XML Schema Definition Language\) oder aus einem XML\-Dokument mit einem Inline\-XML\-Schema laden oder herleiten.  **InferXmlSchema** ermöglicht das Herleiten des Schemas aus dem XML\-Dokument, während bestimmte von Ihnen angegebene XML\-Namespaces ignoriert werden.  
  
> [!NOTE]
>  Die Tabellenreihenfolge in einem **DataSet** wird u. U. nicht beibehalten, wenn Sie ein **DataSet**, das unter Verwendung von XSD\-Konstrukten \(wie z. B. geschachtelten Beziehungen\) im Arbeitsspeicher erstellt wurde, mittels Webdiensten oder XML\-Serialisierung übertragen.  Der Empfänger des **DataSet** sollte daher in diesem Fall keine bestimmte Tabellenreihenfolge voraussetzen.  Wenn jedoch das Schema des zu übertragenden **DataSet** nicht im Speicher erstellt, sondern aus XSD\-Dateien gelesen wird, wird die Tabellenreihenfolge immer beibehalten.  
  
## ReadXmlSchema  
 Sie können die **ReadXmlSchema**\-Methode des **DataSet** verwenden, um das Schema eines **DataSet** ohne Daten aus einem XML\-Dokument zu laden.  **ReadXmlSchema** erstellt ein **DataSet**\-Schema, das mit dem XSD\-Schema \(XML Schema Definition Language\) definiert wird.  
  
 Die **ReadXmlSchema**\-Methode verwendet ein einzelnes Argument. Dabei kann es sich um den Namen einer Datei, einen Stream oder einen **XmlReader** mit dem zu ladenden XML\-Dokument handeln.  Das XML\-Dokument kann nur ein Schema enthalten. Es kann aber auch ein Inlineschema mit XML\-Elementen besitzen, die über Daten verfügen.  Ausführliche Informationen zum Schreiben eines Inlineschemas als XML\-Schema finden Sie unter [Ableiten einer relationalen 'DataSet'\-Struktur aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Wenn das an **ReadXmlSchema** übergebene XML\-Dokument keine Inlineschemainformationen enthält, leitet **ReadXmlSchema** das Schema von den Elementen im XML\-Dokument ab.  Wenn das **DataSet** bereits ein Schema enthält, wird das aktuelle Schema erweitert, indem neue Tabellen hinzugefügt werden, sofern diese nicht bereits vorhanden sind.  Vorhandenen Tabellen werden keine neuen Spalten hinzugefügt.  Wenn eine hinzuzufügende Spalte bereits im **DataSet** vorhanden, deren Typ aber nicht mit der im XML\-Dokument gefundenen Spalte kompatibel ist, wird eine Ausnahme ausgelöst.  Ausführliche Informationen zum Herleiten eines Schemas aus einem XML\-Dokument durch **ReadXmlSchema** finden Sie unter [Herleiten der relationalen DataSet\-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).  
  
 Während **ReadXmlSchema** lediglich das Schema eines **DataSet** lädt oder herleitet, werden mit der **ReadXml**\-Methode des **DataSet** sowohl das Schema als auch die im XML\-Dokument enthaltenen Daten geladen oder hergeleitet.  Weitere Informationen finden Sie unter [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).  
  
 In den folgenden Codebeispielen wird dargestellt, wie ein **DataSet**\-Schema aus einem XML\-Dokument oder einem XML\-Stream geladen wird.  Im ersten Beispiel wird gezeigt, wie der Dateiname eines XML\-Schemas an die **ReadXmlSchema**\-Methode übergeben wird.  Im zweiten Beispiel wird ein **System.IO.StreamReader** dargestellt.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As System.IO.StreamReader = New System.IO.StreamReader ("schema.xsd");  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema(xmlStream)  
xmlStream.Close()  
```  
  
```csharp  
System.IO.StreamReader xmlStream = new System.IO.StreamReader("schema.xsd");  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema(xmlStream);  
xmlStream.Close();  
```  
  
## InferXmlSchema  
 Sie können das **DataSet** auch anweisen, sein Schema mit der **InferXmlSchema**\-Methode des **DataSet** aus einem XML\-Dokument abzuleiten.  **InferXmlSchema** funktioniert wie **ReadXml** zusammen mit einem auf **InferSchema** festgelegten **XmlReadMode** \(lädt Daten und leitet das Schema ab\) und **ReadXmlSchema**, wenn das gelesene Dokument kein Inlineschema enthält.  Allerdings haben Sie mit **InferXmlSchema** zusätzlich die Möglichkeit, bestimmte XML\-Namespaces anzugeben, die beim Herleiten des Schemas ignoriert werden sollen.  **InferXmlSchema** wird mit den folgenden zwei erforderlichen Argumenten verwendet: dem Speicherort des XML\-Dokuments, das durch einen Dateinamen, einen Stream oder einen **XmlReader** angegeben wird, und einem Zeichenfolgenarray aus XML\-Namespaces, die vom Vorgang ignoriert werden sollen.  
  
 Betrachten Sie beispielsweise den folgenden XML\-Code:  
  
```  
<NewDataSet xmlns:od="urn:schemas-microsoft-com:officedata">  
<Categories>  
  <CategoryID od:adotype="3">1</CategoryID>   
  <CategoryName od:maxLength="15" od:adotype="130">Beverages</CategoryName>   
  <Description od:adotype="203">Soft drinks and teas</Description>   
</Categories>  
<Products>  
  <ProductID od:adotype="20">1</ProductID>   
  <ReorderLevel od:adotype="3">10</ReorderLevel>   
  <Discontinued od:adotype="11">0</Discontinued>   
</Products>  
</NewDataSet>  
```  
  
 Aufgrund der Attribute, die für die Elemente im vorhergehenden XML\-Dokument angegeben wurden, würden die **ReadXmlSchema**\-Methode und die **ReadXml**\-Methode \(mit einem auf **InferSchema** festgelegten **XmlReadMode**\) für jedes Element im Dokument Tabellen erstellen: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel** und **Discontinued**.  \(Weitere Informationen finden Sie unter [Herleiten der relationalen DataSet\-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).\) Die geeignetere Vorgehensweise bestünde jedoch darin, zunächst nur die Tabellen **Categories** und **Products** und dann die Spalten **CategoryID**, **CategoryName** und **Description** in der Tabelle **Categories** sowie die Spalten **ProductID**, **ReorderLevel** und **Discontinued** in der Tabelle **Products** zu erstellen.  Damit sichergestellt wird, dass das hergeleitete Schema die in den XML\-Elementen angegebenen Attribute ignoriert, geben Sie mit der **InferXmlSchema**\-Methode an, dass der XML\-Namespace für **officedata** ignoriert werden soll. Dies wird im folgenden Beispiel dargestellt.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## Siehe auch  
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Ableiten einer relationalen 'DataSet'\-Struktur aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)   
 [Herleiten der relationalen DataSet\-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)