---
title: Übersicht der XElement-Klasse
ms.date: 07/20/2015
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
ms.openlocfilehash: a0e50c8a5a14150ee09a328f4dcdd5bc88363621
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413218"
---
# <a name="xelement-class-overview-visual-basic"></a><span data-ttu-id="08e94-102">Übersicht über die XElement-Klasse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08e94-102">XElement Class Overview (Visual Basic)</span></span>
<span data-ttu-id="08e94-103">Die <xref:System.Xml.Linq.XElement>-Klasse ist eine der wichtigsten Klassen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08e94-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="08e94-104">Sie stellt ein XML-Element dar.</span><span class="sxs-lookup"><span data-stu-id="08e94-104">It represents an XML element.</span></span> <span data-ttu-id="08e94-105">Diese Klasse kann zum Erstellen von Elementen, zum Ändern des Inhalts des Elements, zum Hinzufügen, Ändern oder Löschen untergeordneter Elemente, zum Hinzufügen von Attributen zu einem Element oder zum Serialisieren des Inhalts eines Elements in Textform verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="08e94-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="08e94-106">Die Klasse kann auch mit anderen Klassen in <xref:System.Xml?displayProperty=nameWithType> zusammenarbeiten, wie <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> und <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="08e94-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="xelement-functionality"></a><span data-ttu-id="08e94-107">"XElement"-Funktionalität</span><span class="sxs-lookup"><span data-stu-id="08e94-107">XElement Functionality</span></span>  
 <span data-ttu-id="08e94-108">In diesem Thema wird die von der <xref:System.Xml.Linq.XElement>-Klasse bereitgestellte Funktionalität beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08e94-108">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
### <a name="constructing-xml-trees"></a><span data-ttu-id="08e94-109">Konstruieren von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="08e94-109">Constructing XML Trees</span></span>  
 <span data-ttu-id="08e94-110">Für das Konstruieren von XML-Strukturen stehen Ihnen verschiedene Möglichkeiten zur Verfügung. So können Sie z. B. Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="08e94-110">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
- <span data-ttu-id="08e94-111">XML-Strukturen in Code konstruieren</span><span class="sxs-lookup"><span data-stu-id="08e94-111">You can construct an XML tree in code.</span></span> <span data-ttu-id="08e94-112">Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen (Visual Basic)](creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="08e94-112">For more information, see [Creating XML Trees (Visual Basic)](creating-xml-trees.md).</span></span>  
  
- <span data-ttu-id="08e94-113">XML aus verschiedenen Quellen, wie <xref:System.IO.TextReader>, Textdateien oder Internetadressen (URLs), analysieren</span><span class="sxs-lookup"><span data-stu-id="08e94-113">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="08e94-114">Weitere Informationen finden Sie unter [XML (Visual Basic)](parsing-xml.md).</span><span class="sxs-lookup"><span data-stu-id="08e94-114">For more information, see [Parsing XML (Visual Basic)](parsing-xml.md).</span></span>  
  
- <span data-ttu-id="08e94-115">einen <xref:System.Xml.XmlReader> verwenden, um die Struktur aufzufüllen</span><span class="sxs-lookup"><span data-stu-id="08e94-115">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="08e94-116">Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span><span class="sxs-lookup"><span data-stu-id="08e94-116">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
- <span data-ttu-id="08e94-117">mit der <xref:System.Xml.XmlWriter>-Methode einen Writer erstellen, den Writer an das Modul übergeben und dann den in den <xref:System.Xml.Linq.XContainer.CreateWriter%2A> geschriebenen Inhalt zum Auffüllen der XML-Struktur verwenden, sofern ein Modul vorhanden ist, das Inhalt in einen <xref:System.Xml.XmlWriter> schreiben kann</span><span class="sxs-lookup"><span data-stu-id="08e94-117">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="08e94-118">Die verbreitetste Variante, eine XML-Struktur zu erstellen, sieht aber wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="08e94-118">However, the most common way to create an XML tree is as follows:</span></span>  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 <span data-ttu-id="08e94-119">Bei einer weiteren häufig verwendeten Technik zum Erstellen einer XML-Struktur wird die XML-Struktur anhand der Ergebnisse einer LINQ-Abfrage aufgefüllt, wie im folgenden Beispiel dargestellt wird:</span><span class="sxs-lookup"><span data-stu-id="08e94-119">Another very common technique for creating an XML tree involves using the results of a LINQ query to populate an XML tree, as shown in the following example:</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where el.Value > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 <span data-ttu-id="08e94-120">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="08e94-120">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a><span data-ttu-id="08e94-121">Serialisieren von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="08e94-121">Serializing XML Trees</span></span>  
 <span data-ttu-id="08e94-122">Sie können die XML-Struktur in eine <xref:System.IO.File>, in einen <xref:System.IO.TextWriter> oder in einen <xref:System.Xml.XmlWriter> serialisieren.</span><span class="sxs-lookup"><span data-stu-id="08e94-122">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="08e94-123">Weitere Informationen finden Sie unter [Serialisieren von XML-Strukturen (Visual Basic)](serializing-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="08e94-123">For more information, see [Serializing XML Trees (Visual Basic)](serializing-xml-trees.md).</span></span>  
  
### <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="08e94-124">Abrufen von XML-Daten über Achsenmethoden</span><span class="sxs-lookup"><span data-stu-id="08e94-124">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="08e94-125">Mit Achsenmethoden können Sie Attribute, untergeordnete Elemente, Nachfolgerelemente und Vorgängerelemente abrufen.</span><span class="sxs-lookup"><span data-stu-id="08e94-125">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="08e94-126">LINQ-Abfragen verwenden Achsenmethoden und bieten verschiedene flexible und leistungsstarke Möglichkeiten zum Navigieren durch eine XML-Struktur und zu deren Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="08e94-126">LINQ queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="08e94-127">Weitere Informationen finden Sie unter [LINQ to XML-Achsen (Visual Basic)](linq-to-xml-axes.md).</span><span class="sxs-lookup"><span data-stu-id="08e94-127">For more information, see [LINQ to XML Axes (Visual Basic)](linq-to-xml-axes.md).</span></span>  
  
### <a name="querying-xml-trees"></a><span data-ttu-id="08e94-128">Abfragen von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="08e94-128">Querying XML Trees</span></span>  
 <span data-ttu-id="08e94-129">Sie können LINQ-Abfragen schreiben, die Daten aus einer XML-Struktur abrufen.</span><span class="sxs-lookup"><span data-stu-id="08e94-129">You can write LINQ queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="08e94-130">Weitere Informationen finden Sie unter [Querying XML Trees (Visual Basic)](querying-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="08e94-130">For more information, see [Querying XML Trees (Visual Basic)](querying-xml-trees.md).</span></span>  
  
### <a name="modifying-xml-trees"></a><span data-ttu-id="08e94-131">Ändern von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="08e94-131">Modifying XML Trees</span></span>  
 <span data-ttu-id="08e94-132">Sie können ein Element auf unterschiedliche Weise ändern, z. B. durch Ändern seines Inhalts oder seiner Attribute.</span><span class="sxs-lookup"><span data-stu-id="08e94-132">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="08e94-133">Sie können ein Element auch aus seinem übergeordneten Element entfernen.</span><span class="sxs-lookup"><span data-stu-id="08e94-133">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="08e94-134">Weitere Informationen finden Sie unter [Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)](modifying-xml-trees-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="08e94-134">For more information, see [Modifying XML Trees (LINQ to XML) (Visual Basic)](modifying-xml-trees-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e94-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08e94-135">See also</span></span>

- [<span data-ttu-id="08e94-136">Übersicht über die LINQ to XML Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08e94-136">LINQ to XML Programming Overview (Visual Basic)</span></span>](linq-to-xml-programming-overview.md)
