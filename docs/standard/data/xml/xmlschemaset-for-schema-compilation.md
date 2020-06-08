---
title: "\"XmlSchemaSet\" zur Kompilierung von Schemata"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 55c4b175-3170-4071-9d60-dd5a42f79b54
ms.openlocfilehash: 44850755c41b212e88e0b90dd3b016f96a0af96d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290226"
---
# <a name="xmlschemaset-for-schema-compilation"></a>"XmlSchemaSet" zur Kompilierung von Schemata
Beschreibt das <xref:System.Xml.Schema.XmlSchemaSet>, bei dem es sich um einen Cache handelt, in dem XSD-Schemata (XML Schema Definition Language) gespeichert und validiert werden können.  
  
## <a name="the-xmlschemaset-class"></a>Die XmlSchemaSet-Klasse  
 Beim <xref:System.Xml.Schema.XmlSchemaSet> handelt es sich um einen Cache, in dem XSD-Schemata (XML Schema Definition Language) gespeichert und validiert werden können.  
  
 In <xref:System.Xml?displayProperty=nameWithType>, Version 1.0, wurden XML-Schemata als Schemabibliothek in eine <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse geladen. In <xref:System.Xml?displayProperty=nameWithType>, Version 2.0, sind die <xref:System.Xml.XmlValidatingReader>-Klasse und die <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse veraltet und wurden durch die <xref:System.Xml.XmlReader.Create%2A>-Methoden bzw. die <xref:System.Xml.Schema.XmlSchemaSet>-Klasse ersetzt.  
  
 Das <xref:System.Xml.Schema.XmlSchemaSet> wurde eingeführt, um eine Reihe von Problemen einschließlich der Kompatibilität mit Standards, der Leistungsfähigkeit und des veralteten Microsoft XDR-Schemaformats (XML-Data Reduced) zu beheben.  
  
 Es folgt ein Vergleich zwischen der <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse und der <xref:System.Xml.Schema.XmlSchemaSet>-Klasse.  
  
|XmlSchemaCollection|XmlSchemaSet|  
|-------------------------|------------------|  
|Unterstützt Microsoft XDR-Schemata und XML-Schemata des W3C.|Unterstützt nur XML-Schemata des W3C.|  
|Die Schemata werden beim Aufrufen der <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A>-Methode kompiliert.|Die Schemata werden beim Aufrufen der <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode nicht kompiliert. Dadurch wird die Leistungsfähigkeit während der Erstellung der Schemabibliothek erhöht.|  
|Von jedem Schema wird eine einzelne kompilierte Version erstellt, was zu "Schemainseln" führen kann. Folglich werden alle Includes und Importe nur innerhalb dieses Schemas zugeordnet.|Kompilierte Schemata erstellen ein einzelnes logisches Schema, eine "Gruppe" von Schemata. Alle importierten Schemata innerhalb eines Schemas, die der Gruppe hinzugefügt werden, werden der Gruppe selbst direkt hinzugefügt. Daher sind alle Typen für alle Schemata verfügbar.|  
|Es kann nur ein Schema für einen bestimmten Zielnamespace in der Auflistung vorhanden sein.|Es können mehrere Schemata für denselben Zielnamespace hinzugefügt werden, wenn keine Typenkonflikte auftreten.|  
  
## <a name="migrating-to-the-xmlschemaset"></a>Migrieren zum "XmlSchemaSet"  
 Im folgenden Codebeispiel ist eine Anleitung zum Migrieren von der veralteten <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse zur neuen <xref:System.Xml.Schema.XmlSchemaSet>-Klasse enthalten. Im Codebeispiel werden die folgenden Hauptunterschiede zwischen den beiden Klassen veranschaulicht.  
  
- Im Gegensatz zur <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A>-Methode der <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse werden die Schemata beim Aufrufen der <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode von <xref:System.Xml.Schema.XmlSchemaSet> nicht kompiliert. Die <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode von <xref:System.Xml.Schema.XmlSchemaSet> wird im Beispielcode explizit aufgerufen.  
  
- Wenn Sie ein <xref:System.Xml.Schema.XmlSchemaSet> durchlaufen möchten, verwenden Sie die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft des <xref:System.Xml.Schema.XmlSchemaSet>.  
  
 Nachfolgend ist ein Beispiel des veralteten <xref:System.Xml.Schema.XmlSchemaCollection>-Codes angegeben.  
  
```vb  
Dim schemaCollection As XmlSchemaCollection = New XmlSchemaCollection()  
schemaCollection.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaCollection.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema in schemaCollection  
  
   Console.WriteLine(schema.TargetNamespace)  
  
Next  
```  
  
```csharp  
XmlSchemaCollection schemaCollection = new XmlSchemaCollection();  
schemaCollection.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaCollection.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
  
foreach(XmlSchema schema in schemaCollection)  
{  
   Console.WriteLine(schema.TargetNamespace);  
}  
```  
  
 Nachfolgend ist ein Beispiel des entsprechenden <xref:System.Xml.Schema.XmlSchemaSet>-Codes angegeben.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Compile()  
  
Dim schema As XmlSchema  
  
For Each schema in schemaSet.Schemas()  
  
   Console.WriteLine(schema.TargetNamespace)  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Compile();  
  
foreach(XmlSchema schema in schemaSet.Schemas())  
{  
   Console.WriteLine(schema.TargetNamespace);  
}  
```  
  
## <a name="adding-and-retrieving-schemas"></a>Hinzufügen und Abrufen von Schemata  
 Schemata werden einem <xref:System.Xml.Schema.XmlSchemaSet> mithilfe der <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode von <xref:System.Xml.Schema.XmlSchemaSet> hinzugefügt. Wenn ein Schema einem <xref:System.Xml.Schema.XmlSchemaSet> hinzugefügt wird, wird es einem Namespace-URI zugeordnet. Der Zielnamespace-URI kann als Parameter für die <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode angegeben werden. Wenn kein Namespace angegeben wurde, verwendet das <xref:System.Xml.Schema.XmlSchemaSet> den im Schema angegebenen Zielnamespace.  
  
 Schemata werden mithilfe der <xref:System.Xml.Schema.XmlSchemaSet>-Eigenschaft des <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> aus dem <xref:System.Xml.Schema.XmlSchemaSet> abgerufen. Mit der <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft des <xref:System.Xml.Schema.XmlSchemaSet> können Sie die im <xref:System.Xml.Schema.XmlSchema> enthaltenen <xref:System.Xml.Schema.XmlSchemaSet>-Objekte durchlaufen. Die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft gibt entweder alle im<xref:System.Xml.Schema.XmlSchema> enthaltenen <xref:System.Xml.Schema.XmlSchemaSet>-Objekte zurück. Ansonsten, wenn ein Parameter für den Zielnamespace angegeben wurde, werden alle zu diesem Zielnamespace gehörenden <xref:System.Xml.Schema.XmlSchema>-Objekte zurückgegeben. Wenn `null` als Parameter für den Zielnamespace angegeben wurde, gibt die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft alle Schemata ohne Namespace zurück.  
  
 Im folgenden Beispiel wird einem `books.xsd` das `http://www.contoso.com/books`-Schema im <xref:System.Xml.Schema.XmlSchemaSet>-Namespace hinzugefügt. Außerdem werden alle Schemas, die zum `http://www.contoso.com/books`-Namespace gehören, aus dem <xref:System.Xml.Schema.XmlSchemaSet> abgerufen und in die <xref:System.Console> geschrieben.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet  
schemaSet.Add("http://www.contoso.com/books", "books.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema In schemaSet.Schemas("http://www.contoso.com/books")  
  
   schema.Write(Console.Out)  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/books", "books.xsd");  
  
foreach (XmlSchema schema in schemaSet.Schemas("http://www.contoso.com/books"))  
{  
   schema.Write(Console.Out);  
}  
```  
  
 Weitere Informationen über das Hinzufügen und Abrufen von Schemata aus einem <xref:System.Xml.Schema.XmlSchemaSet>-Objekt finden Sie in der Referenzdokumentation zur <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode und zur <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft.  
  
## <a name="compiling-schemas"></a>Kompilieren von Schemata  
 In einem <xref:System.Xml.Schema.XmlSchemaSet> befindliche Schemata werden von der <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode des <xref:System.Xml.Schema.XmlSchemaSet> in ein logisches Schema kompiliert.  
  
> [!NOTE]
> Im Gegensatz zur veralteten <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse werden die Schemata beim Aufrufen der <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode nicht kompiliert.  
  
 Wenn die <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode erfolgreich ausgeführt wird, wird die <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>-Eigenschaft des <xref:System.Xml.Schema.XmlSchemaSet> auf `true` festgelegt.  
  
> [!NOTE]
> Die <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>-Eigenschaft wird nicht beeinflusst, wenn Schemata im <xref:System.Xml.Schema.XmlSchemaSet> bearbeitet werden. Updates der einzelnen Schemata im <xref:System.Xml.Schema.XmlSchemaSet> werden nicht nachverfolgt. Folglich kann die <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>-Eigenschaft `true` sein, obwohl eines der im <xref:System.Xml.Schema.XmlSchemaSet> enthaltenen Schemata veraltet ist, wenn keine Schemata aus dem <xref:System.Xml.Schema.XmlSchemaSet> hinzugefügt oder entfernt wurden.  
  
 Im folgenden Beispiel wird die `books.xsd`-Datei dem <xref:System.Xml.Schema.XmlSchemaSet> hinzugefügt und anschließend eine <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode aufgerufen.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/books", "books.xsd")  
schemaSet.Compile()  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/books", "books.xsd");  
schemaSet.Compile();  
```  
  
 Weitere Informationen über das Kompilieren von Schemata in einem <xref:System.Xml.Schema.XmlSchemaSet> finden Sie in der Referenzdokumentation zur <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode.  
  
## <a name="reprocessing-schemas"></a>Wiederverarbeiten von Schemata  
 Beim Wiederverarbeiten eines Schemas in einem <xref:System.Xml.Schema.XmlSchemaSet> werden alle Wiederverarbeitungsschritte durchgeführt, die beim Aufrufen der <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode des <xref:System.Xml.Schema.XmlSchemaSet> für ein Schema durchgeführt werden. Wenn die <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode erfolgreich aufgerufen wurde, wird die <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>-Eigenschaft des <xref:System.Xml.Schema.XmlSchemaSet> auf `false` festgelegt.  
  
 Die <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode sollte verwendet werden, wenn ein Schema im <xref:System.Xml.Schema.XmlSchemaSet> geändert wurde, nachdem von <xref:System.Xml.Schema.XmlSchemaSet> die Kompilierung durchgeführt wurde.  
  
 Im folgenden Beispiel wird die Wiederverarbeitung eines Schemas dargestellt, das dem <xref:System.Xml.Schema.XmlSchemaSet> mithilfe der <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode hinzugefügt wurde. Nachdem das <xref:System.Xml.Schema.XmlSchemaSet> mithilfe der <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode kompiliert und das dem <xref:System.Xml.Schema.XmlSchemaSet> hinzugefügte Schema geändert wurde, wird die <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>-Eigenschaft auf `true` festgelegt, obwohl ein Schema im <xref:System.Xml.Schema.XmlSchemaSet> geändert wurde. Beim Aufrufen der <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode werden alle von der <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode durchgeführten Wiederverarbeitungsschritte ausgeführt, und die <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>-Eigenschaft wird auf `false` festgelegt.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
Dim schema As XmlSchema = schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Compile()  
  
Dim element As XmlSchemaElement = New XmlSchemaElement()  
schema.Items.Add(element)  
element.Name = "book"  
element.SchemaTypeName = New XmlQualifiedName("string", "http://www.w3.org/2001/XMLSchema")  
  
schemaSet.Reprocess(schema)  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
XmlSchema schema = schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Compile();  
  
XmlSchemaElement element = new XmlSchemaElement();  
schema.Items.Add(element);  
element.Name = "book";  
element.SchemaTypeName = new XmlQualifiedName("string", "http://www.w3.org/2001/XMLSchema");  
  
schemaSet.Reprocess(schema);  
```  
  
 Weitere Informationen über das Wiederverarbeiten eines Schemas in einem <xref:System.Xml.Schema.XmlSchemaSet> finden Sie in der Referenzdokumentation zur <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode.  
  
## <a name="checking-for-a-schema"></a>Suche nach einem Schema  
 Sie können die <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>-Methode des <xref:System.Xml.Schema.XmlSchemaSet> verwenden, um festzustellen ob in einem <xref:System.Xml.Schema.XmlSchemaSet> ein Schema enthalten ist. Die <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>-Methode sucht entweder nach einem Zielnamespace oder einem <xref:System.Xml.Schema.XmlSchema>-Objekt. In beiden Fällen gibt die <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>-Methode `true` zurück, wenn im <xref:System.Xml.Schema.XmlSchemaSet> ein Schema enthalten ist. Andernfalls gibt sie `false` zurück.  
  
 Weitere Informationen über das Suchen nach einem Schema finden Sie in der Referenzdokumentation zur <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>-Methode.  
  
## <a name="removing-schemas"></a>Entfernen von Schemata  
 Schemata werden mithilfe der <xref:System.Xml.Schema.XmlSchemaSet>-Methode und der <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A>-Methode des <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> aus einem <xref:System.Xml.Schema.XmlSchemaSet> entfernt. Die <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A>-Methode entfernt das angegebene Schema aus dem <xref:System.Xml.Schema.XmlSchemaSet>, wohingegen die <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>-Methode das angegebene Schema und alle aus dem <xref:System.Xml.Schema.XmlSchemaSet> importierten Schemata entfernt.  
  
 Im folgenden Beispiel wird das Hinzufügen mehrerer Schemata zu einem <xref:System.Xml.Schema.XmlSchemaSet> und die anschließende Verwendung der <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>-Methode zum Entfernen eines der Schemata und aller von ihr importierten Schemata veranschaulicht.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Add("http://www.contoso.com/music", "http://www.contoso.com/music.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema In schemaSet.Schemas()  
  
   If schema.TargetNamespace = "http://www.contoso.com/music" Then  
      schemaSet.RemoveRecursive(schema)  
   End If  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Add("http://www.contoso.com/music", "http://www.contoso.com/music.xsd");  
  
foreach (XmlSchema schema in schemaSet.Schemas())  
{  
   if (schema.TargetNamespace == "http://www.contoso.com/music")  
   {  
      schemaSet.RemoveRecursive(schema);  
   }  
}  
```  
  
 Weitere Informationen über das Entfernen von Schemata aus einem <xref:System.Xml.Schema.XmlSchemaSet> finden Sie in der Referenzdokumentation zur <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A>-Methode und zur <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>-Methode.  
  
## <a name="schema-resolution-and-xsimport"></a>Schemaauflösung und „xs:import“  
 In den folgenden Beispielen wird die Verhaltensweise des <xref:System.Xml.Schema.XmlSchemaSet> beim Importieren von Schemata beschrieben, wenn in einem <xref:System.Xml.Schema.XmlSchemaSet> mehrere Schemata für einen angegebenen Namespace vorhanden sind.  
  
 Betrachten Sie beispielsweise ein <xref:System.Xml.Schema.XmlSchemaSet>, das mehrere Schemata für den `http://www.contoso.com`-Namespace enthält. Ein Schema mit der folgenden `xs:import`-Anweisung wird dem <xref:System.Xml.Schema.XmlSchemaSet> hinzugefügt.  
  
```xml  
<xs:import namespace="http://www.contoso.com" schemaLocation="http://www.contoso.com/schema.xsd" />  
```  
  
 Das <xref:System.Xml.Schema.XmlSchemaSet> versucht, ein Schema für den `http://www.contoso.com`-Namespace durch Laden aus der URL `http://www.contoso.com/schema.xsd` zu importieren. Im Importschema sind nur die Schemadeklaration und die im Schemadokument deklarierten Typen verfügbar, obwohl im `http://www.contoso.com` andere Schemadokumente für den <xref:System.Xml.Schema.XmlSchemaSet>-Namespace vorhanden sind. Wenn die `schema.xsd`-Datei nicht unter der URL `http://www.contoso.com/schema.xsd` gefunden werden kann, wird kein Schema für den `http://www.contoso.com`-Namespace in das Importschema importiert.  
  
## <a name="validating-xml-documents"></a>Validierung von XML-Dokumenten  
 XML-Dokumente können anhand von Schemata in einem <xref:System.Xml.Schema.XmlSchemaSet> validiert werden. Sie validieren ein XML-Dokument, indem Sie der <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A>-Eigenschaft eines <xref:System.Xml.XmlReaderSettings>-Objekts ein Schema hinzufügen oder indem Sie der <xref:System.Xml.XmlReaderSettings.Schemas%2A>-Eigenschaft eines <xref:System.Xml.XmlReaderSettings>-Objekts eine <xref:System.Xml.Schema.XmlSchemaSet>-Klasse hinzufügen. Das <xref:System.Xml.XmlReaderSettings>-Objekt wird anschließend von der <xref:System.Xml.XmlReader.Create%2A>-Methode der <xref:System.Xml.XmlReader>-Klasse verwendet, um ein <xref:System.Xml.XmlReader>-Objekt zu erstellen und um das XML-Dokument zu validieren.  
  
 Weitere Informationen zum Validieren von XML-Dokumenten mithilfe einer <xref:System.Xml.Schema.XmlSchemaSet>-Klasse finden Sie unter [Validierung eines XML-Schemas (XSD) mit „XmlSchemaSet“](xml-schema-xsd-validation-with-xmlschemaset.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>
- [„XmlSchemaSet“ zur Kompilierung von Schemata](xmlschemaset-for-schema-compilation.md)
- [Validierung eines XML-Schemas (XSD) mit „XmlSchemaSet“](xml-schema-xsd-validation-with-xmlschemaset.md)
