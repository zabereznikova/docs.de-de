---
title: Laden von DataSet-Schemainformationen aus XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 06dcbbedf8c1533b3da52b447c121746ce705083
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083347"
---
# <a name="loading-dataset-schema-information-from-xml"></a>Laden von DataSet-Schemainformationen aus XML
Das Schema der einen <xref:System.Data.DataSet> (seine Tabellen, Spalten, Beziehungen und Einschränkungen) können programmgesteuert definiert, erstellt die **füllen** oder **FillSchema** Methoden eine <xref:System.Data.Common.DataAdapter>, oder aus der geladen ein XML-Dokument. Beim Laden **DataSet** Schemainformationen aus einer XML-Dokument, verwenden Sie entweder die **ReadXmlSchema** oder **InferXmlSchema** -Methode der der **DataSet**. **ReadXmlSchema** ermöglicht es Ihnen, laden oder herleiten **DataSet** Schemainformationen aus dem Dokument mit Schema für XML Schema Definition Language (XSD) oder ein XML-Dokument mit Inline-XML-Schema. **InferXmlSchema** ermöglicht das Herleiten des Schemas aus XML-Dokument und bestimmte von Ihnen angegebenen XML-Namespaces ignoriert.  
  
> [!NOTE]
>  Tabellenreihenfolge in einem **DataSet** möglicherweise nicht beibehalten werden, wenn Sie zum Übertragen von Webdiensten oder XML-Serialisierung verwenden eine **DataSet** , mithilfe von XSD-Konstrukten (z. B. geschachtelten Beziehungen) im Arbeitsspeicher erstellt wurde. Aus diesem Grund der Empfänger die **DataSet** dürfen nicht in diesem Fall Tabellenreihenfolge abhängen. Allerdings Tabellenreihenfolge wird immer beibehalten, wenn das Schema der **DataSet** übertragenen gelesene aus XSD-Dateien, anstatt im Arbeitsspeicher erstellt wird.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Zum Laden des Schemas einer **DataSet** aus einem XML-Dokument ohne Laden von Daten, können Sie die **ReadXmlSchema** Methode der **DataSet**. **ReadXmlSchema** erstellt **DataSet** Schema mithilfe von Schema für XML Schema Definition Language (XSD) definiert.  
  
 Die **ReadXmlSchema** Methode akzeptiert ein einzelnes Argument eines Dateinamens, einen Stream oder ein **"XmlReader"** mit dem XML-Dokument geladen werden. Das XML-Dokument kann nur ein Schema enthalten. Es kann aber auch ein Inlineschema mit XML-Elementen besitzen, die über Daten verfügen. Weitere Informationen zum Schreiben eines Inlineschemas als XML-Schema finden Sie unter [ableiten relationalen DataSet-Struktur von XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Wenn das XML-Dokument übergeben **ReadXmlSchema** enthält keine Inlineschemainformationen, **ReadXmlSchema** das Schema aus den Elementen im XML-Dokument. Wenn die **DataSet** bereits ein Schema enthält, wird das aktuelle Schema erweitert werden, indem neue Tabellen hinzugefügt, wenn sie nicht bereits vorhanden sind. Vorhandenen Tabellen werden keine neuen Spalten hinzugefügt. Wenn in eine Spalte hinzugefügt wird, bereits vorhanden ist die **DataSet** aber hat ein inkompatiblen Typ mit der Spalte gefunden wird, im XML wird eine Ausnahme ausgelöst. Weitere Informationen dazu, wie **ReadXmlSchema** leitet ein Schema aus einem XML-Dokument finden Sie unter [Ableiten von relationalen DataSet-Struktur von XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).  
  
 Obwohl **ReadXmlSchema** lädt oder herleitet lediglich das Schema eine **DataSet**, die **ReadXml** -Methode der der **DataSet** lädt oder herleitet, beide Das Schema und die Daten in das XML-Dokument. Weitere Informationen finden Sie unter [Laden eines Datasets aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).  
  
 Die folgenden Codebeispiele zeigen, wie zum Laden einer **DataSet** Schema aus einer XML-Dokument oder den Stream. Das erste Beispiel zeigt den Namen einer XML-Schema-Datei übergeben werden, um die **ReadXmlSchema** Methode. Im zweiten Beispiel wird eine **System.IO.StreamReader**.  
  
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
  
## <a name="inferxmlschema"></a>InferXmlSchema  
 Sie können auch anweisen, die **DataSet** zum Herleiten die Schemas aus einer XML-Dokument mit den **InferXmlSchema** -Methode der der **DataSet**. **InferXmlSchema** funktioniert genauso wie **ReadXml** mit einer **XmlReadMode** von **InferSchema** (lädt Daten sowie leitet das Schema), und **ReadXmlSchema** , wenn das gelesene Dokument kein Inlineschema enthält. Allerdings **InferXmlSchema** bietet zusätzliche die Möglichkeit können Sie an bestimmte XML-Namespaces ignoriert werden, wenn das Schema abgeleitet wird. **InferXmlSchema** akzeptiert zwei erforderliche Argumente: den Speicherort der XML-Dokuments, angegeben durch einen Dateinamen, einen Stream oder ein **"XmlReader"**; und ein Zeichenfolgenarray von XML-Namespaces, die vom Vorgang ignoriert werden.  
  
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
  
 Aufgrund der Attribute, die für die Elemente in der vorhergehenden XML-Dokument, angegebene sowohl die **ReadXmlSchema** Methode und die **ReadXml** -Methode mit einem **XmlReadMode** von **InferSchema** würde Tabellen für jedes Element im Dokument zu erstellen: **Kategorien**, **CategoryID**, **"CategoryName"**, **Beschreibung**, **Produkte**, **"ProductID"**, **ReorderLevel**, und **nicht mehr unterstützte**. (Weitere Informationen finden Sie unter [Ableiten von relationalen DataSet-Struktur von XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) Eine Struktur besser geeignet wäre jedoch nur erstellen, die **Kategorien** und **Produkte** Tabellen, und klicken Sie dann zum Erstellen **CategoryID**, **"CategoryName"** , und **Beschreibung** Spalten in der **Kategorien** Tabelle und **"ProductID"**, **ReorderLevel**, und **Discontinued** Spalten in der **Produkte** Tabelle. Verwenden, um sicherzustellen, dass das hergeleitete Schema die in den XML-Elementen angegebenen Attribute ignoriert die **InferXmlSchema** Methode, und geben Sie die XML-Namespace für **Officedata** ignoriert werden soll, wie in dargestellt, die folgende Beispiel.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von XML in einem "DataSet"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [Laden eines "DataSets" aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- ["DataSets", "DataTables" und "DataViews"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
