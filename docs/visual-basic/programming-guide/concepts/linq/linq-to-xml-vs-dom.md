---
title: LINQ to XML im Vergleich zu DOM (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 18c36130-d598-40b7-9007-828232252978
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 73aef4ddf4b53297e31d9b8b763dc1cafbef5170
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-xml-vs-dom-visual-basic"></a><span data-ttu-id="b955e-102">LINQ to XML im Vergleich zu DOM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b955e-102">LINQ to XML vs. DOM (Visual Basic)</span></span>
<span data-ttu-id="b955e-103">Dieser Abschnitt beschreibt einige wichtige Unterschiede zwischen [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] und die aktuelle verbreitetsten XML-Programmier-API, die W3C Document Objekt Model (DOM).</span><span class="sxs-lookup"><span data-stu-id="b955e-103">This section describes some key differences between [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] and the current predominant XML programming API, the W3C Document Object Model (DOM).</span></span>  
  
## <a name="new-ways-to-construct-xml-trees"></a><span data-ttu-id="b955e-104">Neue Möglichkeiten zum Konstruieren von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="b955e-104">New Ways to Construct XML Trees</span></span>  
 <span data-ttu-id="b955e-105">Im W3C-DOM erstellen Sie eine XML-Struktur von unten nach oben. Das bedeutet, Sie erstellen ein Dokument, Sie erstellen Elemente, und anschließend fügen Sie die Elemente dem Dokument hinzu.</span><span class="sxs-lookup"><span data-stu-id="b955e-105">In the W3C DOM, you build an XML tree from the bottom up; that is, you create a document, you create elements, and then you add the elements to the document.</span></span>  
  
 <span data-ttu-id="b955e-106">Z. B. wäre Folgendes ein übliches Verfahren zum Erstellen einer XML-Struktur, die mit der Microsoft-Implementierung des DOM, <xref:System.Xml.XmlDocument>:</xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="b955e-106">For example, the following would be a typical way to create an XML tree using the Microsoft implementation of DOM, <xref:System.Xml.XmlDocument>:</span></span>  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
Dim phone1 As XmlElement = doc.CreateElement("Phone")  
phone1.SetAttribute("Type", "Home")  
phone1.InnerText = "206-555-0144"  
Dim phone2 As XmlElement = doc.CreateElement("Phone")  
phone2.SetAttribute("Type", "Work")  
phone2.InnerText = "425-555-0145"  
Dim street1 As XmlElement = doc.CreateElement("Street1")  
street1.InnerText = "123 Main St"  
Dim city As XmlElement = doc.CreateElement("City")  
city.InnerText = "Mercer Island"  
Dim state As XmlElement = doc.CreateElement("State")  
state.InnerText = "WA"  
Dim postal As XmlElement = doc.CreateElement("Postal")  
postal.InnerText = "68042"  
Dim address As XmlElement = doc.CreateElement("Address")  
address.AppendChild(street1)  
address.AppendChild(city)  
address.AppendChild(state)  
address.AppendChild(postal)  
Dim contact As XmlElement = doc.CreateElement("Contact")  
contact.AppendChild(name)  
contact.AppendChild(phone1)  
contact.AppendChild(phone2)  
contact.AppendChild(address)  
Dim contacts As XmlElement = doc.CreateElement("Contacts")  
contacts.AppendChild(contact)  
doc.AppendChild(contacts)  
Console.WriteLine(doc.OuterXml)  
```  
  
 <span data-ttu-id="b955e-107">Dieses Format der Codierung liefert keine ausführlichen visuellen Informationen zum Aufbau der XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="b955e-107">This style of coding does not visually provide much information about the structure of the XML tree.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b955e-108">unterstützt diese Möglichkeit zum Konstruieren einer XML-Struktur, aber auch einen alternativen Ansatz, *funktionale Konstruktion*.</span><span class="sxs-lookup"><span data-stu-id="b955e-108"> supports this approach to constructing an XML tree, but also supports an alternative approach, *functional construction*.</span></span> <span data-ttu-id="b955e-109">In Visual Basic verwendet die funktionaler Konstruktion XML-Literale zum Erstellen einer XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="b955e-109">In Visual Basic, functional construction uses XML literals to build an XML tree.</span></span>  
  
 <span data-ttu-id="b955e-110">Hier ist, wie Sie mithilfe die gleiche XML-Struktur erstellen würde [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] funktionale Konstruktion:</span><span class="sxs-lookup"><span data-stu-id="b955e-110">Here is how you would construct the same XML tree by using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] functional construction:</span></span>  
  
```vb  
Dim contacts = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="Home">206-555-0144</Phone>  
            <Phone Type="Work">425-555-0145</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 <span data-ttu-id="b955e-111">Die Codeeinzüge verdeutlichen den Aufbau des der XML-Struktur zugrunde liegenden XML-Codes.</span><span class="sxs-lookup"><span data-stu-id="b955e-111">Notice that indenting the code to construct the XML tree shows the structure of the underlying XML.</span></span>  
  
 <span data-ttu-id="b955e-112">Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="b955e-112">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="working-directly-with-xml-elements"></a><span data-ttu-id="b955e-113">Direktes Arbeiten mit XML-Elementen</span><span class="sxs-lookup"><span data-stu-id="b955e-113">Working Directly with XML Elements</span></span>  
 <span data-ttu-id="b955e-114">Beim Programmieren mit XML liegt Ihr Hauptaugenmerk in der Regel auf XML-Elementen und vielleicht auch auf Attributen.</span><span class="sxs-lookup"><span data-stu-id="b955e-114">When you program with XML, your primary focus is usually on XML elements and perhaps on attributes.</span></span> <span data-ttu-id="b955e-115">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie direkt mit XML-Elementen und Attributen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="b955e-115">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you can work directly with XML elements and attributes.</span></span> <span data-ttu-id="b955e-116">So können Sie z. B. Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="b955e-116">For example, you can do the following:</span></span>  
  
-   <span data-ttu-id="b955e-117">Sie können XML-Elemente ohne jegliche Verwendung eines Dokumentobjekts erstellen.</span><span class="sxs-lookup"><span data-stu-id="b955e-117">Create XML elements without using a document object at all.</span></span> <span data-ttu-id="b955e-118">Dies vereinfacht beim Arbeiten mit Fragmenten von XML-Strukturen die Programmierung.</span><span class="sxs-lookup"><span data-stu-id="b955e-118">This simplifies programming when you have to work with fragments of XML trees.</span></span>  
  
-   <span data-ttu-id="b955e-119">Sie können `T:System.Xml.Linq.XElement`-Objekte direkt aus einer XML-Datei laden.</span><span class="sxs-lookup"><span data-stu-id="b955e-119">Load `T:System.Xml.Linq.XElement` objects directly from an XML file.</span></span>  
  
-   <span data-ttu-id="b955e-120">Sie können `T:System.Xml.Linq.XElement`-Objekte in eine Datei oder einen Stream serialisieren.</span><span class="sxs-lookup"><span data-stu-id="b955e-120">Serialize `T:System.Xml.Linq.XElement` objects to a file or a stream.</span></span>  
  
 <span data-ttu-id="b955e-121">Vergleichen Sie dies mit dem W3C-DOM, bei dem das XML-Dokument als logischer Container für die XML-Struktur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b955e-121">Compare this to the W3C DOM, in which the XML document is used as a logical container for the XML tree.</span></span> <span data-ttu-id="b955e-122">Im DOM müssen die XML-Knoten einschließlich der Elemente und Attribute im Kontext eines XML-Dokuments erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b955e-122">In DOM, XML nodes, including elements and attributes, must be created in the context of an XML document.</span></span> <span data-ttu-id="b955e-123">Das folgende Codefragment erstellt ein Namenselement im DOM:</span><span class="sxs-lookup"><span data-stu-id="b955e-123">Here is a fragment of the code to create a name element in DOM:</span></span>  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
doc.AppendChild(name)  
```  
  
 <span data-ttu-id="b955e-124">Wenn Sie ein Element in mehreren Dokumenten verwenden möchten, müssen Sie die Knoten dokumentübergreifend importieren.</span><span class="sxs-lookup"><span data-stu-id="b955e-124">If you want to use an element across multiple documents, you must import the nodes across documents.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b955e-125">vermeidet diese Ebene der Komplexität.</span><span class="sxs-lookup"><span data-stu-id="b955e-125"> avoids this layer of complexity.</span></span>  
  
 <span data-ttu-id="b955e-126">Wenn Sie LINQ to XML verwenden, verwenden Sie die <xref:System.Xml.Linq.XDocument>-Klasse nur, wenn Sie auf der Stammebene des Dokuments einen Kommentar oder eine verarbeitungsanweisung hinzufügen möchten.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="b955e-126">When using LINQ to XML, you use the <xref:System.Xml.Linq.XDocument> class only if you want to add a comment or processing instruction at the root level of the document.</span></span>  
  
## <a name="simplified-handling-of-names-and-namespaces"></a><span data-ttu-id="b955e-127">Vereinfachte Handhabung von Namen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="b955e-127">Simplified Handling of Names and Namespaces</span></span>  
 <span data-ttu-id="b955e-128">Die Handhabung von Namen, Namespaces und Namespacepräfixen ist im Allgemeinen ein komplexer Teil der XML-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="b955e-128">Handling names, namespaces, and namespace prefixes is generally a complex part of XML programming.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b955e-129">vereinfacht Namen und Namespaces Gerätetreiberschnittstellen einzufügen, die Anforderung für den Umgang mit Namespacepräfixen.</span><span class="sxs-lookup"><span data-stu-id="b955e-129"> simplifies names and namespaces by eliminating the requirement to deal with namespace prefixes.</span></span> <span data-ttu-id="b955e-130">Das heißt aber nicht, dass Sie die Namespacepräfixe nicht mehr selbst steuern können.</span><span class="sxs-lookup"><span data-stu-id="b955e-130">If you want to control namespace prefixes, you can.</span></span> <span data-ttu-id="b955e-131">Aber wenn Sie sich entscheiden, nicht explizit steuern von Namespacepräfixen [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] weist Namespacepräfixe während der Serialisierung erforderlich sind, oder wird die Serialisierung Standardnamespaces sind.</span><span class="sxs-lookup"><span data-stu-id="b955e-131">But if you decide to not explicitly control namespace prefixes, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] will assign namespace prefixes during serialization if they are required, or will serialize using default namespaces if they are not.</span></span> <span data-ttu-id="b955e-132">Wenn Standardnamespaces verwendet werden, gibt es im resultierenden Dokument keine Namespacepräfixe.</span><span class="sxs-lookup"><span data-stu-id="b955e-132">If default namespaces are used, there will be no namespace prefixes in the resulting document.</span></span> <span data-ttu-id="b955e-133">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="b955e-133">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="b955e-134">Ein anderes Problem mit dem DOM besteht darin, dass es keine Änderung des Namens eines Knotens zulässt.</span><span class="sxs-lookup"><span data-stu-id="b955e-134">Another problem with the DOM is that it does not let you change the name of a node.</span></span> <span data-ttu-id="b955e-135">Stattdessen müssen Sie einen neuen Knoten erstellen und alle untergeordneten Knoten kopieren, sodass die ursprüngliche Knotenidentität verloren geht.</span><span class="sxs-lookup"><span data-stu-id="b955e-135">Instead, you have to create a new node and copy all the child nodes to it, losing the original node identity.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b955e-136">vermeidet dieses Problem durch die Möglichkeit zum Festlegen der <xref:System.Xml.Linq.XName>Eigenschaft auf einem Knoten.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="b955e-136"> avoids this problem by enabling you to set the <xref:System.Xml.Linq.XName> property on a node.</span></span>  
  
## <a name="static-method-support-for-loading-xml"></a><span data-ttu-id="b955e-137">Unterstützung statischer Methoden für das Laden von XML</span><span class="sxs-lookup"><span data-stu-id="b955e-137">Static Method Support for Loading XML</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b955e-138">Sie können XML zu laden, indem Sie anstelle von Instanzmethoden statische Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="b955e-138"> lets you load XML by using static methods, instead of instance methods.</span></span> <span data-ttu-id="b955e-139">Dadurch vereinfacht sich das Laden und das Analysieren.</span><span class="sxs-lookup"><span data-stu-id="b955e-139">This simplifies loading and parsing.</span></span> <span data-ttu-id="b955e-140">Weitere Informationen finden Sie unter [Gewusst wie: Laden von XML aus einer Datei (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="b955e-140">For more information, see [How to: Load XML from a File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md).</span></span>  
  
## <a name="removal-of-support-for-dtd-constructs"></a><span data-ttu-id="b955e-141">Entfernung der Unterstützung für DTD-Konstrukte</span><span class="sxs-lookup"><span data-stu-id="b955e-141">Removal of Support for DTD Constructs</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b955e-142"> vereinfacht die XML-Programmierung zusätzlich, indem die Unterstützung für Entitäten und Entitätsverweise entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="b955e-142"> further simplifies XML programming by removing support for entities and entity references.</span></span> <span data-ttu-id="b955e-143">Die Verwaltung von Entitäten ist komplex und wird selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="b955e-143">The management of entities is complex, and is rarely used.</span></span> <span data-ttu-id="b955e-144">Durch das Entfernen dieser Unterstützung wird die Leistung verbessert und die Programmierung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="b955e-144">Removing their support increases performance and simplifies the programming interface.</span></span> <span data-ttu-id="b955e-145">Wenn eine [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Struktur aufgefüllt wird, werden alle DTD-Entitäten erweitert.</span><span class="sxs-lookup"><span data-stu-id="b955e-145">When a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] tree is populated, all DTD entities are expanded.</span></span>  
  
## <a name="support-for-fragments"></a><span data-ttu-id="b955e-146">Unterstützung für Fragmente</span><span class="sxs-lookup"><span data-stu-id="b955e-146">Support for Fragments</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b955e-147">bietet keine Entsprechung für die `XmlDocumentFragment` Klasse.</span><span class="sxs-lookup"><span data-stu-id="b955e-147"> does not provide an equivalent for the `XmlDocumentFragment` class.</span></span> <span data-ttu-id="b955e-148">In vielen Fällen jedoch die `XmlDocumentFragment` Konzept behandelt werden kann, durch das Ergebnis einer Abfrage, die typisiert wird <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XNode>, oder <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XNode> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="b955e-148">In many cases, however, the `XmlDocumentFragment` concept can be handled by the result of a query that is typed as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XNode>, or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="support-for-xpathnavigator"></a><span data-ttu-id="b955e-149">Unterstützung für XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="b955e-149">Support for XPathNavigator</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b955e-150">bietet Unterstützung für <xref:System.Xml.XPath.XPathNavigator>durch Erweiterungsmethoden in den <xref:System.Xml.XPath?displayProperty=fullName>Namespace.</xref:System.Xml.XPath?displayProperty=fullName> </xref:System.Xml.XPath.XPathNavigator></span><span class="sxs-lookup"><span data-stu-id="b955e-150"> provides support for <xref:System.Xml.XPath.XPathNavigator> through extension methods in the <xref:System.Xml.XPath?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="b955e-151">Weitere Informationen finden Sie unter <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</xref:System.Xml.XPath.Extensions?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b955e-151">For more information, see <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</span></span>  
  
## <a name="support-for-white-space-and-indentation"></a><span data-ttu-id="b955e-152">Unterstützung für Leerraum und Einzüge</span><span class="sxs-lookup"><span data-stu-id="b955e-152">Support for White Space and Indentation</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b955e-153">handhabt Leerzeichen einfacher als das DOM.</span><span class="sxs-lookup"><span data-stu-id="b955e-153"> handles white space more simply than the DOM.</span></span>  
  
 <span data-ttu-id="b955e-154">Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b955e-154">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="b955e-155">Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten.</span><span class="sxs-lookup"><span data-stu-id="b955e-155">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="b955e-156">Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="b955e-156">This is the default behavior for [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="b955e-157">Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert.</span><span class="sxs-lookup"><span data-stu-id="b955e-157">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="b955e-158">Sie möchten nicht, dass diese Einzüge irgendwie geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b955e-158">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="b955e-159">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b955e-159">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you can do this by preserving white space when you load or parse the XML and disabling formatting when you serialize the XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b955e-160">Speichert Leerraum als ein <xref:System.Xml.Linq.XText>-Knoten und kein speziellen <xref:System.Xml.XmlNodeType>Knotentyp, wie dies im DOM der Fall ist.</xref:System.Xml.XmlNodeType> </xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="b955e-160"> stores white space as an <xref:System.Xml.Linq.XText> node, instead of having a specialized <xref:System.Xml.XmlNodeType> node type, as the DOM does.</span></span>  
  
## <a name="support-for-annotations"></a><span data-ttu-id="b955e-161">Unterstützung für Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="b955e-161">Support for Annotations</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b955e-162">-Elemente unterstützen einen erweiterbaren Satz von Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="b955e-162"> elements support an extensible set of annotations.</span></span> <span data-ttu-id="b955e-163">Dies ist nützlich zum Nachverfolgen von verschiedene Informationen zu einem Element, z. B. Schemainformationen, Informationen, ob das Element an eine Benutzeroberfläche gebunden ist oder eine beliebige andere Art von anwendungsspezifischen Informationen.</span><span class="sxs-lookup"><span data-stu-id="b955e-163">This is useful for tracking miscellaneous information about an element, such as schema information, information about whether the element is bound to a UI, or any other kind of application-specific information.</span></span> <span data-ttu-id="b955e-164">Weitere Informationen finden Sie unter [LINQ to XML-Anmerkungen](http://msdn.microsoft.com/library/e2f0052d-61e2-48d4-9ea4-356c9cab35d5).</span><span class="sxs-lookup"><span data-stu-id="b955e-164">For more information, see [LINQ to XML Annotations](http://msdn.microsoft.com/library/e2f0052d-61e2-48d4-9ea4-356c9cab35d5).</span></span>  
  
## <a name="support-for-schema-information"></a><span data-ttu-id="b955e-165">Unterstützung für Schemainformationen</span><span class="sxs-lookup"><span data-stu-id="b955e-165">Support for Schema Information</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b955e-166">bietet Unterstützung für XSD-Validierung durch Erweiterungsmethoden in den <xref:System.Xml.Schema?displayProperty=fullName>Namespace.</xref:System.Xml.Schema?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b955e-166"> provides support for XSD validation through extension methods in the <xref:System.Xml.Schema?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="b955e-167">Sie können prüfen, ob sich eine XML-Struktur nach einer XSD richtet.</span><span class="sxs-lookup"><span data-stu-id="b955e-167">You can validate that an XML tree complies with an XSD.</span></span> <span data-ttu-id="b955e-168">Sie können die XML-Struktur mit dem Post-Schema-Validierungs-Infoset (PSVI) auffüllen.</span><span class="sxs-lookup"><span data-stu-id="b955e-168">You can populate the XML tree with the post-schema-validation infoset (PSVI).</span></span> <span data-ttu-id="b955e-169">Weitere Informationen finden Sie unter [Gewusst wie: Überprüfen Sie mithilfe von XSD](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b) und <xref:System.Xml.Schema.Extensions>.</xref:System.Xml.Schema.Extensions></span><span class="sxs-lookup"><span data-stu-id="b955e-169">For more information, see [How to: Validate Using XSD](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b) and <xref:System.Xml.Schema.Extensions>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b955e-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b955e-170">See Also</span></span>  
 [<span data-ttu-id="b955e-171">Erste Schritte (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="b955e-171">Getting Started (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
