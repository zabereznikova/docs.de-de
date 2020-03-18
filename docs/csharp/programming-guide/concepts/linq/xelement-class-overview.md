---
title: Übersicht über die XElement-Klasse (C#)
ms.date: 07/20/2015
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: 6a93dd4bdaf16fddff800b08b0f3146ecb63f9b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167893"
---
# <a name="xelement-class-overview-c"></a><span data-ttu-id="91a4d-102">Übersicht über die XElement-Klasse (C#)</span><span class="sxs-lookup"><span data-stu-id="91a4d-102">XElement Class Overview (C#)</span></span>
<span data-ttu-id="91a4d-103">Die <xref:System.Xml.Linq.XElement>-Klasse ist eine der wichtigsten Klassen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91a4d-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="91a4d-104">Sie stellt ein XML-Element dar.</span><span class="sxs-lookup"><span data-stu-id="91a4d-104">It represents an XML element.</span></span> <span data-ttu-id="91a4d-105">Diese Klasse kann zum Erstellen von Elementen, zum Ändern des Inhalts des Elements, zum Hinzufügen, Ändern oder Löschen untergeordneter Elemente, zum Hinzufügen von Attributen zu einem Element oder zum Serialisieren des Inhalts eines Elements in Textform verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91a4d-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="91a4d-106">Die Klasse kann auch mit anderen Klassen in <xref:System.Xml?displayProperty=nameWithType> zusammenarbeiten, wie <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> und <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="91a4d-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
<span data-ttu-id="91a4d-107">In diesem Thema wird die von der <xref:System.Xml.Linq.XElement>-Klasse bereitgestellte Funktionalität beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91a4d-107">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
## <a name="constructing-xml-trees"></a><span data-ttu-id="91a4d-108">Konstruieren von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="91a4d-108">Constructing XML Trees</span></span>  
 <span data-ttu-id="91a4d-109">Für das Konstruieren von XML-Strukturen stehen Ihnen verschiedene Möglichkeiten zur Verfügung. So können Sie z. B. Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="91a4d-109">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
- <span data-ttu-id="91a4d-110">XML-Strukturen in Code konstruieren</span><span class="sxs-lookup"><span data-stu-id="91a4d-110">You can construct an XML tree in code.</span></span> <span data-ttu-id="91a4d-111">Weitere Informationen finden Sie unter [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#)) ](./linq-to-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="91a4d-111">For more information, see [Creating XML Trees (C#)](./linq-to-xml-overview.md).</span></span>  
  
- <span data-ttu-id="91a4d-112">XML aus verschiedenen Quellen, wie <xref:System.IO.TextReader>, Textdateien oder Internetadressen (URLs), analysieren</span><span class="sxs-lookup"><span data-stu-id="91a4d-112">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="91a4d-113">Weitere Informationen finden Sie unter [Parsing XML (C#) (XML analysieren (C#))](./how-to-parse-a-string.md).</span><span class="sxs-lookup"><span data-stu-id="91a4d-113">For more information, see [Parsing XML (C#)](./how-to-parse-a-string.md).</span></span>  
  
- <span data-ttu-id="91a4d-114">einen <xref:System.Xml.XmlReader> verwenden, um die Struktur aufzufüllen</span><span class="sxs-lookup"><span data-stu-id="91a4d-114">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="91a4d-115">Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span><span class="sxs-lookup"><span data-stu-id="91a4d-115">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
- <span data-ttu-id="91a4d-116">mit der <xref:System.Xml.XmlWriter>-Methode einen Writer erstellen, den Writer an das Modul übergeben und dann den in den <xref:System.Xml.Linq.XContainer.CreateWriter%2A> geschriebenen Inhalt zum Auffüllen der XML-Struktur verwenden, sofern ein Modul vorhanden ist, das Inhalt in einen <xref:System.Xml.XmlWriter> schreiben kann</span><span class="sxs-lookup"><span data-stu-id="91a4d-116">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="91a4d-117">Die verbreitetste Variante, eine XML-Struktur zu erstellen, sieht aber wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="91a4d-117">However, the most common way to create an XML tree is as follows:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="91a4d-118">Bei einer weiteren häufig verwendeten Technik zum Erstellen einer XML-Struktur wird die XML-Struktur anhand der Ergebnisse einer LINQ-Abfrage aufgefüllt, wie im folgenden Beispiel dargestellt wird:</span><span class="sxs-lookup"><span data-stu-id="91a4d-118">Another very common technique for creating an XML tree involves using the results of a LINQ query to populate an XML tree, as shown in the following example:</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 <span data-ttu-id="91a4d-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="91a4d-119">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="serializing-xml-trees"></a><span data-ttu-id="91a4d-120">Serialisieren von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="91a4d-120">Serializing XML Trees</span></span>  
 <span data-ttu-id="91a4d-121">Sie können die XML-Struktur in eine <xref:System.IO.File>, in einen <xref:System.IO.TextWriter> oder in einen <xref:System.Xml.XmlWriter> serialisieren.</span><span class="sxs-lookup"><span data-stu-id="91a4d-121">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="91a4d-122">Weitere Informationen finden Sie unter [Serializing XML Trees (C#) (Serialisieren von XML-Strukturen (C#))](./preserving-white-space-while-serializing.md).</span><span class="sxs-lookup"><span data-stu-id="91a4d-122">For more information, see [Serializing XML Trees (C#)](./preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="91a4d-123">Abrufen von XML-Daten über Achsenmethoden</span><span class="sxs-lookup"><span data-stu-id="91a4d-123">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="91a4d-124">Mit Achsenmethoden können Sie Attribute, untergeordnete Elemente, Nachfolgerelemente und Vorgängerelemente abrufen.</span><span class="sxs-lookup"><span data-stu-id="91a4d-124">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="91a4d-125">LINQ-Abfragen verwenden Achsenmethoden und bieten verschiedene flexible und leistungsstarke Möglichkeiten zum Navigieren durch eine XML-Struktur und zu deren Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="91a4d-125">LINQ queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="91a4d-126">Weitere Informationen finden Sie unter [LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](./linq-to-xml-axes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="91a4d-126">For more information, see [LINQ to XML Axes (C#)](./linq-to-xml-axes-overview.md).</span></span>  
  
## <a name="querying-xml-trees"></a><span data-ttu-id="91a4d-127">Abfragen von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="91a4d-127">Querying XML Trees</span></span>  
 <span data-ttu-id="91a4d-128">Sie können LINQ-Abfragen schreiben, die Daten aus einer XML-Struktur abrufen.</span><span class="sxs-lookup"><span data-stu-id="91a4d-128">You can write LINQ queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="91a4d-129">Weitere Informationen finden Sie unter [Querying XML Trees (C#) (Abfragen von XML-Strukturen (C#))](./how-to-find-an-element-with-a-specific-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="91a4d-129">For more information, see [Querying XML Trees (C#)](./how-to-find-an-element-with-a-specific-attribute.md).</span></span>  
  
## <a name="modifying-xml-trees"></a><span data-ttu-id="91a4d-130">Ändern von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="91a4d-130">Modifying XML Trees</span></span>  
 <span data-ttu-id="91a4d-131">Sie können ein Element auf unterschiedliche Weise ändern, z. B. durch Ändern seines Inhalts oder seiner Attribute.</span><span class="sxs-lookup"><span data-stu-id="91a4d-131">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="91a4d-132">Sie können ein Element auch aus seinem übergeordneten Element entfernen.</span><span class="sxs-lookup"><span data-stu-id="91a4d-132">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="91a4d-133">Weitere Informationen finden Sie unter [Modifying XML Trees (LINQ to XML) (C#) (Bearbeiten von XML-Strukturen (LINQ to XML) (C#))](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="91a4d-133">For more information, see [Modifying XML Trees (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a4d-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91a4d-134">See also</span></span>

- [<span data-ttu-id="91a4d-135">Working with XML Namespaces (C#) (Übersicht der LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="91a4d-135">LINQ to XML Programming Overview (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
