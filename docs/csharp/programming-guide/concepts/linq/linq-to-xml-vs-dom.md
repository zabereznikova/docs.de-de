---
title: LINQ to XML im Vergleich zu DOM (C#)
description: Hier erfahren Sie mehr über einige wichtige Unterschiede zwischen LINQ to XML und der XML-Programmier-API des W3C-Dokumentobjektmodells (DOM).
ms.date: 07/20/2015
ms.assetid: 51c0e3d2-c047-4e6a-a423-d61a882400b7
ms.openlocfilehash: f5fc3fd7869079d47d7c9031e3668afeed7a117b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165346"
---
# <a name="linq-to-xml-vs-dom-c"></a><span data-ttu-id="3ddb6-103">LINQ to XML im Vergleich zu DOM (C#)</span><span class="sxs-lookup"><span data-stu-id="3ddb6-103">LINQ to XML vs. DOM (C#)</span></span>
<span data-ttu-id="3ddb6-104">In diesem Abschnitt werden einige der wichtigsten Unterschiede zwischen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] und der derzeit verbreitetsten XML-Programmier-API, dem W3C-Dokumentobjektmodell (DOM), beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-104">This section describes some key differences between [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] and the current predominant XML programming API, the W3C Document Object Model (DOM).</span></span>  
  
## <a name="new-ways-to-construct-xml-trees"></a><span data-ttu-id="3ddb6-105">Neue Möglichkeiten zum Konstruieren von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="3ddb6-105">New Ways to Construct XML Trees</span></span>  
 <span data-ttu-id="3ddb6-106">Im W3C-DOM erstellen Sie eine XML-Struktur von unten nach oben. Das bedeutet, Sie erstellen ein Dokument, Sie erstellen Elemente, und anschließend fügen Sie die Elemente dem Dokument hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-106">In the W3C DOM, you build an XML tree from the bottom up; that is, you create a document, you create elements, and then you add the elements to the document.</span></span>  
  
 <span data-ttu-id="3ddb6-107">Das folgende Beispiel zeigt eine typische Herangehensweise an das Erstellen einer XML-Struktur mit der Microsoft-Implementierung des DOM, <xref:System.Xml.XmlDocument>:</span><span class="sxs-lookup"><span data-stu-id="3ddb6-107">For example, the following would be a typical way to create an XML tree using the Microsoft implementation of DOM, <xref:System.Xml.XmlDocument>:</span></span>  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
XmlElement phone1 = doc.CreateElement("Phone");  
phone1.SetAttribute("Type", "Home");  
phone1.InnerText = "206-555-0144";
XmlElement phone2 = doc.CreateElement("Phone");  
phone2.SetAttribute("Type", "Work");  
phone2.InnerText = "425-555-0145";
XmlElement street1 = doc.CreateElement("Street1");
street1.InnerText = "123 Main St";  
XmlElement city = doc.CreateElement("City");  
city.InnerText = "Mercer Island";  
XmlElement state = doc.CreateElement("State");  
state.InnerText = "WA";  
XmlElement postal = doc.CreateElement("Postal");  
postal.InnerText = "68042";  
XmlElement address = doc.CreateElement("Address");  
address.AppendChild(street1);  
address.AppendChild(city);  
address.AppendChild(state);  
address.AppendChild(postal);  
XmlElement contact = doc.CreateElement("Contact");  
contact.AppendChild(name);  
contact.AppendChild(phone1);  
contact.AppendChild(phone2);  
contact.AppendChild(address);  
XmlElement contacts = doc.CreateElement("Contacts");  
contacts.AppendChild(contact);  
doc.AppendChild(contacts);  
```  
  
 <span data-ttu-id="3ddb6-108">Dieses Format der Codierung liefert keine ausführlichen visuellen Informationen zum Aufbau der XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-108">This style of coding does not visually provide much information about the structure of the XML tree.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3ddb6-109">unterstützt diesen Ansatz der Erstellung einer XML-Struktur, aber auch einen alternativen Ansatz, die so genannte *funktionale Konstruktion*.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-109">supports this approach to constructing an XML tree, but also supports an alternative approach, *functional construction*.</span></span> <span data-ttu-id="3ddb6-110">Bei der funktionalen Konstruktion werden zum Erstellen einer XML-Struktur die Konstruktoren <xref:System.Xml.Linq.XElement> und <xref:System.Xml.Linq.XAttribute> verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-110">Functional construction uses the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> constructors to build an XML tree.</span></span>  
  
 <span data-ttu-id="3ddb6-111">Das folgende Beispiel zeigt, wie Sie dieselbe XML-Struktur wie oben mit der funktionalen Konstruktion in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] konstruieren können:</span><span class="sxs-lookup"><span data-stu-id="3ddb6-111">Here is how you would construct the same XML tree by using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] functional construction:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),  
            new XElement("Phone", "206-555-0144",
                new XAttribute("Type", "Home")),  
            new XElement("phone", "425-555-0145",  
                new XAttribute("Type", "Work")),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="3ddb6-112">Die Codeeinzüge verdeutlichen den Aufbau des der XML-Struktur zugrunde liegenden XML-Codes.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-112">Notice that indenting the code to construct the XML tree shows the structure of the underlying XML.</span></span>  
  
 <span data-ttu-id="3ddb6-113">Weitere Informationen finden Sie unter [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))](./linq-to-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3ddb6-113">For more information, see [Creating XML Trees (C#)](./linq-to-xml-overview.md).</span></span>  
  
## <a name="working-directly-with-xml-elements"></a><span data-ttu-id="3ddb6-114">Direktes Arbeiten mit XML-Elementen</span><span class="sxs-lookup"><span data-stu-id="3ddb6-114">Working Directly with XML Elements</span></span>  
 <span data-ttu-id="3ddb6-115">Beim Programmieren mit XML liegt Ihr Hauptaugenmerk in der Regel auf XML-Elementen und vielleicht auch auf Attributen.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-115">When you program with XML, your primary focus is usually on XML elements and perhaps on attributes.</span></span> <span data-ttu-id="3ddb6-116">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie direkt mit XML-Elementen und Attributen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-116">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can work directly with XML elements and attributes.</span></span> <span data-ttu-id="3ddb6-117">So können Sie z. B. Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="3ddb6-117">For example, you can do the following:</span></span>  
  
- <span data-ttu-id="3ddb6-118">Sie können XML-Elemente ohne jegliche Verwendung eines Dokumentobjekts erstellen.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-118">Create XML elements without using a document object at all.</span></span> <span data-ttu-id="3ddb6-119">Dies vereinfacht beim Arbeiten mit Fragmenten von XML-Strukturen die Programmierung.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-119">This simplifies programming when you have to work with fragments of XML trees.</span></span>  
  
- <span data-ttu-id="3ddb6-120">Sie können `T:System.Xml.Linq.XElement`-Objekte direkt aus einer XML-Datei laden.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-120">Load `T:System.Xml.Linq.XElement` objects directly from an XML file.</span></span>  
  
- <span data-ttu-id="3ddb6-121">Sie können `T:System.Xml.Linq.XElement`-Objekte in eine Datei oder einen Stream serialisieren.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-121">Serialize `T:System.Xml.Linq.XElement` objects to a file or a stream.</span></span>  
  
 <span data-ttu-id="3ddb6-122">Vergleichen Sie dies mit dem W3C-DOM, bei dem das XML-Dokument als logischer Container für die XML-Struktur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-122">Compare this to the W3C DOM, in which the XML document is used as a logical container for the XML tree.</span></span> <span data-ttu-id="3ddb6-123">Im DOM müssen die XML-Knoten einschließlich der Elemente und Attribute im Kontext eines XML-Dokuments erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-123">In DOM, XML nodes, including elements and attributes, must be created in the context of an XML document.</span></span> <span data-ttu-id="3ddb6-124">Das folgende Codefragment erstellt ein Namenselement im DOM:</span><span class="sxs-lookup"><span data-stu-id="3ddb6-124">Here is a fragment of the code to create a name element in DOM:</span></span>  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
doc.AppendChild(name);  
```  
  
 <span data-ttu-id="3ddb6-125">Wenn Sie ein Element in mehreren Dokumenten verwenden möchten, müssen Sie die Knoten dokumentübergreifend importieren.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-125">If you want to use an element across multiple documents, you must import the nodes across documents.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3ddb6-126">vermeidet diese Ebene der Komplexität.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-126">avoids this layer of complexity.</span></span>  
  
 <span data-ttu-id="3ddb6-127">Bei der Verwendung von LINQ to XML müssen Sie die <xref:System.Xml.Linq.XDocument>-Klasse nur dann verwenden, wenn Sie der Stammebene des Dokuments einen Kommentar oder eine Verarbeitungsanweisung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-127">When using LINQ to XML, you use the <xref:System.Xml.Linq.XDocument> class only if you want to add a comment or processing instruction at the root level of the document.</span></span>  
  
## <a name="simplified-handling-of-names-and-namespaces"></a><span data-ttu-id="3ddb6-128">Vereinfachte Handhabung von Namen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="3ddb6-128">Simplified Handling of Names and Namespaces</span></span>  
 <span data-ttu-id="3ddb6-129">Die Handhabung von Namen, Namespaces und Namespacepräfixen ist im Allgemeinen ein komplexer Teil der XML-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-129">Handling names, namespaces, and namespace prefixes is generally a complex part of XML programming.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3ddb6-130">vereinfacht Namen und Namespaces, weil der Umgang mit Namespacepräfixen nicht zwingend erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-130">simplifies names and namespaces by eliminating the requirement to deal with namespace prefixes.</span></span> <span data-ttu-id="3ddb6-131">Das heißt aber nicht, dass Sie die Namespacepräfixe nicht mehr selbst steuern können.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-131">If you want to control namespace prefixes, you can.</span></span> <span data-ttu-id="3ddb6-132">Wenn Sie sich aber dafür entscheiden, sich nicht mehr explizit um die Steuerung der Namespacepräfixe kümmern zu wollen, weist [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bei der Serialisierung, wo erforderlich, entsprechende Namespacepräfixe zu oder greift für die Serialisierung auf die Standardnamespaces zurück.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-132">But if you decide to not explicitly control namespace prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will assign namespace prefixes during serialization if they are required, or will serialize using default namespaces if they are not.</span></span> <span data-ttu-id="3ddb6-133">Wenn Standardnamespaces verwendet werden, gibt es im resultierenden Dokument keine Namespacepräfixe.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-133">If default namespaces are used, there will be no namespace prefixes in the resulting document.</span></span> <span data-ttu-id="3ddb6-134">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3ddb6-134">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="3ddb6-135">Ein anderes Problem mit dem DOM besteht darin, dass es keine Änderung des Namens eines Knotens zulässt.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-135">Another problem with the DOM is that it does not let you change the name of a node.</span></span> <span data-ttu-id="3ddb6-136">Stattdessen müssen Sie einen neuen Knoten erstellen und alle untergeordneten Knoten kopieren, sodass die ursprüngliche Knotenidentität verloren geht.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-136">Instead, you have to create a new node and copy all the child nodes to it, losing the original node identity.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3ddb6-137">vermeidet dieses Problem, indem es Ihnen ermöglicht wird, für einen Knoten die <xref:System.Xml.Linq.XName>-Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-137">avoids this problem by enabling you to set the <xref:System.Xml.Linq.XName> property on a node.</span></span>  
  
## <a name="static-method-support-for-loading-xml"></a><span data-ttu-id="3ddb6-138">Unterstützung statischer Methoden für das Laden von XML</span><span class="sxs-lookup"><span data-stu-id="3ddb6-138">Static Method Support for Loading XML</span></span>  
 <span data-ttu-id="3ddb6-139">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie zum Laden von XML anstelle von Instanzmethoden statische Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-139">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lets you load XML by using static methods, instead of instance methods.</span></span> <span data-ttu-id="3ddb6-140">Dadurch vereinfacht sich das Laden und das Analysieren.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-140">This simplifies loading and parsing.</span></span> <span data-ttu-id="3ddb6-141">Weitere Informationen finden Sie unter [Vorgehensweise: Laden von XML aus einer Datei (C#)](./how-to-load-xml-from-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="3ddb6-141">For more information, see [How to load XML from a file (C#)](./how-to-load-xml-from-a-file.md).</span></span>  
  
## <a name="removal-of-support-for-dtd-constructs"></a><span data-ttu-id="3ddb6-142">Entfernung der Unterstützung für DTD-Konstrukte</span><span class="sxs-lookup"><span data-stu-id="3ddb6-142">Removal of Support for DTD Constructs</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3ddb6-143">vereinfacht die XML-Programmierung zusätzlich, indem die Unterstützung für Entitäten und Entitätsverweise entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-143">further simplifies XML programming by removing support for entities and entity references.</span></span> <span data-ttu-id="3ddb6-144">Die Verwaltung von Entitäten ist komplex und wird selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-144">The management of entities is complex, and is rarely used.</span></span> <span data-ttu-id="3ddb6-145">Durch das Entfernen dieser Unterstützung wird die Leistung verbessert und die Programmierung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-145">Removing their support increases performance and simplifies the programming interface.</span></span> <span data-ttu-id="3ddb6-146">Beim Auffüllen einer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Struktur werden alle DTD-Entitäten erweitert.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-146">When a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] tree is populated, all DTD entities are expanded.</span></span>  
  
## <a name="support-for-fragments"></a><span data-ttu-id="3ddb6-147">Unterstützung für Fragmente</span><span class="sxs-lookup"><span data-stu-id="3ddb6-147">Support for Fragments</span></span>  
 <span data-ttu-id="3ddb6-148">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] gibt es keine Entsprechung für die Klasse `XmlDocumentFragment`.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-148">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] does not provide an equivalent for the `XmlDocumentFragment` class.</span></span> <span data-ttu-id="3ddb6-149">In vielen Fällen lassen sich aber mit dem Ergebnis einer Abfrage, die als `XmlDocumentFragment`-Schnittstelle von <xref:System.Collections.Generic.IEnumerable%601> oder als <xref:System.Xml.Linq.XNode>-Schnittstelle von <xref:System.Collections.Generic.IEnumerable%601> typisiert ist, die gleichen Ergebnisse wie mit der <xref:System.Xml.Linq.XElement>-Klasse erzielen.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-149">In many cases, however, the `XmlDocumentFragment` concept can be handled by the result of a query that is typed as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XNode>, or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="support-for-xpathnavigator"></a><span data-ttu-id="3ddb6-150">Unterstützung für XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="3ddb6-150">Support for XPathNavigator</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3ddb6-151">bietet über die Erweiterungsmethoden im <xref:System.Xml.XPath?displayProperty=nameWithType>-Namespace Unterstützung für <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-151">provides support for <xref:System.Xml.XPath.XPathNavigator> through extension methods in the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="3ddb6-152">Weitere Informationen finden Sie unter <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-152">For more information, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
## <a name="support-for-white-space-and-indentation"></a><span data-ttu-id="3ddb6-153">Unterstützung für Leerraum und Einzüge</span><span class="sxs-lookup"><span data-stu-id="3ddb6-153">Support for White Space and Indentation</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3ddb6-154">handhabt Leerzeichen einfacher als das DOM.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-154">handles white space more simply than the DOM.</span></span>  
  
 <span data-ttu-id="3ddb6-155">Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-155">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="3ddb6-156">Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-156">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="3ddb6-157">Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ddb6-157">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="3ddb6-158">Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-158">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="3ddb6-159">Sie möchten nicht, dass diese Einzüge irgendwie geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-159">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="3ddb6-160">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-160">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can do this by preserving white space when you load or parse the XML and disabling formatting when you serialize the XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3ddb6-161">speichert Leerraum als <xref:System.Xml.Linq.XText>-Knoten und nicht als speziellen <xref:System.Xml.XmlNodeType.Whitespace>-Knotentyp, wie dies im DOM der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-161">stores white space as an <xref:System.Xml.Linq.XText> node, instead of having a specialized <xref:System.Xml.XmlNodeType.Whitespace> node type, as the DOM does.</span></span>  
  
## <a name="support-for-annotations"></a><span data-ttu-id="3ddb6-162">Unterstützung für Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="3ddb6-162">Support for Annotations</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="3ddb6-163">-Elemente unterstützen einen erweiterbaren Satz von Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-163">elements support an extensible set of annotations.</span></span> <span data-ttu-id="3ddb6-164">Dies ist hilfreich, wenn verschiedene Informationen zu einem Element nachverfolgt werden sollen, z.B. Schemainformationen, die Information, ob das Element an eine Benutzeroberfläche gebunden ist, oder andere anwendungsspezifische Informationen.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-164">This is useful for tracking miscellaneous information about an element, such as schema information, information about whether the element is bound to a UI, or any other kind of application-specific information.</span></span> <span data-ttu-id="3ddb6-165">Weitere Informationen finden Sie unter [Anmerkungen zu LINQ to XML](./linq-to-xml-annotations.md).</span><span class="sxs-lookup"><span data-stu-id="3ddb6-165">For more information, see [LINQ to XML Annotations](./linq-to-xml-annotations.md).</span></span>  
  
## <a name="support-for-schema-information"></a><span data-ttu-id="3ddb6-166">Unterstützung für Schemainformationen</span><span class="sxs-lookup"><span data-stu-id="3ddb6-166">Support for Schema Information</span></span>  
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3ddb6-167">bietet über die Erweiterungsmethoden im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace Unterstützung für die XSD-Validierung.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-167">provides support for XSD validation through extension methods in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="3ddb6-168">Sie können prüfen, ob sich eine XML-Struktur nach einer XSD richtet.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-168">You can validate that an XML tree complies with an XSD.</span></span> <span data-ttu-id="3ddb6-169">Sie können die XML-Struktur mit dem Post-Schema-Validierungs-Infoset (PSVI) auffüllen.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-169">You can populate the XML tree with the post-schema-validation infoset (PSVI).</span></span> <span data-ttu-id="3ddb6-170">Weitere Informationen finden Sie unter [Vorgehensweise: Überprüfen mithilfe von XSD](./how-to-validate-using-xsd-linq-to-xml.md) und <xref:System.Xml.Schema.Extensions>.</span><span class="sxs-lookup"><span data-stu-id="3ddb6-170">For more information, see [How to validate using XSD](./how-to-validate-using-xsd-linq-to-xml.md) and <xref:System.Xml.Schema.Extensions>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3ddb6-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ddb6-171">See also</span></span>

- [<span data-ttu-id="3ddb6-172">Erste Schritte (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="3ddb6-172">Getting Started (LINQ to XML)</span></span>](./linq-to-xml-overview.md)
