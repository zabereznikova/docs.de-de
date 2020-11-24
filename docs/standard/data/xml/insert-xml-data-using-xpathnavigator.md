---
title: Einfügen von XML-Daten mit "XPathNavigator"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 2ed8c28b-b88d-4be7-9c87-92df01f0821f
ms.openlocfilehash: 1a0fa96c0fc4db1ab005961728e81b6940cd00e6
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822711"
---
# <a name="insert-xml-data-using-xpathnavigator"></a>Einfügen von XML-Daten mit "XPathNavigator"
Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt eine Gruppe von Methoden bereit, die zum Einfügen von nebengeordneten und untergeordneten Knoten sowie von Attributknoten in ein XML-Dokument verwendet werden. Diese Methoden können nur dann verwendet werden, wenn das <xref:System.Xml.XPath.XPathNavigator>-Objekt bearbeitet werden kann, d. h. seine <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Eigenschaft muss `true` sein.  
  
 <xref:System.Xml.XPath.XPathNavigator>-Objekte, die ein XML-Dokument bearbeiten können, werden von der <xref:System.Xml.XmlDocument.CreateNavigator%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse erstellt. <xref:System.Xml.XPath.XPathNavigator>-Objekte, die von der <xref:System.Xml.XPath.XPathDocument>-Klasse erstellt werden, sind schreibgeschützt. Der Versuch, die Bearbeitungsmethoden eines <xref:System.Xml.XPath.XPathNavigator>-Objekts anzuwenden, das von einem <xref:System.Xml.XPath.XPathDocument>-Objekt erstellt wurde, führt zu einer <xref:System.NotSupportedException>.  
  
 Weitere Informationen zum Erstellen bearbeitbarer <xref:System.Xml.XPath.XPathNavigator>-Objekte finden Sie unter [Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).  
  
## <a name="inserting-nodes"></a>Einfügen von Knoten  
 Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt Methoden zum Einfügen von nebengeordneten und untergeordneten Knoten sowie von Attributknoten in ein XML-Dokument bereit. Mit diesen Methoden können Sie Knoten und Attribute an verschiedenen Stellen entsprechend der aktuellen Position eines <xref:System.Xml.XPath.XPathNavigator>-Objekts einfügen. Diese Methoden werden in den folgenden Abschnitten beschrieben.  
  
### <a name="inserting-sibling-nodes"></a>Einfügen von nebengeordneten Knoten  
 Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die folgenden Methoden zum Einfügen von nebengeordneten Knoten bereit.  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>  
  
 Diese Methoden fügen vor und nach dem Knoten, auf dem gerade ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, nebengeordnete Knoten ein.  
  
 Die <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>-Methode sind überladen und verwenden als Parameter einen `string`, ein <xref:System.Xml.XmlReader>-Objekt oder ein <xref:System.Xml.XPath.XPathNavigator>-Objekt, in dem der hinzuzufügende nebengeordnete Knoten enthalten ist. Beide Methoden geben ein <xref:System.Xml.XmlWriter>-Objekt zurück, das zum Einfügen von nebengeordneten Knoten verwendet wird.  
  
 Die <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>-Methode fügen vor und nach dem Knoten, auf dem gerade ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, nebengeordnete Knoten ein. Dabei werden das angegebene Namespacepräfix und der angegebene lokale Name, der Namespace-URI und der Wert als Parameter verwendet.  
  
 Im folgenden Beispiel wird vor dem untergeordneten `pages`-Element des ersten `price`-Element in der Datei `book` ein neues `contosoBooks.xml`-Element eingefügt.  
  
 [!code-cpp[XPathNavigatorMethods#19](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#19)]
 [!code-csharp[XPathNavigatorMethods#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#19)]
 [!code-vb[XPathNavigatorMethods#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#19)]  
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 Weitere Informationen zu den Methoden <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> und <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> finden Sie in der Referenzdokumentation der <xref:System.Xml.XPath.XPathNavigator>-Klasse.  
  
### <a name="inserting-child-nodes"></a>Einfügen von untergeordneten Knoten  
 Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die folgenden Methoden zum Einfügen von untergeordneten Knoten bereit.  
  
- <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>  
  
 Diese Methoden fügen untergeordnete Knoten an das Ende und an den Anfang der Liste untergeordneter Knoten des Knotens an, auf dem gegenwärtig ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist.  
  
 Genau wie die Methoden im Abschnitt "Einfügen von nebengeordneten Knoten" verwenden die <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>-Methode als Parameter einen `string`, ein <xref:System.Xml.XmlReader>-Objekt oder ein <xref:System.Xml.XPath.XPathNavigator>-Objekt, in dem der hinzuzufügende nebengeordnete Knoten enthalten ist. Beide Methoden geben ein <xref:System.Xml.XmlWriter>-Objekt zurück, das zum Einfügen von untergeordneten Knoten verwendet wird.  
  
 Genau wie die Methoden im Abschnitt "Einfügen von nebengeordneten Knoten" fügen die <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>-Methode einen untergeordneten Knoten an das Ende und an den Anfang der Liste untergeordneter Knoten des Knotens an, auf dem gegenwärtig ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist. Dabei werden das angegebene Namespacepräfix und der angegebene lokale Name, der Namespace-URI und der Wert als Parameter verwendet.  
  
 Im folgenden Beispiel wird der Liste mit untergeordneten Elementen des ersten `pages`-Elements in der Datei `book` ein neues untergeordnetes `contosoBooks.xml`-Element angefügt.  
  
 [!code-cpp[XPathNavigatorMethods#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#2)]
 [!code-csharp[XPathNavigatorMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#2)]
 [!code-vb[XPathNavigatorMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#2)]  
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 Weitere Informationen zu den Methoden <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> und <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> finden Sie in der Referenzdokumentation der <xref:System.Xml.XPath.XPathNavigator>-Klasse.  
  
### <a name="inserting-attribute-nodes"></a>Einfügen von Attributknoten  
 Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die folgenden Methoden zum Einfügen von Attributknoten bereit.  
  
- <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>  
  
 Diese Methoden fügen in dem Elementknoten, auf dem gerade ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, Attributknoten ein. Die <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>-Methode erstellt in dem Elementknoten, auf dem gerade ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, einen Attributknoten. Dabei werden das angegebene Namespacepräfix und der angegebene lokale Name, der Namespace-URI und der Wert als Parameter verwendet. Die <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>-Methode gibt ein <xref:System.Xml.XmlWriter>-Objekt zurück, das zum Einfügen von Attributknoten verwendet wird.  
  
 Im folgenden Beispiel werden mit dem von der `discount`-Methode zurückgegebenen `currency`-Objekt im untergeordneten `price`-Element des ersten `book`-Elements in der Datei `contosoBooks.xml` ein neues <xref:System.Xml.XmlWriter>-Attribut und ein neues <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>-Attribut erstellt.  
  
 [!code-cpp[XPathNavigatorMethods#8](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#8)]
 [!code-csharp[XPathNavigatorMethods#8](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#8)]
 [!code-vb[XPathNavigatorMethods#8](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#8)]  
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 Weitere Informationen zur <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>-Methode und zur <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.XPath.XPathNavigator>-Klasse.  
  
## <a name="copying-nodes"></a>Kopieren von Knoten  
 In bestimmten Fällen möchten Sie möglicherweise ein XML-Dokument mit dem Inhalt eines anderen XML-Dokuments füllen. Sowohl die <xref:System.Xml.XPath.XPathNavigator>-Klasse als auch die <xref:System.Xml.XmlWriter>-Klasse können Knoten aus einem vorhandenen <xref:System.Xml.XmlDocument>-Objekt oder <xref:System.Xml.XmlReader>-Objekt in ein <xref:System.Xml.XPath.XPathNavigator>-Objekt kopieren.  
  
 Die Methoden <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, die <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> und <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> der <xref:System.Xml.XPath.XPathNavigator>-Klasse verfügen alle über Überladungen, die ein <xref:System.Xml.XPath.XPathNavigator>-Objekt oder ein <xref:System.Xml.XmlReader>-Objekt als Parameter annehmen können.  
  
 Die <xref:System.Xml.XmlWriter.WriteNode%2A>-Methode der <xref:System.Xml.XmlWriter>-Klasse verfügt über Überladungen, die ein <xref:System.Xml.XmlNode>-Objekt, ein <xref:System.Xml.XmlReader>-Objekt oder ein <xref:System.Xml.XPath.XPathNavigator>-Objekt annehmen können.  
  
 Im folgenden Beispiel werden alle `book`-Elemente aus einem Dokument in ein anderes kopiert.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
  
Dim newBooks As XPathDocument = New XPathDocument("newBooks.xml")  
Dim newBooksNavigator As XPathNavigator = newBooks.CreateNavigator()  
  
Dim nav As XPathNavigator  
For Each nav in newBooksNavigator.SelectDescendants("book", "", false)  
    navigator.AppendChild(nav)  
Next  
  
document.Save("newBooks.xml");  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
  
XPathDocument newBooks = new XPathDocument("newBooks.xml");  
XPathNavigator newBooksNavigator = newBooks.CreateNavigator();  
  
foreach (XPathNavigator nav in newBooksNavigator.SelectDescendants("book", "", false))  
{  
    navigator.AppendChild(nav);  
}  
  
document.Save("newBooks.xml");  
```  
  
## <a name="inserting-values"></a>Einfügen von Werten  
 Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode zum Einfügen von Werten für einen Knoten in ein <xref:System.Xml.XmlDocument>-Objekt bereit.  
  
### <a name="inserting-untyped-values"></a>Einfügen von nicht typisierten Werten  
 Die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode fügt einfach den als Parameter übergebenen nicht typisierten `string`-Wert als Wert des Knotens ein, auf dem das <xref:System.Xml.XPath.XPathNavigator>-Objekt gerade positioniert ist. Der Wert wird ohne Typ bzw. (falls Schemainformationen verfügbar sind) ohne Prüfung der Gültigkeit des neuen Werts bezüglich des Knotentyps eingefügt.  
  
 Im folgenden Beispiel werden alle <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Elemente in der Datei `price` mit der `contosoBooks.xml`-Methode aktualisiert.  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="inserting-typed-values"></a>Einfügen von typisierten Werten  
 Wenn der Typ ein einfacher W3C-XML-Schematyp ist, wird der neue mit der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode eingefügte Wert anhand aller Facets des einfachen Typs überprüft, bevor er festgelegt wird. Wenn der neue Wert bezüglich des Knotentyps nicht gültig ist (z. B. der Wert `-1` für ein Element vom Typ `xs:positiveInteger`), wird eine Ausnahme ausgelöst.  
  
 Im folgenden Beispiel wird versucht, den Wert des `price`-Elements des ersten `book`-Elements der Datei `contosoBooks.xml` in einen <xref:System.DateTime>-Wert zu ändern. Da der XML-Schematyp des `price`-Elements in den `xs:decimal`-Dateien als `contosoBooks.xsd` definiert ist, führt dies zu einer Ausnahme.  
  
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
  
navigator.SetTypedValue(DateTime.Now)  
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
  
navigator.SetTypedValue(DateTime.Now);  
```  
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 In diesem Beispiel wird auch `contosoBooks.xsd` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
## <a name="the-innerxml-and-outerxml-properties"></a>Die Eigenschaften "InnerXml" und "OuterXml"  
 Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse ändern das XML-Markup der Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist.  
  
 Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft ändert das XML-Markup der untergeordneten Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, mit den analysierten Inhalten des angegebenen XML-`string`. Ebenso ändert die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft das XML-Markup der untergeordneten Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, sowie den aktuellen Knoten selbst.  
  
 Neben den in diesem Thema beschriebenen Methoden können die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft zum Einfügen von Knoten und Werten in ein XML-Dokument verwendet werden. Weitere Informationen zum Verwenden der Eigenschaften <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> und <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> zum Einfügen von Knoten und Werten finden Sie im Thema [Ändern von XML-Daten mit XPathNavigator](modify-xml-data-using-xpathnavigator.md).  
  
## <a name="namespace-and-xmllang-conflicts"></a>Konflikte bei Namespaces und "xml:lang"  
 Beim Einfügen von XML-Daten mit der Methoden `xml:lang`, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> und <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> der <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>-Klasse, die <xref:System.Xml.XPath.XPathNavigator>-Objekte als Parameter verwenden, können bestimmte Konflikte bezüglich des Gültigkeitsbereichs von Namespaces und <xref:System.Xml.XmlReader>-Deklarationen auftreten.  
  
 Nachfolgend werden alle möglicherweise auftretenden Konflikte bei Namespaces dargestellt.  
  
- Wenn sich ein Namespace innerhalb des Kontextbereichs des <xref:System.Xml.XmlReader>-Objekts befindet, bei dem sich das Präfix zur Zuordnung des Namespace-URI nicht im Kontext des <xref:System.Xml.XPath.XPathNavigator>-Objekts befindet, wird dem neu eingefügten Knoten eine neue Namespacedeklaration hinzugefügt.  
  
- Wenn sich der gleiche Namespace-URI innerhalb des Kontextbereichs des <xref:System.Xml.XmlReader>-Objekts und des <xref:System.Xml.XPath.XPathNavigator>-Objekts befindet, aber wenn ihm in beiden Kontexten ein anderes Präfix zugeordnet wurde, wird dem neu eingefügten Knoten eine neue Namespacedeklaration hinzugefügt, wobei das Präfix und der Namespace-URI des <xref:System.Xml.XmlReader>-Objekts verwendet werden.  
  
- Wenn sich das gleiche Namespacepräfix innerhalb des Kontextbereichs des <xref:System.Xml.XmlReader>-Objekts und des <xref:System.Xml.XPath.XPathNavigator>-Objekts befindet, aber wenn ihm in beiden Kontexten ein anderer Namespace-URI zugeordnet wurde, wird dem neu eingefügten Knoten eine neue Namespacedeklaration hinzugefügt,. Dabei wird das Präfix mit dem Namespace-URI des <xref:System.Xml.XmlReader>-Objekts erneut deklariert.  
  
- Wenn das Präfix sowie der Namespace-URI im Kontext des <xref:System.Xml.XmlReader>-Objekts und im Kontext des <xref:System.Xml.XPath.XPathNavigator>-Objekts gleich sind, wird dem neu eingefügten Knoten keine neue Namespacedeklaration hinzugefügt.  
  
> [!NOTE]
> Die oben genannte Beschreibung gilt auch für Namespacedeklarationen mit einem leeren `string` als Präfix (z. B. die Standardnamespacedeklaration).  
  
 Nachfolgend werden alle möglicherweise auftretenden Konflikte bei `xml:lang` dargestellt.  
  
- Wenn sich ein `xml:lang`-Attribut im Kontextbereich des <xref:System.Xml.XmlReader>-Objekts, aber nicht im Kontext des <xref:System.Xml.XPath.XPathNavigator>-Objekts befindet, wird dem neu eingefügten Knoten ein `xml:lang`-Attribut hinzugefügt, dessen Wert aus dem <xref:System.Xml.XmlReader>-Objekt entnommen wird.  
  
- Wenn sich ein `xml:lang`-Attribut im Kontextbereich des <xref:System.Xml.XmlReader>-Objekts und des <xref:System.Xml.XPath.XPathNavigator>-Objekts befindet, aber jedes Attribut einen anderen Wert besitzt, wird dem neu eingefügten Knoten ein `xml:lang`-Attribut hinzugefügt, dessen Wert aus dem <xref:System.Xml.XmlReader>-Objekt entnommen wird.  
  
- Wenn sich ein `xml:lang`-Attribut im Kontextbereich des <xref:System.Xml.XmlReader>-Objekts und des <xref:System.Xml.XPath.XPathNavigator>-Objekts befindet, aber beide Attribute den gleichen Wert besitzen, wird dem neu eingefügten Knoten kein neues `xml:lang`-Attribut hinzugefügt.  
  
- Wenn sich ein `xml:lang`-Attribut im Kontextbereich des <xref:System.Xml.XPath.XPathNavigator>-Objekts, aber nicht im Kontextbereich des <xref:System.Xml.XmlReader>-Objekts befindet, wird dem neu eingefügten Knoten kein `xml:lang`-Attribut hinzugefügt.  
  
## <a name="inserting-nodes-with-xmlwriter"></a>Einfügen von Knoten mit "XmlWriter"  
 Die im Abschnitt zum Einfügen von Knoten und Werten beschriebenen Methoden zum Einfügen von nebengeordneten und untergeordneten Knoten sowie von Attributknoten sind überladen. Die Methoden <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> und <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> der <xref:System.Xml.XPath.XPathNavigator>-Klasse geben ein <xref:System.Xml.XmlWriter>-Objekt zurück, das zum Einfügen von Knoten verwendet wird.  
  
### <a name="unsupported-xmlwriter-methods"></a>Nicht unterstützte XmlWriter-Methoden  
 Nicht alle Methoden, mit denen unter Verwendung der <xref:System.Xml.XmlWriter>-Klasse Informationen in ein XML-Dokument geschrieben werden, werden aufgrund des Unterschieds zwischen dem XPath-Datenmodell und dem DOM (Dokumentobjektmodell) von der <xref:System.Xml.XPath.XPathNavigator>-Klasse unterstützt.  
  
 In der folgenden Tabelle werden die Methoden der <xref:System.Xml.XmlWriter>-Klasse beschrieben, die nicht von der <xref:System.Xml.XPath.XPathNavigator>-Klasse unterstützt werden.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.XmlWriter.WriteEntityRef%2A>|Löst eine <xref:System.NotSupportedException>-Ausnahme aus.|  
|<xref:System.Xml.XmlWriter.WriteDocType%2A>|Wird auf der Stammebene ignoriert und löst beim Aufrufen auf einer anderen Ebene im XML-Dokument eine <xref:System.NotSupportedException>-Ausnahme aus.|  
|<xref:System.Xml.XmlWriter.WriteCData%2A>|Wird wie ein Aufruf der <xref:System.Xml.XmlWriter.WriteString%2A>-Methode für die entsprechenden Zeichen behandelt.|  
|<xref:System.Xml.XmlWriter.WriteCharEntity%2A>|Wird wie ein Aufruf der <xref:System.Xml.XmlWriter.WriteString%2A>-Methode für die entsprechenden Zeichen behandelt.|  
|<xref:System.Xml.XmlWriter.WriteSurrogateCharEntity%2A>|Wird wie ein Aufruf der <xref:System.Xml.XmlWriter.WriteString%2A>-Methode für die entsprechenden Zeichen behandelt.|  
  
 Weitere Informationen zur <xref:System.Xml.XmlWriter>-Klasse finden Sie in der Referenzdokumentation der <xref:System.Xml.XmlWriter>-Klasse.  
  
### <a name="multiple-xmlwriter-objects"></a>Mehrere XmlWriter-Objekte  
 Es ist möglich, über mehrere <xref:System.Xml.XPath.XPathNavigator>-Objekte zu verfügen, die auf verschiedene Teile eines XML-Dokuments mit einem oder mehreren offenen <xref:System.Xml.XmlWriter>-Objekten zeigen. In Szenarios mit einfachen Threads sind mehrere <xref:System.Xml.XmlWriter>-Objekte zulässig und werden dort unterstützt.  
  
 Die folgenden beiden Anmerkungen sollten bei der Verwendung mehrerer <xref:System.Xml.XmlWriter>-Objekte unbedingt beachtet werden.  
  
- Dem XML-Dokument werden von <xref:System.Xml.XmlWriter>-Objekten geschriebene XML-Fragmente hinzugefügt, wenn die <xref:System.Xml.XmlWriter.Close%2A>-Methode eines jeden <xref:System.Xml.XmlWriter>-Objekts aufgerufen wird. Bis zu diesem Zeitpunkt schreibt das <xref:System.Xml.XmlWriter>-Objekt ein nicht verbundenes Fragment. Das Ausführen eines Vorgangs für das XML-Dokument wirkt sich nicht auf Fragmente aus, die vor dem Aufrufen von <xref:System.Xml.XmlWriter> von einem <xref:System.Xml.XmlWriter.Close%2A>-Objekt geschrieben wurden.  
  
- Wenn sich auf einer bestimmten XML-Unterstruktur ein offenes <xref:System.Xml.XmlWriter>-Objekt befindet und diese Unterstruktur gelöscht wird, könnte das <xref:System.Xml.XmlWriter>-Objekt der Unterstruktur noch hinzugefügt werden. Aus der Teilstruktur wird einfach ein gelöschtes Fragment.  
  
- Wenn an der gleichen Stelle im XML-Dokument mehrere <xref:System.Xml.XmlWriter>-Objekte geöffnet sind, werden sie dem XML-Dokument in der Reihenfolge hinzugefügt, in der die <xref:System.Xml.XmlWriter>-Objekte geschlossen werden, und nicht in der Reihenfolge, in der sie geöffnet wurden.  
  
 Im folgenden Beispiel werden ein <xref:System.Xml.XmlDocument>-Objekt sowie ein <xref:System.Xml.XPath.XPathNavigator>-Objekt erstellt und anschließend ein von der <xref:System.Xml.XmlWriter>-Methode zurückgegebenes <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>-Objekt verwendet, um die Struktur des ersten Buchs in der Datei `books.xml` zu erstellen. Anschließend wird sie im Beispiel als die Datei `book.xml` gespeichert.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Using writer As XmlWriter = navigator.PrependChild()  
  
    writer.WriteStartElement("bookstore")  
    writer.WriteStartElement("book")  
    writer.WriteAttributeString("genre", "autobiography")  
    writer.WriteAttributeString("publicationdate", "1981-03-22")  
    writer.WriteAttributeString("ISBN", "1-861003-11-0")  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin")  
    writer.WriteStartElement("author")  
    writer.WriteElementString("first-name", "Benjamin")  
    writer.WriteElementString("last-name", "Franklin")  
    writer.WriteElementString("price", "8.99")  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
  
End Using  
  
document.Save("book.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
XPathNavigator navigator = document.CreateNavigator();  
  
using (XmlWriter writer = navigator.PrependChild())  
{  
    writer.WriteStartElement("bookstore");  
    writer.WriteStartElement("book");  
    writer.WriteAttributeString("genre", "autobiography");  
    writer.WriteAttributeString("publicationdate", "1981-03-22");  
    writer.WriteAttributeString("ISBN", "1-861003-11-0");  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin");  
    writer.WriteStartElement("author");  
    writer.WriteElementString("first-name", "Benjamin");  
    writer.WriteElementString("last-name", "Franklin");  
    writer.WriteElementString("price", "8.99");  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
}  
document.Save("book.xml");  
```  
  
## <a name="saving-an-xml-document"></a>Speichern eines XML-Dokuments  
 Änderungen eines <xref:System.Xml.XmlDocument>-Objekts, die von den in diesem Thema beschriebenen Methoden vorgenommen wurden, werden mit den Methoden der <xref:System.Xml.XmlDocument>-Klasse gespeichert. Weitere Informationen zum Speichern der an einem <xref:System.Xml.XmlDocument>-Objekt vorgenommenen Änderungen finden Sie unter [Speichern und Ausgeben eines Dokuments](saving-and-writing-a-document.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](process-xml-data-using-the-xpath-data-model.md)
- [Ändern von XML-Daten mit XPathNavigator](modify-xml-data-using-xpathnavigator.md)
- [Entfernen von XML-Daten mit XPathNavigator](remove-xml-data-using-xpathnavigator.md)
