---
title: Laden von DataSet-Schemainformationen aus XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 69994c546fea842ffef1c8c43d6d6f5bc35e0629
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151051"
---
# <a name="loading-dataset-schema-information-from-xml"></a>Laden von DataSet-Schemainformationen aus XML
Das Schema <xref:System.Data.DataSet> von a (seine Tabellen, Spalten, Beziehungen und Einschränkungen) kann programmgesteuert definiert, von <xref:System.Data.Common.DataAdapter>den **Fill-** oder **FillSchema-Methoden** eines erstellt oder aus einem XML-Dokument geladen werden. Zum Laden von **DataSet-Schemainformationen** aus einem XML-Dokument können Sie entweder die **ReadXmlSchema-** oder die **InferXmlSchema-Methode** des **DataSet**verwenden. **Mit ReadXmlSchema** können Sie **DataSet-Schemainformationen** aus dem Dokument laden oder ableiten, das das XSD-Schema (XML Schema) (XML Schema) oder ein XML-Dokument mit inline XML-Schema enthält. **InferXmlSchema** ermöglicht es Ihnen, das Schema aus dem XML-Dokument abzuleiten, während bestimmte von Ihnen angegebene XML-Namespaces ignoriert werden.  
  
> [!NOTE]
> Die Tabellenreihenfolge in einem **DataSet** wird möglicherweise nicht beibehalten, wenn Sie Webdienste oder XML-Serialisierung verwenden, um ein **DataSet** zu übertragen, das im Arbeitsspeicher mithilfe von XSD-Konstrukten (z. B. verschachtelten Beziehungen) erstellt wurde. Daher sollte der Empfänger des **DataSets** in diesem Fall nicht von der Tabellenreihenfolge abhängen. Die Tabellenreihenfolge bleibt jedoch immer erhalten, wenn das Schema des übertragenen **DataSets** aus XSD-Dateien gelesen wurde, anstatt im Arbeitsspeicher erstellt zu werden.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Um das Schema eines **DataSets** aus einem XML-Dokument zu laden, ohne Daten zu laden, können Sie die **ReadXmlSchema-Methode** des **DataSet**verwenden. **ReadXmlSchema** erstellt **DataSet-Schema,** das mit dem XML-Schema für die Schemadefinitionssprache (XSD) definiert wurde.  
  
 Die **ReadXmlSchema-Methode** verwendet ein einzelnes Argument eines Dateinamens, eines Streams oder eines **XmlReaders,** der das zu ladende XML-Dokument enthält. Das XML-Dokument kann nur ein Schema enthalten. Es kann aber auch ein Inlineschema mit XML-Elementen besitzen, die über Daten verfügen. Weitere Informationen zum Schreiben von Inlineschemas als XML-Schema finden Sie unter [Ableiten der relationalen Struktur von DataSet aus XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Wenn das an **ReadXmlSchema** übergebene XML-Dokument keine Inlineschemainformationen enthält, leitet **ReadXmlSchema** das Schema aus den Elementen im XML-Dokument ab. Wenn das **DataSet** bereits ein Schema enthält, wird das aktuelle Schema durch Hinzufügen neuer Tabellen erweitert, sofern sie noch nicht vorhanden sind. Vorhandenen Tabellen werden keine neuen Spalten hinzugefügt. Wenn eine hinzugefügte Spalte bereits im **DataSet** vorhanden ist, aber einen inkompatiblen Typ mit der im XML gefundenen Spalte hat, wird eine Ausnahme ausgelöst. Weitere Informationen dazu, wie **ReadXmlSchema** ein Schema aus einem XML-Dokument ableitet, finden Sie unter [Ableiten der relationalen Struktur von DataSet aus XML](inferring-dataset-relational-structure-from-xml.md).  
  
 Obwohl **ReadXmlSchema** nur das Schema eines **DataSets**lädt oder ableitet, lädt oder leitet die **ReadXml-Methode** des **DataSet** sowohl das Schema als auch die im XML-Dokument enthaltenen Daten ab. Weitere Informationen finden Sie unter [Laden eines DataSets aus XML](loading-a-dataset-from-xml.md).  
  
 Die folgenden Codebeispiele zeigen, wie Sie ein **DataSet-Schema** aus einem XML-Dokument oder -Stream laden. Das erste Beispiel zeigt einen XML-Schemadateinamen, der an die **ReadXmlSchema-Methode** übergeben wird. Das zweite Beispiel zeigt einen **System.IO.StreamReader**.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As New System.IO.StreamReader("schema.xsd")
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
  
## <a name="inferxmlschema"></a>InferXmlSchema  
 Sie können das **DataSet** auch anweisen, sein Schema aus einem XML-Dokument mit der **InferXmlSchema-Methode** des **DataSet**abzuleiten. **InferXmlSchema** funktioniert genauso wie **ReadXml** mit einem **XmlReadMode** von **InferSchema** (lädt Daten sowie Infesschema) und **ReadXmlSchema,** wenn das zu lesende Dokument kein Inlineschema enthält. **InferXmlSchema** bietet jedoch die zusätzliche Möglichkeit, bestimmte XML-Namespaces anzugeben, die ignoriert werden sollen, wenn das Schema abgeleitet wird. **InferXmlSchema** verwendet zwei erforderliche Argumente: den Speicherort des XML-Dokuments, der durch einen Dateinamen, einen Stream oder einen **XmlReader**angegeben wird. und ein Zeichenfolgenarray von XML-Namespaces, die vom Vorgang ignoriert werden sollen.  
  
 Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
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
  
 Aufgrund der für die Elemente im vorherigen XML-Dokument angegebenen Attribute würden sowohl die **ReadXmlSchema-Methode** als auch die **ReadXml-Methode** mit einem **XmlReadMode** von **InferSchema** Tabellen für jedes Element im Dokument erstellen: **Kategorien**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**und **Discontinued**. (Weitere Informationen finden Sie unter [Ableiten der relationalen Struktur von DataSet aus XML](inferring-dataset-relational-structure-from-xml.md).) Eine geeignetere Struktur wäre jedoch, nur die Tabellen **Kategorien** und **Produkte** zu erstellen und dann die Spalten **CategoryID**, **CategoryName**und **Description** in der Tabelle **Kategorien** sowie **ProductID**, **ReorderLevel**und **Discontinued** in der Tabelle **Produkte** zu erstellen. Um sicherzustellen, dass das abgeleitete Schema die in den XML-Elementen angegebenen Attribute ignoriert, verwenden Sie die **InferXmlSchema-Methode,** und geben Sie den XML-Namespace für **Officedata** an, der ignoriert werden soll, wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von XML in einem "DataSet"](using-xml-in-a-dataset.md)
- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](inferring-dataset-relational-structure-from-xml.md)
- [Laden eines "DataSets" aus XML](loading-a-dataset-from-xml.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
