---
title: Laden von DataSet-Schemainformationen aus XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 4b212a7233e6eec93cdce3e521b58e08745e35e0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="loading-dataset-schema-information-from-xml"></a>Laden von DataSet-Schemainformationen aus XML
Das Schema der eine <xref:System.Data.DataSet> (seine Tabellen, Spalten, Beziehungen und Einschränkungen) können programmgesteuert definiert, erstellt, indem die **füllen** oder **FillSchema** Methoden eine <xref:System.Data.Common.DataAdapter>, oder aus geladen ein XML-Dokument. Beim Laden **DataSet** Schemainformationen aus einem XML-Dokument verwenden Sie entweder die **ReadXmlSchema** oder **InferXmlSchema** Methode der **DataSet**. **ReadXmlSchema** können Sie zum Laden oder herleiten **DataSet** Schemainformationen aus dem Dokument, das Schema für XML Schema Definition Language (XSD) oder ein XML-Dokument mit Inline-XML-Schema enthält. **InferXmlSchema** ermöglicht das Herleiten des Schemas aus der XML-Dokument während bestimmte von Ihnen angegebenen XML-Namespaces ignoriert.  
  
> [!NOTE]
>  Tabellenreihenfolge in einem **DataSet** möglicherweise nicht beibehalten, wenn Sie zum Übertragen von Webdiensten oder XML-Serialisierung verwenden eine **DataSet** , mithilfe von XSD-Konstrukten (z. B. geschachtelten Beziehungen) im Arbeitsspeicher erstellt wurde. Aus diesem Grund für den Empfänger des der **DataSet** sollten Tabellenreihenfolge in diesem Fall nicht erforderlich. Allerdings Tabellenreihenfolge wird immer beibehalten, wenn das Schema der **DataSet** übertragenen gelesene aus XSD-Dateien, anstatt im Arbeitsspeicher erstellt wird.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Zum Laden des Schemas ein **DataSet** aus einem XML-Dokument ohne Daten zu laden, können Sie die **ReadXmlSchema** Methode der **DataSet**. **ReadXmlSchema** erstellt **DataSet** Schema mithilfe von Schemas für XML Schema Definition Language (XSD) definiert.  
  
 Die **ReadXmlSchema** Methode akzeptiert ein einzelnes Argument eines Dateinamens, einen Stream oder eine **XmlReader** mit dem XML-Dokument geladen werden. Das XML-Dokument kann nur ein Schema enthalten. Es kann aber auch ein Inlineschema mit XML-Elementen besitzen, die über Daten verfügen. Informationen über das Schreiben von Inlineschema als XML-Schema finden Sie unter [ableiten relationalen DataSet-Struktur von XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Wenn das XML-Dokument übergeben **ReadXmlSchema** keine Inlineschemainformationen enthält **ReadXmlSchema** das Schema aus den Elementen im XML-Dokument. Wenn die **DataSet** bereits ein Schema enthält, das aktuelle Schema erweitert, indem neue Tabellen hinzugefügt werden, wenn sie nicht bereits vorhanden sind. Vorhandenen Tabellen werden keine neuen Spalten hinzugefügt. Ggf. eine hinzuzufügende Spalte bereits in der **DataSet** aber hat ein inkompatiblen Typ mit der Spalte gefunden, in der XML-Code wird eine Ausnahme ausgelöst. Weitere Informationen dazu, wie **ReadXmlSchema** leitet ein Schema aus einem XML-Dokument, finden Sie unter [Ableiten von relationalen DataSet-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).  
  
 Obwohl **ReadXmlSchema** lädt oder herleitet nur das Schema des eine **DataSet**, die **ReadXml** Methode der **DataSet** lädt oder herleitet, beide Das Schema und die Daten in das XML-Dokument enthalten sind. Weitere Informationen finden Sie unter [beim Laden eines Datasets aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).  
  
 Die folgenden Codebeispiele zeigen, wie beim Laden einer **DataSet** Schema aus einem XML-Dokument oder den Stream. Im ersten Beispiel wird ein XML-Schema-Dateiname übergeben werden, um die **ReadXmlSchema** Methode. Im zweiten Beispiel wird eine **System.IO.StreamReader**.  
  
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
 Sie können auch festlegen, dass die **DataSet** Ableiten von dessen Schema aus einer XML-Dokuments mithilfe der **InferXmlSchema** Methode der **DataSet**. **InferXmlSchema** funktioniert genauso wie **ReadXml** mit einem **XmlReadMode** von **InferSchema** (lädt Daten sowie leitet das Schema ab), und **ReadXmlSchema** , wenn das gelesene Dokument kein Inlineschema enthält. Allerdings **InferXmlSchema** zusätzlich die Möglichkeit Möglichkeit an bestimmte XML-Namespaces ignoriert werden, wenn das Schema abgeleitet wird. **InferXmlSchema** hat zwei erforderliche Argumente: den Speicherort der XML-Dokuments, angegeben durch einen Dateinamen, einen Stream oder eine **XmlReader**; und ein Zeichenfolgenarray mit XML-Namespaces, die vom Vorgang ignoriert werden.  
  
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
  
 Aufgrund der Attribute für die Elemente in der vorhergehenden XML-Dokument sowohl die **ReadXmlSchema** Methode und die **ReadXml** Methode mit einer **XmlReadMode** von **InferSchema** würde Erstellen von Tabellen für jedes Element im Dokument: **Kategorien**, **CategoryID**, **CategoryName**, **Beschreibung**, **Produkte**, **"ProductID"**, **ReorderLevel**, und **nicht mehr unterstützte**. (Weitere Informationen finden Sie unter [Ableiten von relationalen DataSet-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) Eine besser geeignete Struktur wäre jedoch nur für Erstellung der **Kategorien** und **Produkte** Tabellen, und klicken Sie dann auf Erstellen **CategoryID**, **CategoryName** , und **Beschreibung** Spalten in der **Kategorien** Tabelle und **"ProductID"**, **ReorderLevel**, und **Discontinued** Spalten in der **Produkte** Tabelle. Verwenden, um sicherzustellen, dass das hergeleitete Schema die in der XML-Elementen angegebenen Attribute ignoriert die **InferXmlSchema** Methode, und geben Sie den XML-Namespace für **Officedata** ignoriert werden soll, wie in dargestellt, die folgende.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
