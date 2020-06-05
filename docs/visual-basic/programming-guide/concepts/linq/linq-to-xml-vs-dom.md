---
title: LINQ to XML im Vergleich zu DOM
ms.date: 07/20/2015
ms.assetid: 18c36130-d598-40b7-9007-828232252978
ms.openlocfilehash: 5813ca410e3e2b1ec284681451d0c0cec6f5e393
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389331"
---
# <a name="linq-to-xml-vs-dom-visual-basic"></a><span data-ttu-id="e1888-102">LINQ to XML im Vergleich zu DOM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1888-102">LINQ to XML vs. DOM (Visual Basic)</span></span>
<span data-ttu-id="e1888-103">In diesem Abschnitt werden einige der wichtigsten Unterschiede zwischen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] und der derzeit verbreitetsten XML-Programmier-API, dem W3C-Dokumentobjektmodell (DOM), beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1888-103">This section describes some key differences between [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] and the current predominant XML programming API, the W3C Document Object Model (DOM).</span></span>  
  
## <a name="new-ways-to-construct-xml-trees"></a><span data-ttu-id="e1888-104">Neue Möglichkeiten zum Konstruieren von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="e1888-104">New Ways to Construct XML Trees</span></span>  
 <span data-ttu-id="e1888-105">Im W3C-DOM erstellen Sie eine XML-Struktur von unten nach oben. Das bedeutet, Sie erstellen ein Dokument, Sie erstellen Elemente, und anschließend fügen Sie die Elemente dem Dokument hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1888-105">In the W3C DOM, you build an XML tree from the bottom up; that is, you create a document, you create elements, and then you add the elements to the document.</span></span>  
  
 <span data-ttu-id="e1888-106">Das folgende Beispiel zeigt eine typische Herangehensweise an das Erstellen einer XML-Struktur mit der Microsoft-Implementierung des DOM, <xref:System.Xml.XmlDocument>:</span><span class="sxs-lookup"><span data-stu-id="e1888-106">For example, the following would be a typical way to create an XML tree using the Microsoft implementation of DOM, <xref:System.Xml.XmlDocument>:</span></span>  
  
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
  
 <span data-ttu-id="e1888-107">Dieses Format der Codierung liefert keine ausführlichen visuellen Informationen zum Aufbau der XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="e1888-107">This style of coding does not visually provide much information about the structure of the XML tree.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="e1888-108">unterstützt diesen Ansatz der Erstellung einer XML-Struktur, aber auch einen alternativen Ansatz, die so genannte *funktionale Konstruktion*.</span><span class="sxs-lookup"><span data-stu-id="e1888-108">supports this approach to constructing an XML tree, but also supports an alternative approach, *functional construction*.</span></span> <span data-ttu-id="e1888-109">In Visual Basic verwendet die funktionale Konstruktion XML-Literale, um eine XML-Struktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e1888-109">In Visual Basic, functional construction uses XML literals to build an XML tree.</span></span>  
  
 <span data-ttu-id="e1888-110">Das folgende Beispiel zeigt, wie Sie dieselbe XML-Struktur wie oben mit der funktionalen Konstruktion in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] konstruieren können:</span><span class="sxs-lookup"><span data-stu-id="e1888-110">Here is how you would construct the same XML tree by using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] functional construction:</span></span>  
  
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
  
 <span data-ttu-id="e1888-111">Die Codeeinzüge verdeutlichen den Aufbau des der XML-Struktur zugrunde liegenden XML-Codes.</span><span class="sxs-lookup"><span data-stu-id="e1888-111">Notice that indenting the code to construct the XML tree shows the structure of the underlying XML.</span></span>  
  
 <span data-ttu-id="e1888-112">Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen (Visual Basic)](creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="e1888-112">For more information, see [Creating XML Trees (Visual Basic)](creating-xml-trees.md).</span></span>  
  
## <a name="working-directly-with-xml-elements"></a><span data-ttu-id="e1888-113">Direktes Arbeiten mit XML-Elementen</span><span class="sxs-lookup"><span data-stu-id="e1888-113">Working Directly with XML Elements</span></span>  
 <span data-ttu-id="e1888-114">Beim Programmieren mit XML liegt Ihr Hauptaugenmerk in der Regel auf XML-Elementen und vielleicht auch auf Attributen.</span><span class="sxs-lookup"><span data-stu-id="e1888-114">When you program with XML, your primary focus is usually on XML elements and perhaps on attributes.</span></span> <span data-ttu-id="e1888-115">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie direkt mit XML-Elementen und Attributen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e1888-115">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can work directly with XML elements and attributes.</span></span> <span data-ttu-id="e1888-116">So können Sie z. B. Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="e1888-116">For example, you can do the following:</span></span>  
  
- <span data-ttu-id="e1888-117">Sie können XML-Elemente ohne jegliche Verwendung eines Dokumentobjekts erstellen.</span><span class="sxs-lookup"><span data-stu-id="e1888-117">Create XML elements without using a document object at all.</span></span> <span data-ttu-id="e1888-118">Dies vereinfacht beim Arbeiten mit Fragmenten von XML-Strukturen die Programmierung.</span><span class="sxs-lookup"><span data-stu-id="e1888-118">This simplifies programming when you have to work with fragments of XML trees.</span></span>  
  
- <span data-ttu-id="e1888-119">Sie können `T:System.Xml.Linq.XElement`-Objekte direkt aus einer XML-Datei laden.</span><span class="sxs-lookup"><span data-stu-id="e1888-119">Load `T:System.Xml.Linq.XElement` objects directly from an XML file.</span></span>  
  
- <span data-ttu-id="e1888-120">Sie können `T:System.Xml.Linq.XElement`-Objekte in eine Datei oder einen Stream serialisieren.</span><span class="sxs-lookup"><span data-stu-id="e1888-120">Serialize `T:System.Xml.Linq.XElement` objects to a file or a stream.</span></span>  
  
 <span data-ttu-id="e1888-121">Vergleichen Sie dies mit dem W3C-DOM, bei dem das XML-Dokument als logischer Container für die XML-Struktur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1888-121">Compare this to the W3C DOM, in which the XML document is used as a logical container for the XML tree.</span></span> <span data-ttu-id="e1888-122">Im DOM müssen die XML-Knoten einschließlich der Elemente und Attribute im Kontext eines XML-Dokuments erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e1888-122">In DOM, XML nodes, including elements and attributes, must be created in the context of an XML document.</span></span> <span data-ttu-id="e1888-123">Das folgende Codefragment erstellt ein Namenselement im DOM:</span><span class="sxs-lookup"><span data-stu-id="e1888-123">Here is a fragment of the code to create a name element in DOM:</span></span>  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
doc.AppendChild(name)  
```  
  
 <span data-ttu-id="e1888-124">Wenn Sie ein Element in mehreren Dokumenten verwenden möchten, müssen Sie die Knoten dokumentübergreifend importieren.</span><span class="sxs-lookup"><span data-stu-id="e1888-124">If you want to use an element across multiple documents, you must import the nodes across documents.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="e1888-125">vermeidet diese Ebene der Komplexität.</span><span class="sxs-lookup"><span data-stu-id="e1888-125">avoids this layer of complexity.</span></span>  
  
 <span data-ttu-id="e1888-126">Bei der Verwendung von LINQ to XML müssen Sie die <xref:System.Xml.Linq.XDocument>-Klasse nur dann verwenden, wenn Sie der Stammebene des Dokuments einen Kommentar oder eine Verarbeitungsanweisung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="e1888-126">When using LINQ to XML, you use the <xref:System.Xml.Linq.XDocument> class only if you want to add a comment or processing instruction at the root level of the document.</span></span>  
  
## <a name="simplified-handling-of-names-and-namespaces"></a><span data-ttu-id="e1888-127">Vereinfachte Handhabung von Namen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="e1888-127">Simplified Handling of Names and Namespaces</span></span>  
 <span data-ttu-id="e1888-128">Die Handhabung von Namen, Namespaces und Namespacepräfixen ist im Allgemeinen ein komplexer Teil der XML-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="e1888-128">Handling names, namespaces, and namespace prefixes is generally a complex part of XML programming.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="e1888-129">vereinfacht Namen und Namespaces, weil der Umgang mit Namespacepräfixen nicht zwingend erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e1888-129">simplifies names and namespaces by eliminating the requirement to deal with namespace prefixes.</span></span> <span data-ttu-id="e1888-130">Das heißt aber nicht, dass Sie die Namespacepräfixe nicht mehr selbst steuern können.</span><span class="sxs-lookup"><span data-stu-id="e1888-130">If you want to control namespace prefixes, you can.</span></span> <span data-ttu-id="e1888-131">Wenn Sie sich aber dafür entscheiden, sich nicht mehr explizit um die Steuerung der Namespacepräfixe kümmern zu wollen, weist [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bei der Serialisierung, wo erforderlich, entsprechende Namespacepräfixe zu oder greift für die Serialisierung auf die Standardnamespaces zurück.</span><span class="sxs-lookup"><span data-stu-id="e1888-131">But if you decide to not explicitly control namespace prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will assign namespace prefixes during serialization if they are required, or will serialize using default namespaces if they are not.</span></span> <span data-ttu-id="e1888-132">Wenn Standardnamespaces verwendet werden, gibt es im resultierenden Dokument keine Namespacepräfixe.</span><span class="sxs-lookup"><span data-stu-id="e1888-132">If default namespaces are used, there will be no namespace prefixes in the resulting document.</span></span> <span data-ttu-id="e1888-133">Weitere Informationen finden Sie unter [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e1888-133">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="e1888-134">Ein anderes Problem mit dem DOM besteht darin, dass es keine Änderung des Namens eines Knotens zulässt.</span><span class="sxs-lookup"><span data-stu-id="e1888-134">Another problem with the DOM is that it does not let you change the name of a node.</span></span> <span data-ttu-id="e1888-135">Stattdessen müssen Sie einen neuen Knoten erstellen und alle untergeordneten Knoten kopieren, sodass die ursprüngliche Knotenidentität verloren geht.</span><span class="sxs-lookup"><span data-stu-id="e1888-135">Instead, you have to create a new node and copy all the child nodes to it, losing the original node identity.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="e1888-136">vermeidet dieses Problem, indem es Ihnen ermöglicht wird, für einen Knoten die <xref:System.Xml.Linq.XName>-Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e1888-136">avoids this problem by enabling you to set the <xref:System.Xml.Linq.XName> property on a node.</span></span>  
  
## <a name="static-method-support-for-loading-xml"></a><span data-ttu-id="e1888-137">Unterstützung statischer Methoden für das Laden von XML</span><span class="sxs-lookup"><span data-stu-id="e1888-137">Static Method Support for Loading XML</span></span>  
 <span data-ttu-id="e1888-138">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie zum Laden von XML anstelle von Instanzmethoden statische Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1888-138">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lets you load XML by using static methods, instead of instance methods.</span></span> <span data-ttu-id="e1888-139">Dadurch vereinfacht sich das Laden und das Analysieren.</span><span class="sxs-lookup"><span data-stu-id="e1888-139">This simplifies loading and parsing.</span></span> <span data-ttu-id="e1888-140">Weitere Informationen finden Sie unter Gewusst [wie: Laden von XML aus einer Datei (Visual Basic)](how-to-load-xml-from-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="e1888-140">For more information, see [How to: Load XML from a File (Visual Basic)](how-to-load-xml-from-a-file.md).</span></span>  
  
## <a name="removal-of-support-for-dtd-constructs"></a><span data-ttu-id="e1888-141">Entfernung der Unterstützung für DTD-Konstrukte</span><span class="sxs-lookup"><span data-stu-id="e1888-141">Removal of Support for DTD Constructs</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="e1888-142">vereinfacht die XML-Programmierung zusätzlich, indem die Unterstützung für Entitäten und Entitätsverweise entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="e1888-142">further simplifies XML programming by removing support for entities and entity references.</span></span> <span data-ttu-id="e1888-143">Die Verwaltung von Entitäten ist komplex und wird selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1888-143">The management of entities is complex, and is rarely used.</span></span> <span data-ttu-id="e1888-144">Durch das Entfernen dieser Unterstützung wird die Leistung verbessert und die Programmierung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="e1888-144">Removing their support increases performance and simplifies the programming interface.</span></span> <span data-ttu-id="e1888-145">Beim Auffüllen einer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Struktur werden alle DTD-Entitäten erweitert.</span><span class="sxs-lookup"><span data-stu-id="e1888-145">When a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] tree is populated, all DTD entities are expanded.</span></span>  
  
## <a name="support-for-fragments"></a><span data-ttu-id="e1888-146">Unterstützung für Fragmente</span><span class="sxs-lookup"><span data-stu-id="e1888-146">Support for Fragments</span></span>  
 <span data-ttu-id="e1888-147">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] gibt es keine Entsprechung für die Klasse `XmlDocumentFragment`.</span><span class="sxs-lookup"><span data-stu-id="e1888-147">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] does not provide an equivalent for the `XmlDocumentFragment` class.</span></span> <span data-ttu-id="e1888-148">In vielen Fällen lassen sich aber mit dem Ergebnis einer Abfrage, die als `XmlDocumentFragment`-Schnittstelle von <xref:System.Collections.Generic.IEnumerable%601> oder als <xref:System.Xml.Linq.XNode>-Schnittstelle von <xref:System.Collections.Generic.IEnumerable%601> typisiert ist, die gleichen Ergebnisse wie mit der <xref:System.Xml.Linq.XElement>-Klasse erzielen.</span><span class="sxs-lookup"><span data-stu-id="e1888-148">In many cases, however, the `XmlDocumentFragment` concept can be handled by the result of a query that is typed as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XNode>, or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="support-for-xpathnavigator"></a><span data-ttu-id="e1888-149">Unterstützung für XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="e1888-149">Support for XPathNavigator</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="e1888-150">bietet über die Erweiterungsmethoden im <xref:System.Xml.XPath?displayProperty=nameWithType>-Namespace Unterstützung für <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="e1888-150">provides support for <xref:System.Xml.XPath.XPathNavigator> through extension methods in the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="e1888-151">Weitere Informationen finden Sie unter <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e1888-151">For more information, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
## <a name="support-for-white-space-and-indentation"></a><span data-ttu-id="e1888-152">Unterstützung für Leerraum und Einzüge</span><span class="sxs-lookup"><span data-stu-id="e1888-152">Support for White Space and Indentation</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="e1888-153">handhabt Leerzeichen einfacher als das DOM.</span><span class="sxs-lookup"><span data-stu-id="e1888-153">handles white space more simply than the DOM.</span></span>  
  
 <span data-ttu-id="e1888-154">Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e1888-154">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="e1888-155">Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten.</span><span class="sxs-lookup"><span data-stu-id="e1888-155">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="e1888-156">Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1888-156">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="e1888-157">Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert.</span><span class="sxs-lookup"><span data-stu-id="e1888-157">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="e1888-158">Sie möchten nicht, dass diese Einzüge irgendwie geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e1888-158">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="e1888-159">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1888-159">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can do this by preserving white space when you load or parse the XML and disabling formatting when you serialize the XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="e1888-160">speichert Leerraum als <xref:System.Xml.Linq.XText>-Knoten und nicht als speziellen <xref:System.Xml.XmlNodeType.Whitespace>-Knotentyp, wie dies im DOM der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="e1888-160">stores white space as an <xref:System.Xml.Linq.XText> node, instead of having a specialized <xref:System.Xml.XmlNodeType.Whitespace> node type, as the DOM does.</span></span>  
  
## <a name="support-for-annotations"></a><span data-ttu-id="e1888-161">Unterstützung für Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="e1888-161">Support for Annotations</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="e1888-162">-Elemente unterstützen einen erweiterbaren Satz von Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="e1888-162">elements support an extensible set of annotations.</span></span> <span data-ttu-id="e1888-163">Dies ist hilfreich, wenn verschiedene Informationen zu einem Element nachverfolgt werden sollen, z.B. Schemainformationen, die Information, ob das Element an eine Benutzeroberfläche gebunden ist, oder andere anwendungsspezifische Informationen.</span><span class="sxs-lookup"><span data-stu-id="e1888-163">This is useful for tracking miscellaneous information about an element, such as schema information, information about whether the element is bound to a UI, or any other kind of application-specific information.</span></span> <span data-ttu-id="e1888-164">Weitere Informationen finden Sie unter [Anmerkungen zu LINQ to XML](linq-to-xml-annotations.md).</span><span class="sxs-lookup"><span data-stu-id="e1888-164">For more information, see [LINQ to XML Annotations](linq-to-xml-annotations.md).</span></span>  
  
## <a name="support-for-schema-information"></a><span data-ttu-id="e1888-165">Unterstützung für Schemainformationen</span><span class="sxs-lookup"><span data-stu-id="e1888-165">Support for Schema Information</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="e1888-166">bietet über die Erweiterungsmethoden im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace Unterstützung für die XSD-Validierung.</span><span class="sxs-lookup"><span data-stu-id="e1888-166">provides support for XSD validation through extension methods in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="e1888-167">Sie können prüfen, ob sich eine XML-Struktur nach einer XSD richtet.</span><span class="sxs-lookup"><span data-stu-id="e1888-167">You can validate that an XML tree complies with an XSD.</span></span> <span data-ttu-id="e1888-168">Sie können die XML-Struktur mit dem Post-Schema-Validierungs-Infoset (PSVI) auffüllen.</span><span class="sxs-lookup"><span data-stu-id="e1888-168">You can populate the XML tree with the post-schema-validation infoset (PSVI).</span></span> <span data-ttu-id="e1888-169">Weitere Informationen finden Sie unter Gewusst [wie: Überprüfen mithilfe von XSD](how-to-validate-using-xsd-linq-to-xml.md) und <xref:System.Xml.Schema.Extensions> .</span><span class="sxs-lookup"><span data-stu-id="e1888-169">For more information, see [How to: Validate Using XSD](how-to-validate-using-xsd-linq-to-xml.md) and <xref:System.Xml.Schema.Extensions>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1888-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1888-170">See also</span></span>

- [<span data-ttu-id="e1888-171">Erste Schritte (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="e1888-171">Getting Started (LINQ to XML)</span></span>](getting-started-linq-to-xml.md)
