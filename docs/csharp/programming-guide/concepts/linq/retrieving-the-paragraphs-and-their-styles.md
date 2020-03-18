---
title: Abrufen der Absätze und ihrer Stile (C#)
ms.date: 07/20/2015
ms.assetid: c2f767f8-57b1-4b4b-af04-89ffb1f7067d
ms.openlocfilehash: 47127b6f1d6bfaa0d8d93333882a0d0b59f1bae6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168296"
---
# <a name="retrieving-the-paragraphs-and-their-styles-c"></a><span data-ttu-id="f8225-102">Abrufen der Absätze und ihrer Stile (C#)</span><span class="sxs-lookup"><span data-stu-id="f8225-102">Retrieving the Paragraphs and Their Styles (C#)</span></span>
<span data-ttu-id="f8225-103">In diesem Beispiel schreiben wir eine Abfrage, die die Absatzknoten aus einem WordprocessingML-Dokument abruft.</span><span class="sxs-lookup"><span data-stu-id="f8225-103">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="f8225-104">Außerdem ermittelt es für jeden Absatz die verwendete Formatvorlage.</span><span class="sxs-lookup"><span data-stu-id="f8225-104">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="f8225-105">Diese Abfrage baut auf der Abfrage im vorherigen Beispiel auf, [Finding the Default Paragraph Style (C#) (Suchen der standardmäßigen Absatzformatvorlage (C#))](./finding-the-default-paragraph-style.md), in der die Standardformatvorlage aus der Liste der Formatvorlagen abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f8225-105">This query builds on the query in the previous example, [Finding the Default Paragraph Style (C#)](./finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="f8225-106">Diese Information wird benötigt, damit die Abfrage die Formatvorlagen der Absätze abrufen kann, für die keine Formatvorlage explizit festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f8225-106">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="f8225-107">Absatzformatvorlagen werden über das `w:pPr`-Element festgelegt. Wenn ein Absatz dieses Element nicht enthält, wird er mit der Standardformatvorlage formatiert.</span><span class="sxs-lookup"><span data-stu-id="f8225-107">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="f8225-108">In diesem Thema wird die Bedeutung einiger Teile der Abfrage erläutert, bevor die Abfrage im Kontext eines vollständigen, funktionstüchtigen Beispiels gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f8225-108">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8225-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8225-109">Example</span></span>  
 <span data-ttu-id="f8225-110">Die Abfrage verwendet zum Abrufen aller in einem Dokument vorhandenen Absätze und der zugehörigen Formatvorlagen die folgende Quelle:</span><span class="sxs-lookup"><span data-stu-id="f8225-110">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```csharp  
xDoc.Root.Element(w + "body").Descendants(w + "p")  
```  
  
 <span data-ttu-id="f8225-111">Dieser Ausdruck ähnelt der Quelle der Abfrage im vorherigen Beispiel, [Finding the Default Paragraph Style (C#), (Suchen der standardmäßigen Absatzformatvorlage (C#))](./finding-the-default-paragraph-style.md).</span><span class="sxs-lookup"><span data-stu-id="f8225-111">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (C#)](./finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="f8225-112">Der Hauptunterschied besteht darin, dass der Ausdruck anstelle der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse die <xref:System.Xml.Linq.XContainer.Elements%2A>-Achse verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8225-112">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="f8225-113">Die Abfrage verwendet die <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse, weil in Dokumenten mit Abschnitten die Absätze nicht die direkten untergeordneten Elemente des Textkörpers sind. Die Absätze befinden sich zwei Ebenen weiter unten in der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="f8225-113">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="f8225-114">Durch die Verwendung der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse funktioniert der Code unabhängig davon, ob das Dokument Abschnitte verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8225-114">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8225-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8225-115">Example</span></span>  
 <span data-ttu-id="f8225-116">Die Abfrage verwendet eine `let`-Klausel, um das Element zu bestimmen, das den Formatvorlagenknoten enthält.</span><span class="sxs-lookup"><span data-stu-id="f8225-116">The query uses a `let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="f8225-117">Wenn es kein Element gibt, wird `styleNode` auf `null` gesetzt.</span><span class="sxs-lookup"><span data-stu-id="f8225-117">If there is no element, then `styleNode` is set to `null`:</span></span>  
  
```csharp  
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()  
```  
  
 <span data-ttu-id="f8225-118">Die `let`-Klausel verwendet zuerst die <xref:System.Xml.Linq.XContainer.Elements%2A>-Achse, um nach allen Elementen mit dem Namen `pPr` zu suchen, und sucht dann mit der <xref:System.Xml.Linq.Extensions.Elements%2A>-Erweiterungsmethode nach allen untergeordneten Elementen mit dem Namen `pStyle`. Schließlich verwendet sie den <xref:System.Linq.Enumerable.FirstOrDefault%2A>-Standardabfrageoperator, um die Auflistung in ein Singleton umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="f8225-118">The `let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="f8225-119">Wenn die Auflistung leer ist, wird `styleNode` auf `null` gesetzt.</span><span class="sxs-lookup"><span data-stu-id="f8225-119">If the collection is empty, `styleNode` is set to `null`.</span></span> <span data-ttu-id="f8225-120">Dies ist eine sinnvolle Vorgehensweise, um nach dem `pStyle`-Nachfolgerknoten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="f8225-120">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="f8225-121">Beachten Sie dabei: Wenn der untergeordnete `pPr`-Knoten nicht existiert, löst der Code keine Ausnahme aus, sondern `styleNode` wird auf `null` gesetzt, was dem erwünschten Verhalten dieser `let`-Klausel entspricht.</span><span class="sxs-lookup"><span data-stu-id="f8225-121">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `null`, which is the desired behavior of this `let` clause.</span></span>  
  
 <span data-ttu-id="f8225-122">Die Abfrage projiziert eine Auflistung eines anonymen Typs mit zwei Membern, `StyleName` und `ParagraphNode`.</span><span class="sxs-lookup"><span data-stu-id="f8225-122">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8225-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8225-123">Example</span></span>  
 <span data-ttu-id="f8225-124">Dieses Beispiel verarbeitet ein WordprocessingML-Dokument, indem es die Absatzknoten aus einem WordprocessingML-Dokument abruft.</span><span class="sxs-lookup"><span data-stu-id="f8225-124">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="f8225-125">Außerdem ermittelt es für jeden Absatz die verwendete Formatvorlage.</span><span class="sxs-lookup"><span data-stu-id="f8225-125">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="f8225-126">Das Beispiel baut auf den vorherigen Beispielen dieses Lernprogramms auf.</span><span class="sxs-lookup"><span data-stu-id="f8225-126">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="f8225-127">Die neue Abfrage wird im Code unten durch entsprechende Kommentare gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f8225-127">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="f8225-128">Eine Anleitung zum Erstellen des Quelldokuments für dieses Beispiel finden Sie unter [Creating the Source Office Open XML Document (C#) (Erstellen eines Office Open-Quell-XML-Dokuments (C#))](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="f8225-128">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="f8225-129">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="f8225-129">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="f8225-130">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8225-130">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative), docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
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
  
// Following is the new query that finds all paragraphs in the  
// document and their styles.  
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
  
foreach (var p in paragraphs)  
    Console.WriteLine("StyleName:{0}", p.StyleName);  
```  
  
 <span data-ttu-id="f8225-131">Dieses Beispiel generiert bei Anwendung auf das in [Erstellen eines Office Open-Quell-XML-Dokuments (C#)](./creating-the-source-office-open-xml-document.md) beschriebene Dokument die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="f8225-131">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
```output  
StyleName:Heading1  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
```  
  
## <a name="next-steps"></a><span data-ttu-id="f8225-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f8225-132">Next Steps</span></span>  
 <span data-ttu-id="f8225-133">Im nächsten Thema, [Abrufen des Texts der Absätze (C#)](./retrieving-the-text-of-the-paragraphs.md), erstellen Sie eine Abfrage zum Abrufen des Texts der Absätze.</span><span class="sxs-lookup"><span data-stu-id="f8225-133">In the next topic, [Retrieving the Text of the Paragraphs (C#)](./retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8225-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8225-134">See also</span></span>

- [<span data-ttu-id="f8225-135">Tutorial: Manipulating Content in a WordprocessingML Document (C#) (Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#))</span><span class="sxs-lookup"><span data-stu-id="f8225-135">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
