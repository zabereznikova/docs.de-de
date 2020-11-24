---
title: Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5711b225-6aa2-4e4f-9898-19f2d518ad1a
ms.openlocfilehash: cd95d2331f9f178b916cf22ec4b1ead7d7c4a116
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824349"
---
# <a name="reading-xml-data-using-xpathdocument-and-xmldocument"></a>Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument
Es gibt zwei Möglichkeiten, wie ein XML-Dokument in einem <xref:System.Xml.XPath?displayProperty=nameWithType>-Namespace gelesen werden kann. Zum einem kann ein XML-Dokument mithilfe der schreibgeschützten <xref:System.Xml.XPath.XPathDocument>-Klasse und zum anderen mithilfe der editierbaren <xref:System.Xml.XmlDocument>-Klasse im <xref:System.Xml?displayProperty=nameWithType>-Namespace gelesen werden.  
  
## <a name="reading-xml-documents-using-the-xpathdocument-class"></a>Lesen von XML-Dokumenten mithilfe der XPathDocument-Klasse  
 Die <xref:System.Xml.XPath.XPathDocument>-Klasse bietet eine schnelle, schreibgeschützte Darstellung eines XML-Dokuments im Speicher mithilfe des XPath-Datenmodells. Instanzen der <xref:System.Xml.XPath.XPathDocument>-Klasse werden mithilfe einer ihrer sechs Konstruktoren erstellt. Diese Konstruktoren ermöglichen das Lesen eines XML-Dokuments mithilfe eines der Objekte <xref:System.IO.Stream>, <xref:System.IO.TextReader> oder <xref:System.Xml.XmlReader> sowie des `string`-Pfads zu einer XML-Datei.  
  
 Im folgenden Beispiel wird die Verwendung des <xref:System.Xml.XPath.XPathDocument>-Konstruktors der `string`-Klasse zum Lesen eines XML-Dokuments veranschaulicht.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
```  
  
## <a name="reading-xml-documents-using-the-xmldocument-class"></a>Lesen von XML-Dokumenten mithilfe der XmlDocument-Klasse  
 Die <xref:System.Xml.XmlDocument>-Klasse ist eine editierbare speicherresidente Darstellung eines XML-Dokuments, die das DOM Level 1 Core und das DOM Level 2 Core des W3C implementiert. Instanzen der <xref:System.Xml.XmlDocument>-Klasse werden mithilfe einer ihrer drei Konstruktoren erstellt. Sie können ein neues, leeres <xref:System.Xml.XmlDocument>-Objekt erstellen, indem Sie den Konstruktor der <xref:System.Xml.XmlDocument>-Klasse ohne Parameter aufrufen. Verwenden Sie nach dem Aufrufen des Konstruktors die <xref:System.Xml.XmlDocument.Load%2A>-Methode, um XML-Daten aus einem der Objekte <xref:System.Xml.XmlDocument>, <xref:System.IO.Stream> oder <xref:System.IO.TextReader> sowie aus dem <xref:System.Xml.XmlReader>-Pfad zu einer XML-Datei in das neue `string`-Objekt zu laden.  
  
 Im folgenden Beispiel wird die Verwendung des Konstruktors der <xref:System.Xml.XmlDocument>-Klasse ohne Parameter und die Verwendung der <xref:System.Xml.XmlDocument.Load%2A>-Methode zum Lesen eines XML-Dokuments veranschaulicht.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
```  
  
## <a name="determining-the-encoding-of-an-xml-document"></a>Bestimmen der Codierung eines XML-Dokuments  
 Ein <xref:System.Xml.XmlReader>-Objekt kann, wie in den vorangehenden Abschnitten dargestellt, zum Lesen eines XML-Dokuments und zum Erstellen eines <xref:System.Xml.XPath.XPathDocument>-Objekts und eines <xref:System.Xml.XmlDocument>-Objekts verwendet werden. Ein <xref:System.Xml.XmlReader>-Objekt liest jedoch u. U. nicht codierte Daten und stellt folglich keine Codierungsinformationen bereit.  
  
 Die <xref:System.Xml.XmlTextReader>-Klasse erbt von der <xref:System.Xml.XmlReader>-Klasse, stellt mithilfe ihrer <xref:System.Xml.XmlTextReader.Encoding%2A>-Eigenschaft Codierungsinformationen bereit und kann zum Erstellen eines <xref:System.Xml.XPath.XPathDocument>-Objekts oder eines <xref:System.Xml.XmlDocument>-Objekts verwendet werden.  
  
 Weitere Informationen über die von der <xref:System.Xml.XmlTextReader>-Klasse bereitgestellten Codierungsinformationen finden Sie unter der <xref:System.Xml.XmlTextReader.Encoding%2A>-Eigenschaft in der Referenzdokumentation der <xref:System.Xml.XmlTextReader>-Klasse.  
  
## <a name="creating-xpathnavigator-objects"></a>Erstellen von XPathNavigator-Objekten  
 Nachdem Sie ein XML-Dokument in ein <xref:System.Xml.XPath.XPathDocument>-Objekt oder ein <xref:System.Xml.XmlDocument>-Objekt gelesen haben, können Sie ein <xref:System.Xml.XPath.XPathNavigator>-Objekt zum Auswählen, Auswerten, Navigieren und in einigen Fällen zum Bearbeiten der zugrunde liegenden XML-Daten erstellen.  
  
 Zusätzlich zur <xref:System.Xml.XPath.XPathDocument>-Klasse implementieren sowohl die <xref:System.Xml.XmlDocument>-Klasse als auch die <xref:System.Xml.XmlNode>-Klasse die <xref:System.Xml.XPath.IXPathNavigable>-Schnittstelle des <xref:System.Xml.XPath?displayProperty=nameWithType>-Namespaces. Folglich stellen alle drei Klassen eine <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A>-Methode bereit, die ein <xref:System.Xml.XPath.XPathNavigator>-Objekt zurückgibt.  
  
### <a name="editing-xml-documents-using-the-xpathnavigator-class"></a>Bearbeiten von XML-Dokumenten mithilfe der XPathNavigator-Klasse  
 Zusätzlich zum Auswählen, Auswerten und Navigieren von XML-Daten kann die <xref:System.Xml.XPath.XPathNavigator>-Klasse in einigen Fällen auch zum Bearbeiten eines XML-Dokuments anhand des Objekts, mit dem es erstellt wurde, verwendet werden.  
  
 Die <xref:System.Xml.XPath.XPathDocument>-Klasse ist schreibgeschützt, während die <xref:System.Xml.XmlDocument>-Klasse bearbeitet werden kann. Daher können <xref:System.Xml.XPath.XPathNavigator>-Objekte, die auf der Grundlage eines <xref:System.Xml.XPath.XPathDocument>-Objekts erstellt wurden, nicht zur Verarbeitung eines XML-Dokuments verwendet werden, während Objekte, die auf der Grundlage eines <xref:System.Xml.XmlDocument>-Objekts erstellt wurden, für die Verarbeitung von XML-Dokumenten eingesetzt werden können. Die <xref:System.Xml.XPath.XPathDocument>-Klasse sollte nur zum Lesen von XML-Dokumenten verwendet werden. In Fällen, bei denen Sie ein XML-Dokument bearbeiten müssen oder Zugriff auf zusätzliche Funktionen benötigen, die von der <xref:System.Xml.XmlDocument>-Klasse bereitgestellt werden (z. B. Ereignisbehandlung), sollten Sie die <xref:System.Xml.XmlDocument>-Klasse verwenden.  
  
 Die <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse gibt an, ob ein <xref:System.Xml.XPath.XPathNavigator>-Objekt XML-Daten bearbeiten kann.  
  
 In der folgenden Tabelle wird der Wert der <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Eigenschaft für jede Klasse beschrieben.  
  
|<xref:System.Xml.XPath.IXPathNavigable>-Implementierung|<xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Wert|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Xml.XPath.XPathDocument>|`false`|  
|<xref:System.Xml.XmlDocument>|`true`|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](process-xml-data-using-the-xpath-data-model.md)
- [Zugreifen auf XML-Daten mit XPathNavigator](accessing-xml-data-using-xpathnavigator.md)
- [Bearbeiten von XML-Daten mit XPathNavigator](editing-xml-data-using-xpathnavigator.md)
- [Schemavalidierung mithilfe von „XPathNavigator“](schema-validation-using-xpathnavigator.md)
