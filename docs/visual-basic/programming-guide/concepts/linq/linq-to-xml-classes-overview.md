---
title: "LINQ to XML-Klassen (Übersicht) (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: f11b62b5-d522-4c23-92ae-23186dc16447
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 12885f93bb7e56dd66d36090d41700195313e944
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-classes-overview-visual-basic"></a>LINQ to XML-Klassen (Übersicht) (Visual Basic)
Dieses Thema enthält eine Liste der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Klassen in der <xref:System.Xml.Linq>-Namespace und eine kurze Beschreibung der einzelnen.</xref:System.Xml.Linq>  
  
## <a name="linq-to-xml-classes"></a>LINQ to XML-Klassen  
  
### <a name="xattribute-class"></a>"XAttribute"-Klasse  
 <xref:System.Xml.Linq.XAttribute>Stellt ein XML-Attribut.</xref:System.Xml.Linq.XAttribute> Ausführliche Informationen und Beispiele finden Sie unter [Übersicht über XAttribute-Klasse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md).  
  
### <a name="xcdata-class"></a>"XCData"-Klasse  
 <xref:System.Xml.Linq.XCData>Stellt einen CDATA-Textknoten dar.</xref:System.Xml.Linq.XCData>  
  
### <a name="xcomment-class"></a>"XComment"-Klasse  
 <xref:System.Xml.Linq.XComment>Stellt einen XML-Kommentar dar.</xref:System.Xml.Linq.XComment>  
  
### <a name="xcontainer-class"></a>"XContainer"-Klasse  
 <xref:System.Xml.Linq.XContainer>ist eine abstrakte Basisklasse für alle Knoten, die untergeordnete Knoten besitzen dürfen.</xref:System.Xml.Linq.XContainer> Die folgenden Klassen leiten sich von der <xref:System.Xml.Linq.XContainer>Klasse:</xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XElement>  
  
-   <xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a>XDeclaration-Klasse  
 <xref:System.Xml.Linq.XDeclaration>Stellt eine XML-Deklaration dar.</xref:System.Xml.Linq.XDeclaration> XML-Deklarationen werden zum Deklarieren der XML-Version und zum Codieren von Dokumenten verwendet. Außerdem geben XML-Deklarationen an, ob das XML-Dokument eigenständig ist. Wenn ein Dokument eigenständig ist, sind keine externen Markupdeklarationen vorhanden (weder in einer externen DTD, noch in einer externen Parameterentität, auf die von der internen Teilmenge aus verwiesen wird).  
  
### <a name="xdocument-class"></a>"XDocument"-Klasse  
 <xref:System.Xml.Linq.XDocument>Stellt ein XML-Dokument dar.</xref:System.Xml.Linq.XDocument> Ausführliche Informationen und Beispiele finden Sie unter [Übersicht über das XDocument-Klasse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
### <a name="xdocumenttype-class"></a>"XDocumentType"-Klasse  
 <xref:System.Xml.Linq.XDocumentType>Stellt eine XML-Dokumenttypdefinition (DTD) dar.</xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xelement-class"></a>"XElement"-Klasse  
 <xref:System.Xml.Linq.XElement>Stellt ein XML-Element.</xref:System.Xml.Linq.XElement> Ausführliche Informationen und Beispiele finden Sie unter [Übersicht über das XElement-Klasse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md).  
  
### <a name="xname-class"></a>"XName"-Klasse  
 <xref:System.Xml.Linq.XName>stellt Namen von Elementen (<xref:System.Xml.Linq.XElement>) und Attribute (<xref:System.Xml.Linq.XAttribute>).</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XName> Ausführliche Informationen und Beispiele finden Sie unter [Übersicht über das XDocument-Klasse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
 Bei der Entwicklung von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] wurde auf einen möglichst einfachen Umgang mit XML-Namen Wert gelegt. Aufgrund ihrer Komplexität werden XML-Namen in XML oft als Angelegenheit für Fortgeschrittene betrachtet. Ursache dieser Komplexität sind aber nicht die von den Entwicklern regelmäßig beim Programmieren verwendeten Namespaces, sondern die Namespacepräfixe. Namespace-Präfixe kann nützlich, die Tastatureingaben erforderlich, wenn Sie die XML-Eingabe zu reduzieren oder um XML leichter lesbar zu machen. Präfixe sind jedoch häufig nur eine Verknüpfung zur Verwendung des vollständigen XML-Namespace und in den meisten Fällen nicht erforderlich. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]XML-Namen einfacher, indem alle Präfixe in ihren entsprechenden XML-Namespace aufgelöst. Präfixe sind verfügbar, wenn erforderlich, durch die <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>-Methode.</xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>  
  
 Bei Bedarf ist es möglich, Namespacepräfixe zu steuern. Eine solche Steuerung von Namespacepräfixen ist z. B. dann erforderlich, wenn Sie mit anderen XML-Systemen, wie XSLT oder XAML, arbeiten. Wenn Sie beispielsweise einen XPath-Ausdruck verwenden, der Namespacepräfixe verwendet und in ein XSLT-Stylesheet eingebettet ist, müssen Sie sicherstellen, dass Ihr XML-Dokument mit Namespacepräfixen serialisiert wird, die den im XPath-Ausdruck verwendeten Namespacepräfixen entsprechen.  
  
### <a name="xnamespace-class"></a>"XNamespace"-Klasse  
 <xref:System.Xml.Linq.XNamespace>Stellt einen Namespace für ein <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XNamespace> Namespaces sind eine Komponente von einer <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName>  
  
### <a name="xnode-class"></a>"XNode"-Klasse  
 <xref:System.Xml.Linq.XNode>ist eine abstrakte Klasse, die die Knoten einer XML-Struktur darstellt.</xref:System.Xml.Linq.XNode> Die folgenden Klassen leiten sich von der <xref:System.Xml.Linq.XNode>Klasse:</xref:System.Xml.Linq.XNode>  
  
-   <xref:System.Xml.Linq.XText></xref:System.Xml.Linq.XText>  
  
-   <xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment>  
  
-   <xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction>  
  
-   <xref:System.Xml.Linq.XDocumentType></xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a>"XNodeDocumentOrderComparer"-Klasse  
 <xref:System.Xml.Linq.XNodeDocumentOrderComparer>bietet Funktionen zum Vergleichen von Knoten anhand ihrer Dokumentreihenfolge.</xref:System.Xml.Linq.XNodeDocumentOrderComparer>  
  
### <a name="xnodeequalitycomparer-class"></a>"XNodeEqualityComparer"-Klasse  
 <xref:System.Xml.Linq.XNodeEqualityComparer>Stellt Funktionen zur Knoten auf Wertgleichheit vergleichen.</xref:System.Xml.Linq.XNodeEqualityComparer>  
  
### <a name="xobject-class"></a>"XObject"-Klasse  
 <xref:System.Xml.Linq.XObject>ist eine abstrakte Basisklasse von <xref:System.Xml.Linq.XNode>und <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XObject> Sie stellt Anmerkungs- und Ereignisfunktionen bereit.  
  
### <a name="xobjectchange-class"></a>"XObjectChange"-Klasse  
 <xref:System.Xml.Linq.XObjectChange>Gibt den Ereignistyp beim Auslösen eines Ereignisses für eine <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></xref:System.Xml.Linq.XObjectChange>  
  
### <a name="xobjectchangeeventargs-class"></a>"XObjectChangeEventArgs"-Klasse  
 <xref:System.Xml.Linq.XObjectChangeEventArgs>Stellt Daten für die <xref:System.Xml.Linq.XObject.Changing>und <xref:System.Xml.Linq.XObject.Changed>Ereignisse.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing></xref:System.Xml.Linq.XObjectChangeEventArgs>  
  
### <a name="xprocessinginstruction-class"></a>XProcessingInstruction-Klasse  
 <xref:System.Xml.Linq.XProcessingInstruction>Stellt eine XML-verarbeitungsanweisung dar.</xref:System.Xml.Linq.XProcessingInstruction> Eine Verarbeitungsanweisung stellt der Anwendung, die das XML-Dokument verarbeitet, entsprechende Informationen zur Verarbeitung bereit.  
  
### <a name="xtext-class"></a>"XText"-Klasse  
 <xref:System.Xml.Linq.XText>Stellt einen Textknoten dar.</xref:System.Xml.Linq.XText> Diese Klasse muss in den meisten Fällen nicht verwendet werden. Sie wird hauptsächlich für gemischten Inhalt eingesetzt.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML-Programmierung (Übersicht) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
