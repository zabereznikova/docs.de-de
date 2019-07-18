---
title: LINQ to XML-Klassen-Übersicht (Visual Basic)
ms.date: 07/20/2015
ms.assetid: f11b62b5-d522-4c23-92ae-23186dc16447
ms.openlocfilehash: 10a6384167ee6ad6463a7f2f993b871fc8baea9e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610745"
---
# <a name="linq-to-xml-classes-overview-visual-basic"></a>LINQ to XML-Klassen-Übersicht (Visual Basic)
In diesem Thema finden Sie eine Liste der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Klassen im <xref:System.Xml.Linq>-Namespace sowie jeweils eine kurze Beschreibung.  
  
## <a name="linq-to-xml-classes"></a>LINQ to XML-Klassen  
  
### <a name="xattribute-class"></a>"XAttribute"-Klasse  
 <xref:System.Xml.Linq.XAttribute> stellt ein XML-Attribut dar. Ausführliche Informationen und Beispiele finden Sie unter [XAttribute Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md).  
  
### <a name="xcdata-class"></a>"XCData"-Klasse  
 <xref:System.Xml.Linq.XCData> stellt einen CDATA-Textknoten dar.  
  
### <a name="xcomment-class"></a>"XComment"-Klasse  
 <xref:System.Xml.Linq.XComment> stellt einen XML-Kommentar dar.  
  
### <a name="xcontainer-class"></a>"XContainer"-Klasse  
 <xref:System.Xml.Linq.XContainer> ist eine abstrakte Basisklasse für alle Knoten, die untergeordnete Knoten besitzen dürfen. Die folgenden Klassen leiten sich von der <xref:System.Xml.Linq.XContainer>-Klasse her:  
  
- <xref:System.Xml.Linq.XElement>  
  
- <xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a>XDeclaration-Klasse  
 <xref:System.Xml.Linq.XDeclaration> stellt eine XML-Deklaration dar. XML-Deklarationen werden zum Deklarieren der XML-Version und zum Codieren von Dokumenten verwendet. Außerdem geben XML-Deklarationen an, ob das XML-Dokument eigenständig ist. Wenn ein Dokument eigenständig ist, sind keine externen Markupdeklarationen vorhanden (weder in einer externen DTD, noch in einer externen Parameterentität, auf die von der internen Teilmenge aus verwiesen wird).  
  
### <a name="xdocument-class"></a>"XDocument"-Klasse  
 <xref:System.Xml.Linq.XDocument> stellt ein XML-Dokument dar. Ausführliche Informationen und Beispiele finden Sie unter [Übersicht über das XDocument-Klasse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
### <a name="xdocumenttype-class"></a>"XDocumentType"-Klasse  
 <xref:System.Xml.Linq.XDocumentType> stellt eine XML-Dokumenttypdefinition (DTD) dar.  
  
### <a name="xelement-class"></a>"XElement"-Klasse  
 <xref:System.Xml.Linq.XElement> stellt ein XML-Element dar. Ausführliche Informationen und Beispiele finden Sie unter [XElement Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md).  
  
### <a name="xname-class"></a>"XName"-Klasse  
 <xref:System.Xml.Linq.XName> stellt Namen von Elementen (<xref:System.Xml.Linq.XElement>) und Attributen (<xref:System.Xml.Linq.XAttribute>) dar. Ausführliche Informationen und Beispiele finden Sie unter [Übersicht über das XDocument-Klasse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
 Bei der Entwicklung von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] wurde auf einen möglichst einfachen Umgang mit XML-Namen Wert gelegt. Aufgrund ihrer Komplexität werden XML-Namen in XML oft als Angelegenheit für Fortgeschrittene betrachtet. Ursache dieser Komplexität sind aber nicht die von den Entwicklern regelmäßig beim Programmieren verwendeten Namespaces, sondern die Namespacepräfixe. Namespacepräfixe können helfen, die Anzahl der Tastaturanschläge zu verringern, die beim Eingeben von XML oder beim Bearbeiten von XML im Sinne einer besseren Lesbarkeit notwendig sind. Präfixe sind jedoch häufig nur eine Verknüpfung zur Verwendung des vollständigen XML-Namespace und in den meisten Fällen nicht erforderlich. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] vereinfacht XML-Namen, indem alle Präfixe in ihren entsprechenden XML-Namespace aufgelöst werden. Wenn erforderlich, sind Präfixe über die <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>-Methode verfügbar.  
  
 Bei Bedarf ist es möglich, Namespacepräfixe zu steuern. Eine solche Steuerung von Namespacepräfixen ist z. B. dann erforderlich, wenn Sie mit anderen XML-Systemen, wie XSLT oder XAML, arbeiten. Wenn Sie beispielsweise einen XPath-Ausdruck verwenden, der Namespacepräfixe verwendet und in ein XSLT-Stylesheet eingebettet ist, müssen Sie sicherstellen, dass Ihr XML-Dokument mit Namespacepräfixen serialisiert wird, die den im XPath-Ausdruck verwendeten Namespacepräfixen entsprechen.  
  
### <a name="xnamespace-class"></a>"XNamespace"-Klasse  
 <xref:System.Xml.Linq.XNamespace> stellt einen Namespace für ein <xref:System.Xml.Linq.XElement> oder ein <xref:System.Xml.Linq.XAttribute> dar. Namespaces sind eine Komponente eines <xref:System.Xml.Linq.XName>.  
  
### <a name="xnode-class"></a>"XNode"-Klasse  
 <xref:System.Xml.Linq.XNode> ist eine abstrakte Klasse, die die Knoten einer XML-Struktur darstellt. Die folgenden Klassen leiten sich von der <xref:System.Xml.Linq.XNode>-Klasse her:  
  
- <xref:System.Xml.Linq.XText>  
  
- <xref:System.Xml.Linq.XContainer>  
  
- <xref:System.Xml.Linq.XComment>  
  
- <xref:System.Xml.Linq.XProcessingInstruction>  
  
- <xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a>"XNodeDocumentOrderComparer"-Klasse  
 <xref:System.Xml.Linq.XNodeDocumentOrderComparer> ermöglicht das Vergleichen von Knoten anhand ihrer Dokumentreihenfolge.  
  
### <a name="xnodeequalitycomparer-class"></a>"XNodeEqualityComparer"-Klasse  
 <xref:System.Xml.Linq.XNodeEqualityComparer> ermöglicht das Vergleichen von Knoten anhand ihrer Wertgleichheit.  
  
### <a name="xobject-class"></a>"XObject"-Klasse  
 <xref:System.Xml.Linq.XObject> ist eine abstrakte Basisklasse von <xref:System.Xml.Linq.XNode> und <xref:System.Xml.Linq.XAttribute>. Sie stellt Anmerkungs- und Ereignisfunktionen bereit.  
  
### <a name="xobjectchange-class"></a>"XObjectChange"-Klasse  
 <xref:System.Xml.Linq.XObjectChange> gibt den Ereignistyp an, wenn ein Ereignis für ein <xref:System.Xml.Linq.XObject> ausgelöst wird.  
  
### <a name="xobjectchangeeventargs-class"></a>"XObjectChangeEventArgs"-Klasse  
 <xref:System.Xml.Linq.XObjectChangeEventArgs> stellt Daten für die Ereignisse <xref:System.Xml.Linq.XObject.Changing> und <xref:System.Xml.Linq.XObject.Changed> bereit.  
  
### <a name="xprocessinginstruction-class"></a>XProcessingInstruction-Klasse  
 <xref:System.Xml.Linq.XProcessingInstruction> stellt eine XML-Verarbeitungsanweisung dar. Eine Verarbeitungsanweisung stellt der Anwendung, die das XML-Dokument verarbeitet, entsprechende Informationen zur Verarbeitung bereit.  
  
### <a name="xtext-class"></a>"XText"-Klasse  
 <xref:System.Xml.Linq.XText> stellt einen Textknoten dar. Diese Klasse muss in den meisten Fällen nicht verwendet werden. Sie wird hauptsächlich für gemischten Inhalt eingesetzt.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML Programming Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
