---
title: Abrufen des Texts der Absätze (C#)
description: Erfahren Sie, wie Sie LINQ-Abfragen verwenden, um den Text der einzelnen Absätze in einem WordprocessingML-Dokument als Zeichenfolge in C# abzurufen. Dieses Beispiel verwendet verkettete Abfragen.
ms.date: 07/20/2015
ms.assetid: 127d635e-e559-408f-90c8-2bb621ca50ac
ms.openlocfilehash: 58a07ab848307c886927815e4e49e90806f61346
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302593"
---
# <a name="retrieving-the-text-of-the-paragraphs-c"></a><span data-ttu-id="7c389-104">Abrufen des Texts der Absätze (C#)</span><span class="sxs-lookup"><span data-stu-id="7c389-104">Retrieving the Text of the Paragraphs (C#)</span></span>
<span data-ttu-id="7c389-105">Dieses Beispiel baut auf dem vorherigen Beispiel [Retrieving the Paragraphs and Their Styles (C#) (Abrufen der Absätze und deren Formate (C#))](./retrieving-the-paragraphs-and-their-styles.md) auf.</span><span class="sxs-lookup"><span data-stu-id="7c389-105">This example builds on the previous example, [Retrieving the Paragraphs and Their Styles (C#)](./retrieving-the-paragraphs-and-their-styles.md).</span></span> <span data-ttu-id="7c389-106">Dieses neue Beispiel ruft den Text jedes einzelnen Absatzes als Zeichenfolge ab</span><span class="sxs-lookup"><span data-stu-id="7c389-106">This new example retrieves the text of each paragraph as a string.</span></span>  
  
 <span data-ttu-id="7c389-107">Zum Abrufen des Texts fügt dieses Beispiel eine zusätzliche Abfrage hinzu, die die Auflistung der anonymen Typen durchläuft und eine neue Auflistung eines anonymen Typs unter Hinzufügung eines neuen Members, `Text`, projiziert</span><span class="sxs-lookup"><span data-stu-id="7c389-107">To retrieve the text, this example adds an additional query that iterates through the collection of anonymous types and projects a new collection of an anonymous type with the addition of a new member, `Text`.</span></span> <span data-ttu-id="7c389-108">Mithilfe des <xref:System.Linq.Enumerable.Aggregate%2A>-Standardabfrageoperators werden mehrere Zeichenfolgen zu einer Zeichenfolge verkettet.</span><span class="sxs-lookup"><span data-stu-id="7c389-108">It uses the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span>  
  
 <span data-ttu-id="7c389-109">Dieses Verfahren (erst eine Auflistung eines anonymen Typs projizieren und dann diese Auflistung zum Projizieren einer neuen Auflistung eines anonymen Typs verwenden) ist eine häufig verwendete und sinnvolle Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="7c389-109">This technique (that is, first projecting to a collection of an anonymous type, then using this collection to project to a new collection of an anonymous type) is a common and useful idiom.</span></span> <span data-ttu-id="7c389-110">Diese Abfrage hätte auch ohne Projizieren in den ersten anonymen Typ geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="7c389-110">This query could have been written without projecting to the first anonymous type.</span></span> <span data-ttu-id="7c389-111">Aufgrund der verzögerten Auswertung wird aber nicht allzu viel zusätzliche Rechenleistung beansprucht.</span><span class="sxs-lookup"><span data-stu-id="7c389-111">However, because of lazy evaluation, doing so does not use much additional processing power.</span></span> <span data-ttu-id="7c389-112">Die Ausdrucksweise erstellt zwar mehr kurzlebige Objekte auf dem Heap, dies führt aber nur zu unerheblichen Leistungseinbußen.</span><span class="sxs-lookup"><span data-stu-id="7c389-112">The idiom creates more short lived objects on the heap, but this does not substantially degrade performance.</span></span>  
  
 <span data-ttu-id="7c389-113">Natürlich wäre es auch möglich, eine einzelne Abfrage zu schreiben, die die Funktionalität zum Abrufen der Absätze, der Formatvorlagen der einzelnen Absätze und des Texts in den Absätzen enthält.</span><span class="sxs-lookup"><span data-stu-id="7c389-113">Of course, it would be possible to write a single query that contains the functionality to retrieve the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="7c389-114">Häufig ist es aber sinnvoll, eine kompliziertere Abfrage in mehrere Abfragen aufzuteilen, weil der resultierende Code dann modularer und einfacher zu verwalten ist.</span><span class="sxs-lookup"><span data-stu-id="7c389-114">However, it often is useful to break up a more complicated query into multiple queries because the resulting code is more modular and easier to maintain.</span></span> <span data-ttu-id="7c389-115">Wenn Sie einen Teil der Abfrage wiederverwenden müssen und die Abfragen auf diese Weise geschrieben sind, können Sie den entsprechenden Abfrageteil auch einfacher umgestalten.</span><span class="sxs-lookup"><span data-stu-id="7c389-115">Furthermore, if you need to reuse a portion of the query, it is easier to refactor if the queries are written in this manner.</span></span>  
  
 <span data-ttu-id="7c389-116">Diese miteinander verketteten Abfragen verwenden das Verarbeitungsmodell, das im Thema [Tutorial: Verketten von Abfragen (C#)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md) näher erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="7c389-116">These queries, which are chained together, use the processing model that is examined in detail in the topic [Tutorial: Chaining Queries Together (C#)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c389-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c389-117">Example</span></span>  
 <span data-ttu-id="7c389-118">Dieses Beispiel verarbeitet ein WordprocessingML-Dokument, indem es den Elementknoten, die Namen der Formatvorlagen und den Text der einzelnen Absätze bestimmt.</span><span class="sxs-lookup"><span data-stu-id="7c389-118">This example processes a WordprocessingML document, determining the element node, the style name, and the text of each paragraph.</span></span> <span data-ttu-id="7c389-119">Das Beispiel baut auf den vorherigen Beispielen dieses Lernprogramms auf.</span><span class="sxs-lookup"><span data-stu-id="7c389-119">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="7c389-120">Die neue Abfrage wird im Code unten durch entsprechende Kommentare gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="7c389-120">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="7c389-121">Eine Anleitung zum Erstellen des Quelldokuments für dieses Beispiel finden Sie unter [Creating the Source Office Open XML Document (C#) (Erstellen eines Office Open-Quell-XML-Dokuments (C#))](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="7c389-121">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="7c389-122">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="7c389-122">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="7c389-123">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c389-123">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship =  
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
          docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation =  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
string defaultStyle =
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
// Find all paragraphs in the document.  
var paragraphs =  
    from para in xDoc  
                 .Root  
                 .Element(w + "body")  
                 .Descendants(w + "p")  
    let styleNode = para  
                    .Elements(w + "pPr")  
                    .Elements(w + "pStyle")  
                    .FirstOrDefault()  
    select new  
    {  
        ParagraphNode = para,  
        StyleName = styleNode != null ?  
            (string)styleNode.Attribute(w + "val") :  
            defaultStyle  
    };  
  
// Following is the new query that retrieves the text of  
// each paragraph.  
var paraWithText =  
    from para in paragraphs  
    select new  
    {  
        ParagraphNode = para.ParagraphNode,  
        StyleName = para.StyleName,  
        Text = para  
               .ParagraphNode  
               .Elements(w + "r")  
               .Elements(w + "t")  
               .Aggregate(  
                   new StringBuilder(),  
                   (s, i) => s.Append((string)i),  
                   s => s.ToString()  
               )  
    };  
  
foreach (var p in paraWithText)  
    Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
```  
  
 <span data-ttu-id="7c389-124">Dieses Beispiel produziert bei Anwendung auf das in [Creating the Source Office Open XML Document (C#) (Erstellen eines Office Open-Quell-XML-Dokuments (C#))](./creating-the-source-office-open-xml-document.md) beschriebene Dokument die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7c389-124">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
```output  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >using System;<  
StyleName:Code ><  
StyleName:Code >class Program {<  
StyleName:Code >    public static void (string[] args) {<  
StyleName:Code >        Console.WriteLine("Hello World");<  
StyleName:Code >    }<  
StyleName:Code >}<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
## <a name="next-steps"></a><span data-ttu-id="7c389-125">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7c389-125">Next Steps</span></span>  
 <span data-ttu-id="7c389-126">Im nächsten Beispiel wird gezeigt, wie Sie zum Verketten mehrerer Zeichenfolgen zu einer einzelnen Zeichenfolge statt <xref:System.Linq.Enumerable.Aggregate%2A> eine Erweiterungsmethode verwenden können:</span><span class="sxs-lookup"><span data-stu-id="7c389-126">The next example shows how to use an extension method, instead of <xref:System.Linq.Enumerable.Aggregate%2A>, to concatenate multiple strings into a single string.</span></span>  
  
- [<span data-ttu-id="7c389-127">Refactoring mit einer Erweiterungsmethode (C#)</span><span class="sxs-lookup"><span data-stu-id="7c389-127">Refactoring Using an Extension Method (C#)</span></span>](./refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="7c389-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c389-128">See also</span></span>

- [<span data-ttu-id="7c389-129">Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#)</span><span class="sxs-lookup"><span data-stu-id="7c389-129">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](shape-of-wordprocessingml-documents.md)
- [<span data-ttu-id="7c389-130">Deferred Execution and Lazy Evaluation in LINQ to XML (C#) (Verzögerte Ausführung und Auswertung in LINQ to XML (C#))</span><span class="sxs-lookup"><span data-stu-id="7c389-130">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
