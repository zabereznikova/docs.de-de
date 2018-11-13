---
title: Übersicht über LINQ to XML (C#)
ms.date: 10/30/2018
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
ms.openlocfilehash: 5e005343226b47fb843b817747ca03c49c28dbfc
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "43856620"
---
# <a name="linq-to-xml-overview-c"></a><span data-ttu-id="53488-102">Übersicht über LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="53488-102">LINQ to XML Overview (C#)</span></span>
<span data-ttu-id="53488-103">XML hat sich mittlerweile als hervorragende Möglichkeit durchgesetzt, Daten in einer Vielzahl von Kontexten zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="53488-103">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="53488-104">Sie finden XML beispielsweise im Internet, in Konfigurationsdateien, in Microsoft Office Word-Dateien und in Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="53488-104">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>  
  
 <span data-ttu-id="53488-105">Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] steht Ihnen ein topaktueller, völlig neu gestalteter Ansatz für die Programmierung mit XML zur Verfügung,</span><span class="sxs-lookup"><span data-stu-id="53488-105">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="53488-106">der die DOM-Funktionen (Dokumentobjektmodell) zum Ändern von Dokumenten im Arbeitsspeicher als auch die Unterstützung für [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdrücke in sich vereint.</span><span class="sxs-lookup"><span data-stu-id="53488-106">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="53488-107">Obwohl sich diese Abfrageausdrücke syntaktisch von XPath unterscheiden, bieten sie eine ähnliche Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="53488-107">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>  
  
## <a name="linq-to-xml-developers"></a><span data-ttu-id="53488-108">LINQ to XML-Entwickler</span><span class="sxs-lookup"><span data-stu-id="53488-108">LINQ to XML Developers</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="53488-109">eignet sich für ein breites Spektrum von Entwicklern.</span><span class="sxs-lookup"><span data-stu-id="53488-109">targets a variety of developers.</span></span> <span data-ttu-id="53488-110">Für einen ganz normalen Entwickler, der einfach eine Aufgabe erledigen möchte, vereinfacht [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] das Arbeiten mit XML, weil der Umgang mit Abfragen ähnlich wie in SQL ist.</span><span class="sxs-lookup"><span data-stu-id="53488-110">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="53488-111">Programmierer werden so innerhalb kurzer Zeit in die Lage versetzt, kompakte und dennoch leistungsfähige Abfragen in der Programmiersprache ihrer Wahl zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="53488-111">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>  
  
 <span data-ttu-id="53488-112">Professionelle Entwickler können mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ihre Produktivität deutlich steigern.</span><span class="sxs-lookup"><span data-stu-id="53488-112">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="53488-113">Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] muss weniger Code geschrieben werden, und dieser Code ist ausdrucksvoller, kompakter und leistungsstärker.</span><span class="sxs-lookup"><span data-stu-id="53488-113">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="53488-114">Sie können Abfrageausdrücke aus mehreren Datendomänen gleichzeitig verwenden.</span><span class="sxs-lookup"><span data-stu-id="53488-114">They can use query expressions from multiple data domains at the same time.</span></span>  
  
## <a name="what-is-linq-to-xml"></a><span data-ttu-id="53488-115">Was ist LINQ to XML?</span><span class="sxs-lookup"><span data-stu-id="53488-115">What Is LINQ to XML?</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="53488-116">ist eine LINQ-fähige XML-Programmierschnittstelle im Arbeitsspeicher, mit der Sie aus [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-Programmiersprachen heraus mit XML arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="53488-116">is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] programming languages.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="53488-117">ähnelt dem Dokumentobjektmodell (DOM) darin, dass das XML-Dokument im Arbeitsspeicher bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="53488-117">is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="53488-118">Sie können das Dokument abfragen und ändern, und nach dem Ändern können Sie es in einer Datei speichern oder es serialisieren und über das Internet versenden.</span><span class="sxs-lookup"><span data-stu-id="53488-118">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="53488-119">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] unterscheidet sich aber auch vom DOM: Es stellt ein neues Objektmodell bereit, das leichter und einfacher zu handhaben ist und das sich Sprachfunktionen in C# zunutze macht.</span><span class="sxs-lookup"><span data-stu-id="53488-119">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in C#.</span></span>  
  
 <span data-ttu-id="53488-120">Der wichtigste Vorteil von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] besteht in dessen Integration in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53488-120">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span></span> <span data-ttu-id="53488-121">Diese Integration ermöglicht es Ihnen, Abfragen für das XML-Dokument im Arbeitsspeicher zu schreiben, um Auflistungen von Elementen und Attributen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="53488-121">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="53488-122">Die Abfragefunktion von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist von ihrer Funktionalität her mit der von XPath und XQuery vergleichbar, die Syntax ist allerdings eine andere.</span><span class="sxs-lookup"><span data-stu-id="53488-122">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="53488-123">Die Integration von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] in C# bietet eine stärkere Typisierung, Syntaxüberprüfung bei der Kompilierung und verbesserte Debuggerunterstützung.</span><span class="sxs-lookup"><span data-stu-id="53488-123">The integration of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] in C# provides stronger typing, compile-time checking, and improved debugger support.</span></span>  
  
 <span data-ttu-id="53488-124">Ein weiterer Vorteil von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist die Fähigkeit, Abfrageergebnisse als Parameter für <xref:System.Xml.Linq.XElement>-Objektkonstruktoren und <xref:System.Xml.Linq.XAttribute>-Objektkonstruktoren zu verwenden. Dies ist ein sehr effizienter Ansatz zum Erstellen von XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="53488-124">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="53488-125">Diese Herangehensweise, die als *funktionale Konstruktion* bezeichnet wird, versetzt Entwickler in die Lage, XML-Strukturen problemlos von einer Form in eine andere zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="53488-125">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>  
  
 <span data-ttu-id="53488-126">Angenommen, Ihnen liegt eine typische XML-Bestellung, wie in [XML-Beispieldatei: Typische Bestellung (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md) vor.</span><span class="sxs-lookup"><span data-stu-id="53488-126">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span> <span data-ttu-id="53488-127">Durch die Verwendung von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie zum Abrufen des Attributwerts der Teilenummer für jedes Artikelelement im Auftrag die folgende Abfrage ausführen:</span><span class="sxs-lookup"><span data-stu-id="53488-127">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>  
  
```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load($"{purchaseOrderFilepath}");

IEnumerable<string> partNos =  from item in purchaseOrder.Descendants("Item")  
                               select (string) item.Attribute("PartNumber");  
``` 
<span data-ttu-id="53488-128">Diese kann im Methodensyntaxformat umgeschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="53488-128">This can be rewritten in method syntax form:</span></span>

```csharp
IEnumerable<string> partNos = purchaseOrder.Descendants("Item").Select(x => (string) x.Attribute("PartNumber"));
```

<span data-ttu-id="53488-129">Ein anderes Beispiel: Sie möchten, sortiert nach Teilenummer, eine Liste der Artikel abfragen, deren Wert über 100 Dollar liegt.</span><span class="sxs-lookup"><span data-stu-id="53488-129">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="53488-130">Zum Abfragen dieser Informationen könnten Sie die folgende Abfrage ausführen:</span><span class="sxs-lookup"><span data-stu-id="53488-130">To obtain this information, you could run the following query:</span></span>  
  
```csharp 
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load($"{purchaseOrderFilepath}");

IEnumerable<XElement> pricesByPartNos =  from item in purchaseOrder.Descendants("Item")  
                                 where (int) item.Element("Quantity") * (decimal) item.Element("USPrice") > 100  
                                 orderby (string)item.Element("PartNumber")  
                                 select item;  
```  

<span data-ttu-id="53488-131">Auch diese kann wieder im Methodensyntaxformat umgeschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="53488-131">Again, this can be rewritten in method syntax form:</span></span>

```csharp
IEnumerable<XElement> pricesByPartNos = purchaseOrder.Descendants("Item")
                                        .Where(item => (int)item.Element("Quantity") * (decimal)item.Element("USPrice") > 100)
                                        .OrderBy(order => order.Element("PartNumber"));
```

 <span data-ttu-id="53488-132">Zusätzlich zu diesen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Funktionen stellt [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eine verbesserte XML-Programmierschnittstelle bereit.</span><span class="sxs-lookup"><span data-stu-id="53488-132">In addition to these [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="53488-133">Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie Folgendes durchführen:</span><span class="sxs-lookup"><span data-stu-id="53488-133">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>  
  
-   <span data-ttu-id="53488-134">Laden Sie XML aus [Dateien](how-to-load-xml-from-a-file.md) oder [Streams](how-to-stream-xml-fragments-from-an-xmlreader.md).</span><span class="sxs-lookup"><span data-stu-id="53488-134">Load XML from [files](how-to-load-xml-from-a-file.md) or [streams](how-to-stream-xml-fragments-from-an-xmlreader.md).</span></span>  
  
-   <span data-ttu-id="53488-135">XML in Dateien oder Streams serialisieren</span><span class="sxs-lookup"><span data-stu-id="53488-135">Serialize XML to files or streams.</span></span>  
  
-   <span data-ttu-id="53488-136">XML mittels funktionaler Konstruktion von Grund auf neu erstellen</span><span class="sxs-lookup"><span data-stu-id="53488-136">Create XML from scratch by using functional construction.</span></span>  
  
-   <span data-ttu-id="53488-137">XML mit XPath-ähnlichen Achsen abfragen</span><span class="sxs-lookup"><span data-stu-id="53488-137">Query XML using XPath-like axes.</span></span>  
  
-   <span data-ttu-id="53488-138">XML-Strukturen im Arbeitsspeicher mit Methoden wie <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> und <xref:System.Xml.Linq.XElement.SetValue%2A> bearbeiten</span><span class="sxs-lookup"><span data-stu-id="53488-138">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>  
  
-   <span data-ttu-id="53488-139">XML-Strukturen mit XSD validieren</span><span class="sxs-lookup"><span data-stu-id="53488-139">Validate XML trees using XSD.</span></span>  
  
-   <span data-ttu-id="53488-140">XML-Strukturen mit einer Kombination aus diesen Funktionen von einer Form in eine andere transformieren</span><span class="sxs-lookup"><span data-stu-id="53488-140">Use a combination of these features to transform XML trees from one shape into another.</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="53488-141">Erstellen von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="53488-141">Creating XML Trees</span></span>  
 <span data-ttu-id="53488-142">Einer der bedeutendsten Vorteile beim Programmieren mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist die einfache Erstellung von XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="53488-142">One of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="53488-143">Wenn Sie z.B. eine kleine XML-Struktur erstellen möchten, können Sie einen Code wie im folgenden Beispiel schreiben:</span><span class="sxs-lookup"><span data-stu-id="53488-143">For example, to create a small XML tree, you can write code as follows:</span></span>  
  
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
  
 <span data-ttu-id="53488-144">Weitere Informationen finden Sie unter [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="53488-144">For more information, see [Creating XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53488-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53488-145">See Also</span></span>

- <xref:System.Xml.Linq>  
- [<span data-ttu-id="53488-146">Erste Schritte (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="53488-146">Getting Started (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
