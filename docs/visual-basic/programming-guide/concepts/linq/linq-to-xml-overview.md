---
title: Übersicht über LINQ to XML
ms.date: 07/20/2015
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
ms.openlocfilehash: a30340e06a3f8eac9fe2b7718b14ba20363d682f
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636470"
---
# <a name="linq-to-xml-overview-visual-basic"></a><span data-ttu-id="d121b-102">Übersicht über LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d121b-102">LINQ to XML Overview (Visual Basic)</span></span>
<span data-ttu-id="d121b-103">XML hat sich mittlerweile als hervorragende Möglichkeit durchgesetzt, Daten in einer Vielzahl von Kontexten zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="d121b-103">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="d121b-104">Sie finden XML beispielsweise im Internet, in Konfigurationsdateien, in Microsoft Office Word-Dateien und in Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="d121b-104">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>  
  
 <span data-ttu-id="d121b-105">Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] steht Ihnen ein topaktueller, völlig neu gestalteter Ansatz für die Programmierung mit XML zur Verfügung,</span><span class="sxs-lookup"><span data-stu-id="d121b-105">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="d121b-106">Sie stellt die in-Memory-Funktionen für die Dokument Änderung des Dokumentobjektmodell (DOM) bereit und unterstützt LINQ-Abfrage Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="d121b-106">It provides the in-memory document-modification capabilities of the Document Object Model (DOM) and supports LINQ query expressions.</span></span> <span data-ttu-id="d121b-107">Obwohl sich diese Abfrageausdrücke syntaktisch von XPath unterscheiden, bieten sie eine ähnliche Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="d121b-107">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>  
  
## <a name="linq-to-xml-developers"></a><span data-ttu-id="d121b-108">LINQ to XML-Entwickler</span><span class="sxs-lookup"><span data-stu-id="d121b-108">LINQ to XML Developers</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="d121b-109">eignet sich für ein breites Spektrum von Entwicklern.</span><span class="sxs-lookup"><span data-stu-id="d121b-109">targets a variety of developers.</span></span> <span data-ttu-id="d121b-110">Für einen ganz normalen Entwickler, der einfach eine Aufgabe erledigen möchte, vereinfacht [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] das Arbeiten mit XML, weil der Umgang mit Abfragen ähnlich wie in SQL ist.</span><span class="sxs-lookup"><span data-stu-id="d121b-110">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="d121b-111">Programmierer werden so innerhalb kurzer Zeit in die Lage versetzt, kompakte und dennoch leistungsfähige Abfragen in der Programmiersprache ihrer Wahl zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d121b-111">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>  
  
 <span data-ttu-id="d121b-112">Professionelle Entwickler können mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ihre Produktivität deutlich steigern.</span><span class="sxs-lookup"><span data-stu-id="d121b-112">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="d121b-113">Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] muss weniger Code geschrieben werden, und dieser Code ist ausdrucksvoller, kompakter und leistungsstärker.</span><span class="sxs-lookup"><span data-stu-id="d121b-113">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="d121b-114">Sie können Abfrageausdrücke aus mehreren Datendomänen gleichzeitig verwenden.</span><span class="sxs-lookup"><span data-stu-id="d121b-114">They can use query expressions from multiple data domains at the same time.</span></span>  
  
## <a name="what-is-linq-to-xml"></a><span data-ttu-id="d121b-115">Was ist LINQ to XML?</span><span class="sxs-lookup"><span data-stu-id="d121b-115">What Is LINQ to XML?</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="d121b-116">ist eine LINQ-fähige XML-Programmierschnittstelle im Arbeitsspeicher, mit der Sie in .NET Framework-Programmiersprachen mit XML arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="d121b-116">is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the .NET Framework programming languages.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="d121b-117">ähnelt dem Dokumentobjektmodell (DOM) darin, dass das XML-Dokument im Arbeitsspeicher bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d121b-117">is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="d121b-118">Sie können das Dokument abfragen und ändern, und nach dem Ändern können Sie es in einer Datei speichern oder es serialisieren und über das Internet versenden.</span><span class="sxs-lookup"><span data-stu-id="d121b-118">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="d121b-119">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] unterscheidet sich jedoch vom Dom: Es stellt ein neues Objektmodell bereit, das weniger gewichtet und leichter zu arbeiten ist und die Sprachfunktionen in Visual Basic nutzt.</span><span class="sxs-lookup"><span data-stu-id="d121b-119">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in Visual Basic.</span></span>  
  
 <span data-ttu-id="d121b-120">Der wichtigste Vorteil von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist die Integration in Language-Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="d121b-120">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with Language-Integrated Query (LINQ).</span></span> <span data-ttu-id="d121b-121">Diese Integration ermöglicht es Ihnen, Abfragen für das XML-Dokument im Arbeitsspeicher zu schreiben, um Auflistungen von Elementen und Attributen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d121b-121">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="d121b-122">Die Abfragefunktion von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist von ihrer Funktionalität her mit der von XPath und XQuery vergleichbar, die Syntax ist allerdings eine andere.</span><span class="sxs-lookup"><span data-stu-id="d121b-122">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="d121b-123">Die Integration von LINQ in Visual Basic bietet eine stärkere Typisierung, Überprüfung der Kompilierzeit und verbesserte Debuggerunterstützung.</span><span class="sxs-lookup"><span data-stu-id="d121b-123">The integration of LINQ in Visual Basic provides stronger typing, compile-time checking, and improved debugger support.</span></span>  
  
 <span data-ttu-id="d121b-124">Ein weiterer Vorteil von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist die Fähigkeit, Abfrageergebnisse als Parameter für <xref:System.Xml.Linq.XElement>-Objektkonstruktoren und <xref:System.Xml.Linq.XAttribute>-Objektkonstruktoren zu verwenden. Dies ist ein sehr effizienter Ansatz zum Erstellen von XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="d121b-124">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="d121b-125">Diese Herangehensweise, die als *funktionale Konstruktion* bezeichnet wird, versetzt Entwickler in die Lage, XML-Strukturen problemlos von einer Form in eine andere zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="d121b-125">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>  
  
 <span data-ttu-id="d121b-126">Angenommen, Ihnen liegt eine typische XML-Bestellung, wie in [XML-Beispieldatei: Typische Bestellung (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md) vor.</span><span class="sxs-lookup"><span data-stu-id="d121b-126">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span> <span data-ttu-id="d121b-127">Durch die Verwendung von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie zum Abrufen des Attributwerts der Teilenummer für jedes Artikelelement im Auftrag die folgende Abfrage ausführen:</span><span class="sxs-lookup"><span data-stu-id="d121b-127">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 <span data-ttu-id="d121b-128">Ein anderes Beispiel: Sie möchten, sortiert nach Teilenummer, eine Liste der Artikel abfragen, deren Wert über 100 Dollar liegt.</span><span class="sxs-lookup"><span data-stu-id="d121b-128">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="d121b-129">Zum Abfragen dieser Informationen könnten Sie die folgende Abfrage ausführen:</span><span class="sxs-lookup"><span data-stu-id="d121b-129">To obtain this information, you could run the following query:</span></span>  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 <span data-ttu-id="d121b-130">Zusätzlich zu diesen LINQ-Funktionen bietet [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eine verbesserte XML-Programmierschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d121b-130">In addition to these LINQ capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="d121b-131">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bietet folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="d121b-131">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>  
  
- <span data-ttu-id="d121b-132">XML aus Dateien oder Streams laden</span><span class="sxs-lookup"><span data-stu-id="d121b-132">Load XML from files or streams.</span></span>  
  
- <span data-ttu-id="d121b-133">XML in Dateien oder Streams serialisieren</span><span class="sxs-lookup"><span data-stu-id="d121b-133">Serialize XML to files or streams.</span></span>  
  
- <span data-ttu-id="d121b-134">XML mittels funktionaler Konstruktion von Grund auf neu erstellen</span><span class="sxs-lookup"><span data-stu-id="d121b-134">Create XML from scratch by using functional construction.</span></span>  
  
- <span data-ttu-id="d121b-135">XML mit XPath-ähnlichen Achsen abfragen</span><span class="sxs-lookup"><span data-stu-id="d121b-135">Query XML using XPath-like axes.</span></span>  
  
- <span data-ttu-id="d121b-136">XML-Strukturen im Arbeitsspeicher mit Methoden wie <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> und <xref:System.Xml.Linq.XElement.SetValue%2A> bearbeiten</span><span class="sxs-lookup"><span data-stu-id="d121b-136">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>  
  
- <span data-ttu-id="d121b-137">XML-Strukturen mit XSD validieren</span><span class="sxs-lookup"><span data-stu-id="d121b-137">Validate XML trees using XSD.</span></span>  
  
- <span data-ttu-id="d121b-138">XML-Strukturen mit einer Kombination aus diesen Funktionen von einer Form in eine andere transformieren</span><span class="sxs-lookup"><span data-stu-id="d121b-138">Use a combination of these features to transform XML trees from one shape into another.</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="d121b-139">Erstellen von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="d121b-139">Creating XML Trees</span></span>  
 <span data-ttu-id="d121b-140">Einer der bedeutendsten Vorteile beim Programmieren mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist die einfache Erstellung von XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="d121b-140">IOne of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="d121b-141">Wenn Sie z. b. eine kleine XML-Struktur erstellen möchten, können Sie Code wie folgt schreiben:</span><span class="sxs-lookup"><span data-stu-id="d121b-141">For example, to create a small XML tree, you can write  code as follows:</span></span>  
  
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
  
 <span data-ttu-id="d121b-142">Der Visual Basic-Compiler übersetzt XML-Literale in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Methodenaufrufe.</span><span class="sxs-lookup"><span data-stu-id="d121b-142">The Visual Basic compiler translates XML literals into [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] method calls.</span></span>  
  
 <span data-ttu-id="d121b-143">Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="d121b-143">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d121b-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d121b-144">See also</span></span>

- <xref:System.Xml.Linq>
- [<span data-ttu-id="d121b-145">Erste Schritte (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="d121b-145">Getting Started (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
- [<span data-ttu-id="d121b-146">Übersicht über LINQ to XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d121b-146">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)
- [<span data-ttu-id="d121b-147">XML</span><span class="sxs-lookup"><span data-stu-id="d121b-147">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
