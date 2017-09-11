---
title: "LINQ to XML-Übersicht (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
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
ms.openlocfilehash: 4732aaa64119ba98ab11205e8c93dd8d3eb62d4b
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="linq-to-xml-overview-visual-basic"></a><span data-ttu-id="1b0f5-102">LINQ to XML-Übersicht (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b0f5-102">LINQ to XML Overview (Visual Basic)</span></span>
<span data-ttu-id="1b0f5-103">XML hat sich mittlerweile als hervorragende Möglichkeit durchgesetzt, Daten in einer Vielzahl von Kontexten zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-103">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="1b0f5-104">Sie finden XML beispielsweise im Internet, in Konfigurationsdateien, in Microsoft Office Word-Dateien und in Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-104">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>  
  
 <span data-ttu-id="1b0f5-105">Mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] steht Ihnen ein topaktueller, völlig neu gestalteter Ansatz für die Programmierung mit XML zur Verfügung,</span><span class="sxs-lookup"><span data-stu-id="1b0f5-105">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="1b0f5-106">der die DOM-Funktionen (Dokumentobjektmodell) zum Ändern von Dokumenten im Arbeitsspeicher als auch die Unterstützung für [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfrageausdrücke in sich vereint.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-106">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query expressions.</span></span> <span data-ttu-id="1b0f5-107">Obwohl sich diese Abfrageausdrücke syntaktisch von XPath unterscheiden, bieten sie eine ähnliche Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-107">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>  
  
## <a name="linq-to-xml-developers"></a><span data-ttu-id="1b0f5-108">LINQ to XML-Entwickler</span><span class="sxs-lookup"><span data-stu-id="1b0f5-108">LINQ to XML Developers</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="1b0f5-109"> eignet sich für ein breites Spektrum von Entwicklern.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-109"> targets a variety of developers.</span></span> <span data-ttu-id="1b0f5-110">Für einen ganz normalen Entwickler, der einfach eine Aufgabe erledigen möchte, vereinfacht [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] das Arbeiten mit XML, weil der Umgang mit Abfragen ähnlich wie in SQL ist.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-110">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="1b0f5-111">Programmierer werden so innerhalb kurzer Zeit in die Lage versetzt, kompakte und dennoch leistungsfähige Abfragen in der Programmiersprache ihrer Wahl zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-111">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>  
  
 <span data-ttu-id="1b0f5-112">Professionelle Entwickler können mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ihre Produktivität deutlich steigern.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-112">Professional developers can use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="1b0f5-113">Mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] muss weniger Code geschrieben werden, und dieser Code ist ausdrucksvoller, kompakter und leistungsstärker.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-113">With [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="1b0f5-114">Sie können Abfrageausdrücke aus mehreren Datendomänen gleichzeitig verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-114">They can use query expressions from multiple data domains at the same time.</span></span>  
  
## <a name="what-is-linq-to-xml"></a><span data-ttu-id="1b0f5-115">Was ist LINQ to XML?</span><span class="sxs-lookup"><span data-stu-id="1b0f5-115">What Is LINQ to XML?</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="1b0f5-116"> ist eine LINQ-fähige XML-Programmierschnittstelle im Arbeitsspeicher, mit der Sie aus [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]-Programmiersprachen heraus mit XML arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-116"> is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] programming languages.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="1b0f5-117">ist z. B. die (DOKUMENTOBJEKTMODELL) daraufhin das XML-Dokument in den Speicher.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-117"> is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="1b0f5-118">Sie können das Dokument abfragen und ändern, und nach dem Ändern können Sie es in einer Datei speichern oder es serialisieren und über das Internet versenden.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-118">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="1b0f5-119">Allerdings [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] unterscheidet sich von DOM: Es bietet ein neues Objektmodell, die umfangreich ist und einfacher zu handhaben und, die nutzt die Vorteile der Sprachfeatures in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-119">However, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in Visual Basic.</span></span>  
  
 <span data-ttu-id="1b0f5-120">Der wichtigste Vorteil von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] besteht in dessen Integration in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b0f5-120">The most important advantage of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is its integration with [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)].</span></span> <span data-ttu-id="1b0f5-121">Diese Integration ermöglicht es Ihnen, Abfragen für das XML-Dokument im Arbeitsspeicher zu schreiben, um Auflistungen von Elementen und Attributen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-121">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="1b0f5-122">Die Abfragefunktion von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ist von ihrer Funktionalität her mit der von XPath und XQuery vergleichbar, die Syntax ist allerdings eine andere.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-122">The query capability of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="1b0f5-123">Die Integration von [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] in Visual Basic bietet eine stärkere Typisierung, während der Kompilierung und verbesserte Debuggerunterstützung.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-123">The integration of [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] in Visual Basic provides stronger typing, compile-time checking, and improved debugger support.</span></span>  
  
 <span data-ttu-id="1b0f5-124">Ein weiterer Vorteil von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ist die Fähigkeit, Abfrageergebnisse als Parameter verwenden, <xref:System.Xml.Linq.XElement>und <xref:System.Xml.Linq.XAttribute>Objektkonstruktoren einen leistungsfähigen Ansatz zum Erstellen von XML-Strukturen.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1b0f5-124">Another advantage of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="1b0f5-125">Dieses Verfahren namens *funktionale Konstruktion*, ermöglicht es Entwicklern, die von einer Form in eine andere XML-Strukturen problemlos zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-125">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>  
  
 <span data-ttu-id="1b0f5-126">Angenommen, Sie müssen möglicherweise eine Standard-XML-Bestellung, wie in beschrieben [XML-Beispieldatei: Typische Bestellung (LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348).</span><span class="sxs-lookup"><span data-stu-id="1b0f5-126">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348).</span></span> <span data-ttu-id="1b0f5-127">Durch die Verwendung von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie zum Abrufen des Attributwerts der Teilenummer für jedes Artikelelement im Auftrag die folgende Abfrage ausführen:</span><span class="sxs-lookup"><span data-stu-id="1b0f5-127">By using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 <span data-ttu-id="1b0f5-128">Ein anderes Beispiel: Sie möchten, sortiert nach Teilenummer, eine Liste der Artikel abfragen, deren Wert über&100; Dollar liegt.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-128">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="1b0f5-129">Zum Abfragen dieser Informationen könnten Sie die folgende Abfrage ausführen:</span><span class="sxs-lookup"><span data-stu-id="1b0f5-129">To obtain this information, you could run the following query:</span></span>  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 <span data-ttu-id="1b0f5-130">Zusätzlich zu diesen [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Funktionen [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] bietet eine verbesserte XML-Programmierschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-130">In addition to these [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] capabilities, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="1b0f5-131">Mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie Folgendes durchführen:</span><span class="sxs-lookup"><span data-stu-id="1b0f5-131">Using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you can:</span></span>  
  
-   <span data-ttu-id="1b0f5-132">XML aus Dateien oder Streams laden</span><span class="sxs-lookup"><span data-stu-id="1b0f5-132">Load XML from files or streams.</span></span>  
  
-   <span data-ttu-id="1b0f5-133">XML in Dateien oder Streams serialisieren</span><span class="sxs-lookup"><span data-stu-id="1b0f5-133">Serialize XML to files or streams.</span></span>  
  
-   <span data-ttu-id="1b0f5-134">XML mittels funktionaler Konstruktion von Grund auf neu erstellen</span><span class="sxs-lookup"><span data-stu-id="1b0f5-134">Create XML from scratch by using functional construction.</span></span>  
  
-   <span data-ttu-id="1b0f5-135">XML mit XPath-ähnlichen Achsen abfragen</span><span class="sxs-lookup"><span data-stu-id="1b0f5-135">Query XML using XPath-like axes.</span></span>  
  
-   <span data-ttu-id="1b0f5-136">Bearbeiten Sie die XML-Struktur im Arbeitsspeicher mit Methoden wie z. B. <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, und <xref:System.Xml.Linq.XElement.SetValue%2A>.</xref:System.Xml.Linq.XElement.SetValue%2A> </xref:System.Xml.Linq.XNode.ReplaceWith%2A> </xref:System.Xml.Linq.XNode.Remove%2A> </xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="1b0f5-136">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>  
  
-   <span data-ttu-id="1b0f5-137">XML-Strukturen mit XSD validieren</span><span class="sxs-lookup"><span data-stu-id="1b0f5-137">Validate XML trees using XSD.</span></span>  
  
-   <span data-ttu-id="1b0f5-138">XML-Strukturen mit einer Kombination aus diesen Funktionen von einer Form in eine andere transformieren</span><span class="sxs-lookup"><span data-stu-id="1b0f5-138">Use a combination of these features to transform XML trees from one shape into another.</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="1b0f5-139">Erstellen von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="1b0f5-139">Creating XML Trees</span></span>  
 <span data-ttu-id="1b0f5-140">Einer der bedeutendsten Vorteile beim Programmieren mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ist die einfache Erstellung von XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-140">IOne of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="1b0f5-141">Beispielsweise können eine kleine XML-Struktur zu erstellen, Sie Code wie folgt schreiben:</span><span class="sxs-lookup"><span data-stu-id="1b0f5-141">For example, to create a small XML tree, you can write  code as follows:</span></span>  
  
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
  
 <span data-ttu-id="1b0f5-142">Die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Compiler übersetzt XML-Literale in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Methodenaufrufe.</span><span class="sxs-lookup"><span data-stu-id="1b0f5-142">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler translates XML literals into [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] method calls.</span></span>  
  
 <span data-ttu-id="1b0f5-143">Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="1b0f5-143">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0f5-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b0f5-144">See Also</span></span>  
 <span data-ttu-id="1b0f5-145"><xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="1b0f5-145"><xref:System.Xml.Linq></span></span>   
<span data-ttu-id="1b0f5-146"> [Erste Schritte (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="1b0f5-146"> [Getting Started (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md) </span></span>  
<span data-ttu-id="1b0f5-147"> [Übersicht über LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="1b0f5-147"> [Overview of LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md) </span></span>  
<span data-ttu-id="1b0f5-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span><span class="sxs-lookup"><span data-stu-id="1b0f5-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span></span>
