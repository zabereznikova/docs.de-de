---
title: "Übersicht der LINQ to XML-Klassen (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bf666100-5392-4968-97f4-f6b9d3287d7b
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0dc4307c3cf87fa9b5cb38bdaa9d9bf77adf1424
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-classes-overview-c"></a><span data-ttu-id="216ed-102">Übersicht der LINQ to XML-Klassen (C#)</span><span class="sxs-lookup"><span data-stu-id="216ed-102">LINQ to XML Classes Overview (C#)</span></span>
<span data-ttu-id="216ed-103">In diesem Thema finden Sie eine Liste der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Klassen im <xref:System.Xml.Linq>-Namespace sowie jeweils eine kurze Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="216ed-103">This topic provides a list of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes in the <xref:System.Xml.Linq> namespace, and a short description of each.</span></span>  
  
## <a name="linq-to-xml-classes"></a><span data-ttu-id="216ed-104">LINQ to XML-Klassen</span><span class="sxs-lookup"><span data-stu-id="216ed-104">LINQ to XML Classes</span></span>  
  
### <a name="xattribute-class"></a><span data-ttu-id="216ed-105">"XAttribute"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-105">XAttribute Class</span></span>  
 <span data-ttu-id="216ed-106"><xref:System.Xml.Linq.XAttribute> stellt ein XML-Attribut dar.</span><span class="sxs-lookup"><span data-stu-id="216ed-106"><xref:System.Xml.Linq.XAttribute> represents an XML attribute.</span></span> <span data-ttu-id="216ed-107">Ausführliche Informationen und Beispiele finden Sie unter [XAttribute Class Overview (C#) (Übersicht über die XAttribute-Klasse (C#))](../../../../csharp/programming-guide/concepts/linq/xattribute-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="216ed-107">For detailed information and examples, see [XAttribute Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xattribute-class-overview.md).</span></span>  
  
### <a name="xcdata-class"></a><span data-ttu-id="216ed-108">"XCData"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-108">XCData Class</span></span>  
 <span data-ttu-id="216ed-109"><xref:System.Xml.Linq.XCData> stellt einen CDATA-Textknoten dar.</span><span class="sxs-lookup"><span data-stu-id="216ed-109"><xref:System.Xml.Linq.XCData> represents a CDATA text node.</span></span>  
  
### <a name="xcomment-class"></a><span data-ttu-id="216ed-110">"XComment"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-110">XComment Class</span></span>  
 <span data-ttu-id="216ed-111"><xref:System.Xml.Linq.XComment> stellt einen XML-Kommentar dar.</span><span class="sxs-lookup"><span data-stu-id="216ed-111"><xref:System.Xml.Linq.XComment> represents an XML comment.</span></span>  
  
### <a name="xcontainer-class"></a><span data-ttu-id="216ed-112">"XContainer"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-112">XContainer Class</span></span>  
 <span data-ttu-id="216ed-113"><xref:System.Xml.Linq.XContainer> ist eine abstrakte Basisklasse für alle Knoten, die untergeordnete Knoten besitzen dürfen.</span><span class="sxs-lookup"><span data-stu-id="216ed-113"><xref:System.Xml.Linq.XContainer> is an abstract base class for all nodes that can have child nodes.</span></span> <span data-ttu-id="216ed-114">Die folgenden Klassen leiten sich von der <xref:System.Xml.Linq.XContainer>-Klasse her:</span><span class="sxs-lookup"><span data-stu-id="216ed-114">The following classes derive from the <xref:System.Xml.Linq.XContainer> class:</span></span>  
  
-   <xref:System.Xml.Linq.XElement>  
  
-   <xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a><span data-ttu-id="216ed-115">"XDeclaration"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-115">XDeclaration Class</span></span>  
 <span data-ttu-id="216ed-116"><xref:System.Xml.Linq.XDeclaration> stellt eine XML-Deklaration dar.</span><span class="sxs-lookup"><span data-stu-id="216ed-116"><xref:System.Xml.Linq.XDeclaration> represents an XML declaration.</span></span> <span data-ttu-id="216ed-117">XML-Deklarationen werden zum Deklarieren der XML-Version und zum Codieren von Dokumenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="216ed-117">An XML declaration is used to declare the XML version and the encoding of a document.</span></span> <span data-ttu-id="216ed-118">Außerdem geben XML-Deklarationen an, ob das XML-Dokument eigenständig ist.</span><span class="sxs-lookup"><span data-stu-id="216ed-118">In addition, an XML declaration specifies whether the XML document is stand-alone.</span></span> <span data-ttu-id="216ed-119">Wenn ein Dokument eigenständig ist, sind keine externen Markupdeklarationen vorhanden (weder in einer externen DTD, noch in einer externen Parameterentität, auf die von der internen Teilmenge aus verwiesen wird).</span><span class="sxs-lookup"><span data-stu-id="216ed-119">If a document is stand-alone, there are no external markup declarations, either in an external DTD, or in an external parameter entity referenced from the internal subset.</span></span>  
  
### <a name="xdocument-class"></a><span data-ttu-id="216ed-120">"XDocument"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-120">XDocument Class</span></span>  
 <span data-ttu-id="216ed-121"><xref:System.Xml.Linq.XDocument> stellt ein XML-Dokument dar.</span><span class="sxs-lookup"><span data-stu-id="216ed-121"><xref:System.Xml.Linq.XDocument> represents an XML document.</span></span> <span data-ttu-id="216ed-122">Ausführliche Informationen und Beispiele finden Sie unter [XDocument Class Overview (C#) (Übersicht über die XDocument-Klasse (C#))](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="216ed-122">For detailed information and examples, see [XDocument Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
### <a name="xdocumenttype-class"></a><span data-ttu-id="216ed-123">"XDocumentType"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-123">XDocumentType Class</span></span>  
 <span data-ttu-id="216ed-124"><xref:System.Xml.Linq.XDocumentType> stellt eine XML-Dokumenttypdefinition (DTD) dar.</span><span class="sxs-lookup"><span data-stu-id="216ed-124"><xref:System.Xml.Linq.XDocumentType> represents an XML Document Type Definition (DTD).</span></span>  
  
### <a name="xelement-class"></a><span data-ttu-id="216ed-125">"XElement"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-125">XElement Class</span></span>  
 <span data-ttu-id="216ed-126"><xref:System.Xml.Linq.XElement> stellt ein XML-Element dar.</span><span class="sxs-lookup"><span data-stu-id="216ed-126"><xref:System.Xml.Linq.XElement> represents an XML element.</span></span> <span data-ttu-id="216ed-127">Ausführliche Informationen und Beispiele finden Sie unter [XElement Class Overview (C#) (Übersicht über die XElement-Klasse (C#))](../../../../csharp/programming-guide/concepts/linq/xelement-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="216ed-127">For detailed information and examples, see [XElement Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xelement-class-overview.md).</span></span>  
  
### <a name="xname-class"></a><span data-ttu-id="216ed-128">"XName"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-128">XName Class</span></span>  
 <span data-ttu-id="216ed-129"><xref:System.Xml.Linq.XName> stellt Namen von Elementen (<xref:System.Xml.Linq.XElement>) und Attributen (<xref:System.Xml.Linq.XAttribute>) dar.</span><span class="sxs-lookup"><span data-stu-id="216ed-129"><xref:System.Xml.Linq.XName> represents names of elements (<xref:System.Xml.Linq.XElement>) and attributes (<xref:System.Xml.Linq.XAttribute>).</span></span> <span data-ttu-id="216ed-130">Ausführliche Informationen und Beispiele finden Sie unter [XDocument Class Overview (C#) (Übersicht über die XDocument-Klasse (C#))](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="216ed-130">For detailed information and examples, see [XDocument Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
 <span data-ttu-id="216ed-131">Bei der Entwicklung von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] wurde auf einen möglichst einfachen Umgang mit XML-Namen Wert gelegt.</span><span class="sxs-lookup"><span data-stu-id="216ed-131">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is designed to make XML names as straightforward as possible.</span></span> <span data-ttu-id="216ed-132">Aufgrund ihrer Komplexität werden XML-Namen in XML oft als Angelegenheit für Fortgeschrittene betrachtet.</span><span class="sxs-lookup"><span data-stu-id="216ed-132">Due to their complexity, XML names are often considered to be an advanced topic in XML.</span></span> <span data-ttu-id="216ed-133">Ursache dieser Komplexität sind aber nicht die von den Entwicklern regelmäßig beim Programmieren verwendeten Namespaces, sondern die Namespacepräfixe.</span><span class="sxs-lookup"><span data-stu-id="216ed-133">Arguably, this complexity comes not from namespaces, which developers use regularly in programming, but from namespace prefixes.</span></span> <span data-ttu-id="216ed-134">Namespacepräfixe können helfen, die Anzahl der Tastaturanschläge zu verringern, die beim Eingeben von XML oder beim Bearbeiten von XML im Sinne einer besseren Lesbarkeit notwendig sind.</span><span class="sxs-lookup"><span data-stu-id="216ed-134">Namespace prefixes can be useful to reduce the keystrokes required when you input XML, or to make XML easier to read.</span></span> <span data-ttu-id="216ed-135">Präfixe sind jedoch häufig nur eine Verknüpfung zur Verwendung des vollständigen XML-Namespace und in den meisten Fällen nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="216ed-135">However, prefixes are often just a shortcut for using the full XML namespace, and are not required in most cases.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="216ed-136"> vereinfacht XML-Namen, indem alle Präfixe in ihren entsprechenden XML-Namespace aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="216ed-136"> simplifies XML names by resolving all prefixes to their corresponding XML namespace.</span></span> <span data-ttu-id="216ed-137">Wenn erforderlich, sind Präfixe über die <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>-Methode verfügbar.</span><span class="sxs-lookup"><span data-stu-id="216ed-137">Prefixes are available, if they are required, through the <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> method.</span></span>  
  
 <span data-ttu-id="216ed-138">Bei Bedarf ist es möglich, Namespacepräfixe zu steuern.</span><span class="sxs-lookup"><span data-stu-id="216ed-138">It is possible, if necessary, to control namespace prefixes.</span></span> <span data-ttu-id="216ed-139">Eine solche Steuerung von Namespacepräfixen ist z. B. dann erforderlich, wenn Sie mit anderen XML-Systemen, wie XSLT oder XAML, arbeiten.</span><span class="sxs-lookup"><span data-stu-id="216ed-139">In some circumstances, if you are working with other XML systems, such as XSLT or XAML, you need to control namespace prefixes.</span></span> <span data-ttu-id="216ed-140">Wenn Sie beispielsweise einen XPath-Ausdruck verwenden, der Namespacepräfixe verwendet und in ein XSLT-Stylesheet eingebettet ist, müssen Sie sicherstellen, dass Ihr XML-Dokument mit Namespacepräfixen serialisiert wird, die den im XPath-Ausdruck verwendeten Namespacepräfixen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="216ed-140">For example, if you have an XPath expression that uses namespace prefixes and is embedded in an XSLT stylesheet, you must make sure that your XML document is serialized with namespace prefixes that match those used in the XPath expression.</span></span>  
  
### <a name="xnamespace-class"></a><span data-ttu-id="216ed-141">"XNamespace"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-141">XNamespace Class</span></span>  
 <span data-ttu-id="216ed-142"><xref:System.Xml.Linq.XNamespace> stellt einen Namespace für ein <xref:System.Xml.Linq.XElement> oder ein <xref:System.Xml.Linq.XAttribute> dar.</span><span class="sxs-lookup"><span data-stu-id="216ed-142"><xref:System.Xml.Linq.XNamespace> represents a namespace for an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="216ed-143">Namespaces sind eine Komponente eines <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="216ed-143">Namespaces are a component of an <xref:System.Xml.Linq.XName>.</span></span>  
  
### <a name="xnode-class"></a><span data-ttu-id="216ed-144">"XNode"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-144">XNode Class</span></span>  
 <span data-ttu-id="216ed-145"><xref:System.Xml.Linq.XNode> ist eine abstrakte Klasse, die die Knoten einer XML-Struktur darstellt.</span><span class="sxs-lookup"><span data-stu-id="216ed-145"><xref:System.Xml.Linq.XNode> is an abstract class that represents the nodes of an XML tree.</span></span> <span data-ttu-id="216ed-146">Die folgenden Klassen leiten sich von der <xref:System.Xml.Linq.XNode>-Klasse her:</span><span class="sxs-lookup"><span data-stu-id="216ed-146">The following classes derive from the <xref:System.Xml.Linq.XNode> class:</span></span>  
  
-   <xref:System.Xml.Linq.XText>  
  
-   <xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XComment>  
  
-   <xref:System.Xml.Linq.XProcessingInstruction>  
  
-   <xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a><span data-ttu-id="216ed-147">"XNodeDocumentOrderComparer"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-147">XNodeDocumentOrderComparer Class</span></span>  
 <span data-ttu-id="216ed-148"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> ermöglicht das Vergleichen von Knoten anhand ihrer Dokumentreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="216ed-148"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> provides functionality to compare nodes for their document order.</span></span>  
  
### <a name="xnodeequalitycomparer-class"></a><span data-ttu-id="216ed-149">"XNodeEqualityComparer"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-149">XNodeEqualityComparer Class</span></span>  
 <span data-ttu-id="216ed-150"><xref:System.Xml.Linq.XNodeEqualityComparer> ermöglicht das Vergleichen von Knoten anhand ihrer Wertgleichheit.</span><span class="sxs-lookup"><span data-stu-id="216ed-150"><xref:System.Xml.Linq.XNodeEqualityComparer> provides functionality to compare nodes for value equality.</span></span>  
  
### <a name="xobject-class"></a><span data-ttu-id="216ed-151">"XObject"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-151">XObject Class</span></span>  
 <span data-ttu-id="216ed-152"><xref:System.Xml.Linq.XObject> ist eine abstrakte Basisklasse von <xref:System.Xml.Linq.XNode> und <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="216ed-152"><xref:System.Xml.Linq.XObject> is an abstract base class of <xref:System.Xml.Linq.XNode> and <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="216ed-153">Sie stellt Anmerkungs- und Ereignisfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="216ed-153">It provides annotation and event functionality.</span></span>  
  
### <a name="xobjectchange-class"></a><span data-ttu-id="216ed-154">"XObjectChange"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-154">XObjectChange Class</span></span>  
 <span data-ttu-id="216ed-155"><xref:System.Xml.Linq.XObjectChange> gibt den Ereignistyp an, wenn ein Ereignis für ein <xref:System.Xml.Linq.XObject> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="216ed-155"><xref:System.Xml.Linq.XObjectChange> specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>  
  
### <a name="xobjectchangeeventargs-class"></a><span data-ttu-id="216ed-156">"XObjectChangeEventArgs"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-156">XObjectChangeEventArgs Class</span></span>  
 <span data-ttu-id="216ed-157"><xref:System.Xml.Linq.XObjectChangeEventArgs> stellt Daten für die Ereignisse <xref:System.Xml.Linq.XObject.Changing> und <xref:System.Xml.Linq.XObject.Changed> bereit.</span><span class="sxs-lookup"><span data-stu-id="216ed-157"><xref:System.Xml.Linq.XObjectChangeEventArgs> provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>  
  
### <a name="xprocessinginstruction-class"></a><span data-ttu-id="216ed-158">"XProcessingInstruction"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-158">XProcessingInstruction Class</span></span>  
 <span data-ttu-id="216ed-159"><xref:System.Xml.Linq.XProcessingInstruction> stellt eine XML-Verarbeitungsanweisung dar.</span><span class="sxs-lookup"><span data-stu-id="216ed-159"><xref:System.Xml.Linq.XProcessingInstruction> represents an XML processing instruction.</span></span> <span data-ttu-id="216ed-160">Eine Verarbeitungsanweisung stellt der Anwendung, die das XML-Dokument verarbeitet, entsprechende Informationen zur Verarbeitung bereit.</span><span class="sxs-lookup"><span data-stu-id="216ed-160">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
### <a name="xtext-class"></a><span data-ttu-id="216ed-161">"XText"-Klasse</span><span class="sxs-lookup"><span data-stu-id="216ed-161">XText Class</span></span>  
 <span data-ttu-id="216ed-162"><xref:System.Xml.Linq.XText> stellt einen Textknoten dar.</span><span class="sxs-lookup"><span data-stu-id="216ed-162"><xref:System.Xml.Linq.XText> represents a text node.</span></span> <span data-ttu-id="216ed-163">Diese Klasse muss in den meisten Fällen nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="216ed-163">In most cases, you do not have to use this class.</span></span> <span data-ttu-id="216ed-164">Sie wird hauptsächlich für gemischten Inhalt eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="216ed-164">This class is primarily used for mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="216ed-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="216ed-165">See Also</span></span>  
 [<span data-ttu-id="216ed-166">LINQ to XML Programming Overview (C#) (Übersicht der LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="216ed-166">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
