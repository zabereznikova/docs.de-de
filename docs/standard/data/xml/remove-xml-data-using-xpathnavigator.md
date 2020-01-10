---
title: Entfernen von XML-Daten mit "XPathNavigator"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 9f436bca-1b96-494b-a6d2-e102c7551752
ms.openlocfilehash: 062a98a9cc10e6be00f165cf617de2d92d65acbf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710361"
---
# <a name="remove-xml-data-using-xpathnavigator"></a>Entfernen von XML-Daten mit "XPathNavigator"
Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt eine Gruppe von Methoden bereit, mit denen Knoten und Werte aus einem XML-Dokument entfernt werden. Diese Methoden können nur dann verwendet werden, wenn das <xref:System.Xml.XPath.XPathNavigator>-Objekt bearbeitet werden kann, d. h. seine <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Eigenschaft muss `true` sein.  
  
 <xref:System.Xml.XPath.XPathNavigator>-Objekte, die ein XML-Dokument bearbeiten können, werden von der <xref:System.Xml.XmlDocument.CreateNavigator%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse erstellt. <xref:System.Xml.XPath.XPathNavigator>-Objekte, die von der <xref:System.Xml.XPath.XPathDocument>-Klasse erstellt werden, sind schreibgeschützt. Der Versuch, die Bearbeitungsmethoden eines <xref:System.Xml.XPath.XPathNavigator>-Objekts anzuwenden, das von einem <xref:System.Xml.XPath.XPathDocument>-Objekt erstellt wurde, führt zu einer <xref:System.NotSupportedException>.  
  
 Weitere Informationen zum Erstellen bearbeitbarer <xref:System.Xml.XPath.XPathNavigator>-Objekte finden Sie unter [Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).  
  
## <a name="removing-nodes"></a>Entfernen von Knoten  
 Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>-Methode zum Entfernen von Knoten aus einem XML-Dokument bereit.  
  
### <a name="removing-a-node"></a>Entfernen eines Knotens  
 Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>-Methode bereit, mit der der aktuelle Knoten aus einem XML-Dokument gelöscht werden kann, auf dem sich gerade ein <xref:System.Xml.XPath.XPathNavigator>-Objekt befindet.  
  
 Nachdem ein Knoten mithilfe der <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>-Methode gelöscht wurde, kann vom Stamm eines <xref:System.Xml.XmlDocument>-Objekts aus nicht mehr darauf zugegriffen werden. Nachdem der Knoten gelöscht wurde, wird der <xref:System.Xml.XPath.XPathNavigator> auf dem übergeordneten Knoten des gelöschten Knotens positioniert.  
  
 Der Löschvorgang hat keine Auswirkungen auf die Position der <xref:System.Xml.XPath.XPathNavigator>-Objekte, die sich auf dem gelöschten Knoten befinden. Diese <xref:System.Xml.XPath.XPathNavigator>-Objekte sind insofern gültig, als sie innerhalb der gelöschten Unterstruktur verschoben werden können. Sie können jedoch nicht mit einer der regulären Knotensatz-Navigationsmethoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse in die Hauptknotenstruktur verschoben werden.  
  
> [!NOTE]
> Mithilfe der <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse können diese <xref:System.Xml.XPath.XPathNavigator>-Objekte zurück in die entsprechende Hauptknotenstruktur verschoben werden bzw. aus dieser in die gelöschte Unterstruktur verschoben werden.  
  
 Im folgenden Beispiel wird das `price`-Element des ersten `book`-Elements der Datei `contosoBooks.xml` mithilfe der <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>-Methode gelöscht. Die Position des <xref:System.Xml.XPath.XPathNavigator>-Objekts, nachdem das `price`-Element im übergeordneten `book`-Element gelöscht wurde.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.DeleteSelf()  
  
Console.WriteLine("Position after delete: {0}", navigator.Name)  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.DeleteSelf();  
  
Console.WriteLine("Position after delete: {0}", navigator.Name);  
Console.WriteLine(navigator.OuterXml);  
```  
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-an-attribute-node"></a>Entfernen eines Attributknotens  
 Attributknoten können mithilfe der <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>-Methode aus einem XML-Dokument entfernt werden.  
  
 Nachdem ein Attributknoten gelöscht wurde, kann nicht mehr von einem Stammknoten eines <xref:System.Xml.XmlDocument>-Objekts aus darauf zugegriffen werden, und das <xref:System.Xml.XPath.XPathNavigator>-Objekt wird auf dem übergeordneten Element positioniert.  
  
#### <a name="default-attributes"></a>Standardattribute  
 Unabhängig davon, mit welcher Methode Attribute entfernt wurden, bestehen spezielle Einschränkungen für das Entfernen von Standardattributen in der DTD oder im XML-Schema des XML-Dokuments. Standardattribute können nicht entfernt werden, wenn nicht das zugehörige Element ebenfalls entfernt wird. Standardattribute sind immer für Elemente vorhanden, für die Standardattribute deklariert wurden. Daher führt das Löschen eines Standardattributs dazu, dass ein Ersatzattribut in das Element eingefügt und der deklarierte Standardwert initialisiert wird.  
  
## <a name="removing-values"></a>Entfernen von Werten  
 Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode zum Entfernen von nicht typisierten und typisierten Knoten aus einem XML-Dokument bereit.  
  
### <a name="removing-untyped-values"></a>Entfernen nicht typisierter Werte  
 Die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode fügt einfach den als Parameter übergebenen nicht typisierten `string`-Wert als Wert des Knotens ein, auf dem das <xref:System.Xml.XPath.XPathNavigator>-Objekt gerade positioniert ist. Durch Übergeben einer leeren Zeichenfolge an die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode wird der Wert des aktuellen Knotens entfernt.  
  
 Im folgenden Beispiel wird der Wert des `price`-Elements des ersten `book`-Elements der Datei `contosoBooks.xml` mithilfe der <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode entfernt.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetValue("")  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetValue("");  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-typed-values"></a>Entfernen typisierter Werte  
 Wenn der Typ ein einfacher W3C-XML-Schematyp ist, wird der neue mit der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode eingefügte Wert anhand aller Facets des einfachen Typs überprüft, bevor er festgelegt wird. Wenn der neue Wert bezüglich des Knotentyps nicht gültig ist (z. B. der Wert `-1` für ein Element vom Typ `xs:positiveInteger`), wird eine Ausnahme ausgelöst. Außerdem ist es nicht möglich, der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode `null` als Parameter zu übergeben. Daher muss das Entfernen eines typisierten Werts in Übereinstimmung mit dem Schematyp des Knotens erfolgen.  
  
 Im folgenden Beispiel wird der Wert des `price`-Elements des ersten `book`-Elements der Datei `contosoBooks.xml` mithilfe der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode entfernt, indem der Wert auf `0` festgelegt wird. Der Wert des Knotens wird nicht entfernt, es wird jedoch der Buchpreis entsprechend seinem Datentyp `xs:decimal` entfernt.  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetTypedValue(0)  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetTypedValue(0);  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
## <a name="namespace-nodes"></a>Namespaceknoten  
 Namespaceknoten können nicht aus einem <xref:System.Xml.XmlDocument>-Objekt gelöscht werden. Beim Versuch, Namespaceknoten mithilfe der <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>-Methode zu löschen, wird eine Ausnahme ausgelöst.  
  
## <a name="the-innerxml-and-outerxml-properties"></a>Die Eigenschaften "InnerXml" und "OuterXml"  
 Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse ändern das XML-Markup der Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist.  
  
 Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft ändert das XML-Markup der untergeordneten Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, mit den analysierten Inhalten des angegebenen XML-`string`. Ebenso ändert die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft das XML-Markup der untergeordneten Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, sowie den aktuellen Knoten selbst.  
  
 Neben den in diesem Thema beschriebenen Methoden können die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft zum Entfernen von Knoten und Werten aus einem XML-Dokument verwendet werden. Weitere Informationen zum Verwenden der Eigenschaften <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> und <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> zum Ändern von Knoten finden Sie im Thema [Ändern von XML-Daten mit XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md).  
  
## <a name="saving-an-xml-document"></a>Speichern eines XML-Dokuments  
 Änderungen eines <xref:System.Xml.XmlDocument>-Objekts, die von den in diesem Thema beschriebenen Methoden vorgenommen wurden, werden mit den Methoden der <xref:System.Xml.XmlDocument>-Klasse gespeichert. Weitere Informationen zum Speichern der an einem <xref:System.Xml.XmlDocument>-Objekt vorgenommenen Änderungen finden Sie unter [Speichern und Ausgeben eines Dokuments](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Einfügen von XML-Daten mit XPathNavigator](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)
- [Ändern von XML-Daten mit XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)
