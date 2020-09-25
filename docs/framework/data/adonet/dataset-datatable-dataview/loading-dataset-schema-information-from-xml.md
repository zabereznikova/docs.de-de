---
title: Laden von DataSet-Schemainformationen aus XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: b084590d7158024227a9f12da759b56ae2031373
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201342"
---
# <a name="loading-dataset-schema-information-from-xml"></a>Laden von DataSet-Schemainformationen aus XML

Das Schema von a <xref:System.Data.DataSet> (Tabellen, Spalten, Beziehungen und Einschränkungen) kann Programm gesteuert definiert, durch die **Fill** -Methode oder die **FillSchema** -Methode eines erstellt <xref:System.Data.Common.DataAdapter> oder aus einem XML-Dokument geladen werden. Zum Laden von **DataSet** -Schema Informationen aus einem XML-Dokument können Sie entweder die " **infoxmlschema** "-Methode oder die **InferXmlSchema** -Methode des **DataSets**verwenden. Mit " **infoxmlschema** " können Sie **DataSet** -Schema Informationen aus dem Dokument, das das XSD-Schema (XML Schema Definition Language) enthält, oder ein XML-Dokument mit Inline-XML-Schema laden bzw. daraus ableiten. Mit **InferXmlSchema** können Sie das Schema aus dem XML-Dokument ableiten, während bestimmte von Ihnen angegebene XML-Namespaces ignoriert werden.  
  
> [!NOTE]
> Die Tabellen Anordnung in einem **DataSet** wird möglicherweise nicht beibehalten, wenn Sie Webdienste oder XML-Serialisierung verwenden, um ein **DataSet** zu übertragen, das in-Memory mithilfe von XSD-Konstrukten (z. b. gruppierte Beziehungen) erstellt wurde. Daher sollte der Empfänger des **DataSets** in diesem Fall nicht von der Tabellen Anordnung abhängen. Die Tabellen Anordnung wird jedoch immer beibehalten, wenn das Schema des übertragenen **DataSets** aus XSD-Dateien gelesen wurde und nicht im Arbeitsspeicher erstellt wurde.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  

 Wenn Sie das Schema eines **DataSets** aus einem XML-Dokument ohne das Laden von Daten laden möchten, können Sie die Methode "read **XmlSchema** " des **DataSets**verwenden. Das mit dem XSD-Schema (XML Schema Definition Language) definierte **DataSet** -Schema wird von "read **XmlSchema** " erstellt.  
  
 Die Methode "read **XmlSchema** " nimmt ein einzelnes Argument eines Datei namens, eines Streams oder eines **XmlReader** , der das zu ladende XML-Dokument enthält. Das XML-Dokument kann nur ein Schema enthalten. Es kann aber auch ein Inlineschema mit XML-Elementen besitzen, die über Daten verfügen. Ausführliche Informationen zum Schreiben eines Inline Schemas als XML-Schema finden Sie unter [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Wenn das an " **infoxmlschema** " übergebenen XML-Dokument keine Inline Schema Informationen enthält, leitet " **infoxmlschema** " das Schema aus den Elementen im XML-Dokument ab. Wenn das **DataSet** bereits ein Schema enthält, wird das aktuelle Schema erweitert, indem neue Tabellen hinzugefügt werden, sofern diese nicht bereits vorhanden sind. Vorhandenen Tabellen werden keine neuen Spalten hinzugefügt. Wenn eine hinzugefügte Spalte bereits im **DataSet** vorhanden ist, aber einen nicht kompatiblen Typ mit der im XML gefundenen Spalte aufweist, wird eine Ausnahme ausgelöst. Ausführliche Informationen dazu, wie " **infoxmlschema** " ein Schema aus einem XML-Dokument ableitet, finden Sie unter [ableiten der relationalen DataSet-Struktur aus XML](inferring-dataset-relational-structure-from-xml.md).  
  
 Obwohl das Schema eines **DataSets**von " **infoxmlschema** " geladen oder abgerufen wird, werden sowohl das Schema als auch die Daten, die im XML-Dokument enthalten sind, von der "read **XML** "-Methode des **DataSets** geladen oder abgerufen. Weitere Informationen finden Sie unter [Laden eines Datasets aus XML](loading-a-dataset-from-xml.md).  
  
 In den folgenden Codebeispielen wird gezeigt, wie ein **DataSet** -Schema aus einem XML-Dokument oder-Stream geladen wird. Im ersten Beispiel wird gezeigt, wie ein XML-Schema Dateiname an die Methode "read **XmlSchema** " übermittelt wird. Das zweite Beispiel zeigt einen **System. IO. StreamReader**.  
  
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

 Sie können das **DataSet** auch anweisen, sein Schema mithilfe der **InferXmlSchema** -Methode des **DataSets**von einem XML-Dokument abzuleiten. **InferXmlSchema** funktioniert genauso wie "read **XML** " mit einem **xmllesemode** " **InferSchema** " (lädt sowohl Daten als auch ein ausgabenschema) und "leadxmlschema", wenn das gelesene Dokument kein Inline Schema enthält. **ReadXmlSchema** **InferXmlSchema** bietet jedoch die zusätzliche Möglichkeit, bestimmte XML-Namespaces anzugeben, die beim Ableiten des Schemas ignoriert werden. **InferXmlSchema** erfordert zwei erforderliche Argumente: den Speicherort des XML-Dokuments, das durch einen Dateinamen, einen Stream oder einen **XmlReader**angegeben wird. und ein Zeichen folgen Array von XML-Namespaces, die vom Vorgang ignoriert werden sollen.  
  
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
  
 Aufgrund der Attribute, die für die Elemente im vorangehenden XML-Dokument angegeben sind, würden sowohl die "read **XmlSchema** "-Methode als auch die "read **Discontinued** **CategoryName** **Description** **XML** "-Methode mit einem " **xmllesemode** " von " **CategoryID** **InferSchema** " Tabellen für jedes Element im Dokument erstellen **Products** **:** **ProductID** **ReorderLevel** (Weitere Informationen finden Sie unter [ableiten der relationalen DataSet-Struktur aus XML](inferring-dataset-relational-structure-from-xml.md).) Eine geeignetere Struktur wäre jedoch, nur die Tabellen **Categories** und **Products** zu erstellen und dann die Spalten **CategoryID**, **CategoryName**und **Description** in der Tabelle **Categories** sowie die Spalten **ProductID**, **ReorderLevel**und nicht mehr unter **stützte Spalten in** der Tabelle **Products** zu erstellen. Um sicherzustellen, dass das abzurufende Schema die in den XML-Elementen angegebenen Attribute ignoriert, verwenden Sie die **InferXmlSchema** -Methode, und geben Sie den XML-Namespace für **officedata** an, der ignoriert werden soll, wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>Siehe auch

- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](inferring-dataset-relational-structure-from-xml.md)
- [Laden eines "DataSets" aus XML](loading-a-dataset-from-xml.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
