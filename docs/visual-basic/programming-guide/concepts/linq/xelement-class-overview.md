---
title: "Übersicht über die XElement-Klasse (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
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
ms.openlocfilehash: 78a72effa021408943b9248546106c6fd655ac0b
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="xelement-class-overview-visual-basic"></a><span data-ttu-id="d6a9f-102">Übersicht über die XElement-Klasse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6a9f-102">XElement Class Overview (Visual Basic)</span></span>
<span data-ttu-id="d6a9f-103">Die <xref:System.Xml.Linq.XElement>-Klasse ist eine der wichtigsten Klassen in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d6a9f-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span> <span data-ttu-id="d6a9f-104">Sie stellt ein XML-Element dar.</span><span class="sxs-lookup"><span data-stu-id="d6a9f-104">It represents an XML element.</span></span> <span data-ttu-id="d6a9f-105">Diese Klasse kann zum Erstellen von Elementen, zum Ändern des Inhalts des Elements, zum Hinzufügen, Ändern oder Löschen untergeordneter Elemente, zum Hinzufügen von Attributen zu einem Element oder zum Serialisieren des Inhalts eines Elements in Textform verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6a9f-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="d6a9f-106">Sie können außerdem Interoperabilität mit anderen Klassen in <xref:System.Xml?displayProperty=fullName>, wie z. B. <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, und <xref:System.Xml.Xsl.XslCompiledTransform>.</xref:System.Xml.Xsl.XslCompiledTransform> </xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> </xref:System.Xml?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d6a9f-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=fullName>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="xelement-functionality"></a><span data-ttu-id="d6a9f-107">"XElement"-Funktionalität</span><span class="sxs-lookup"><span data-stu-id="d6a9f-107">XElement Functionality</span></span>  
 <span data-ttu-id="d6a9f-108">In diesem Thema wird beschrieben, die Funktionalität von der <xref:System.Xml.Linq.XElement>Klasse.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d6a9f-108">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
### <a name="constructing-xml-trees"></a><span data-ttu-id="d6a9f-109">Konstruieren von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="d6a9f-109">Constructing XML Trees</span></span>  
 <span data-ttu-id="d6a9f-110">Für das Konstruieren von XML-Strukturen stehen Ihnen verschiedene Möglichkeiten zur Verfügung. So können Sie z. B. Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="d6a9f-110">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
-   <span data-ttu-id="d6a9f-111">XML-Strukturen in Code konstruieren</span><span class="sxs-lookup"><span data-stu-id="d6a9f-111">You can construct an XML tree in code.</span></span> <span data-ttu-id="d6a9f-112">Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="d6a9f-112">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
-   <span data-ttu-id="d6a9f-113">Sie können XML-Daten aus verschiedenen Quellen, z. B. Analysieren einer <xref:System.IO.TextReader>, Textdateien oder Internetadressen (URLs).</xref:System.IO.TextReader></span><span class="sxs-lookup"><span data-stu-id="d6a9f-113">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="d6a9f-114">Weitere Informationen finden Sie unter [Analysieren von XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d6a9f-114">For more information, see [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).</span></span>  
  
-   <span data-ttu-id="d6a9f-115">Sie können eine <xref:System.Xml.XmlReader>um die Struktur aufzufüllen.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="d6a9f-115">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="d6a9f-116">Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="d6a9f-116">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
-   <span data-ttu-id="d6a9f-117">Wenn Sie ein Modul haben, den Inhalt zu schreiben, können ein <xref:System.Xml.XmlWriter>, können Sie die <xref:System.Xml.Linq.XContainer.CreateWriter%2A>-Methode einen Writer erstellen, den Writer an das Modul übergeben und verwenden Sie die Inhalte, um die die <xref:System.Xml.XmlWriter>Auffüllen der XML-Struktur.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XContainer.CreateWriter%2A> </xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="d6a9f-117">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="d6a9f-118">Die verbreitetste Variante, eine XML-Struktur zu erstellen, sieht aber wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d6a9f-118">However, the most common way to create an XML tree is as follows:</span></span>  
  
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
  
 <span data-ttu-id="d6a9f-119">Umfasst die anderen häufig verwendeten Technik zum Erstellen einer XML-Struktur mit den Ergebnissen einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfrage um eine XML-Struktur aufzufüllen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d6a9f-119">Another very common technique for creating an XML tree involves using the results of a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query to populate an XML tree, as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="d6a9f-120">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d6a9f-120">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a><span data-ttu-id="d6a9f-121">Serialisieren von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="d6a9f-121">Serializing XML Trees</span></span>  
 <span data-ttu-id="d6a9f-122">Sie können die XML-Struktur Serialisieren einer <xref:System.IO.File>, <xref:System.IO.TextWriter>, oder eine <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="d6a9f-122">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="d6a9f-123">Weitere Informationen finden Sie unter [Serialisieren von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="d6a9f-123">For more information, see [Serializing XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).</span></span>  
  
### <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="d6a9f-124">Abrufen von XML-Daten über Achsenmethoden</span><span class="sxs-lookup"><span data-stu-id="d6a9f-124">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="d6a9f-125">Mit Achsenmethoden können Sie Attribute, untergeordnete Elemente, Nachfolgerelemente und Vorgängerelemente abrufen.</span><span class="sxs-lookup"><span data-stu-id="d6a9f-125">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]<span data-ttu-id="d6a9f-126">-Abfragen verwenden Achsenmethoden und bieten verschiedene flexible und leistungsstarke Möglichkeiten zum Navigieren durch eine XML-Struktur und zu deren Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="d6a9f-126"> queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="d6a9f-127">Weitere Informationen finden Sie unter [LINQ to XML-Achsen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).</span><span class="sxs-lookup"><span data-stu-id="d6a9f-127">For more information, see [LINQ to XML Axes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).</span></span>  
  
### <a name="querying-xml-trees"></a><span data-ttu-id="d6a9f-128">Abfragen von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="d6a9f-128">Querying XML Trees</span></span>  
 <span data-ttu-id="d6a9f-129">Sie können schreiben [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfragen, die Daten aus einer XML-Struktur zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="d6a9f-129">You can write [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="d6a9f-130">Weitere Informationen finden Sie unter [Abfragen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="d6a9f-130">For more information, see [Querying XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).</span></span>  
  
### <a name="modifying-xml-trees"></a><span data-ttu-id="d6a9f-131">Ändern von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="d6a9f-131">Modifying XML Trees</span></span>  
 <span data-ttu-id="d6a9f-132">Sie können ein Element auf unterschiedliche Weise ändern, z. B. durch Ändern seines Inhalts oder seiner Attribute.</span><span class="sxs-lookup"><span data-stu-id="d6a9f-132">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="d6a9f-133">Sie können ein Element auch aus seinem übergeordneten Element entfernen.</span><span class="sxs-lookup"><span data-stu-id="d6a9f-133">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="d6a9f-134">Weitere Informationen finden Sie unter [Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d6a9f-134">For more information, see [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6a9f-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6a9f-135">See Also</span></span>  
 [<span data-ttu-id="d6a9f-136">LINQ to XML-Programmierung (Übersicht) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6a9f-136">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
