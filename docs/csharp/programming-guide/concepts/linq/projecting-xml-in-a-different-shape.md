---
title: Projektieren von XML in eine andere Form (C#)
description: Erfahren Sie, wie Sie XML in eine andere Form als das Quell-XML-Format projizieren. Sehen Sie sich ein Codebeispiel an, das Klassen aus der WindowsBase-Assembly verwendet.
ms.date: 07/20/2015
ms.assetid: 4cb6b14a-32dc-4a2a-813e-bf9368fa8d86
ms.openlocfilehash: 492c0671b6a81f7e6b8d5f93698f84b88b14bd23
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299096"
---
# <a name="projecting-xml-in-a-different-shape-c"></a><span data-ttu-id="e3ef5-104">Projektieren von XML in eine andere Form (C#)</span><span class="sxs-lookup"><span data-stu-id="e3ef5-104">Projecting XML in a Different Shape (C#)</span></span>
<span data-ttu-id="e3ef5-105">In diesem Thema wird anhand eines Beispiels gezeigt, wie Sie XML in eine andere Form als das Quell-XML projizieren können.</span><span class="sxs-lookup"><span data-stu-id="e3ef5-105">This topic shows an example of projecting XML that is in a different shape than the source XML.</span></span>  
  
 <span data-ttu-id="e3ef5-106">Viele typische XML-Transformationen bestehen aus verketteten Abfragen. Dies trifft auch auf dieses Beispiel zu.</span><span class="sxs-lookup"><span data-stu-id="e3ef5-106">Many typical XML transformations consist of chained queries, as in this example.</span></span> <span data-ttu-id="e3ef5-107">Üblicherweise wird mit einer bestimmten Form von XML begonnen, die Zwischenergebnisse werden als Auflistungen anonymer Typen oder benannter Typen projiziert und zum Schluss werden die Ergebnisse zurück in XML projiziert, das eine vollkommen andere Form als das Quell-XML besitzt.</span><span class="sxs-lookup"><span data-stu-id="e3ef5-107">It is common to start with some form of XML, project intermediate results as collections of anonymous types or named types, and then finally to project the results back into XML that is in an entirely different shape than the source XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3ef5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e3ef5-108">Example</span></span>  
 <span data-ttu-id="e3ef5-109">Dieses Beispiel verarbeitet ein WordprocessingML-Dokument, indem es die Absatzknoten aus einem WordprocessingML-Dokument abruft.</span><span class="sxs-lookup"><span data-stu-id="e3ef5-109">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="e3ef5-110">Außerdem identifiziert es die Formatvorlage und den Text der einzelnen Absätze.</span><span class="sxs-lookup"><span data-stu-id="e3ef5-110">It also identifies the style and text of each paragraph.</span></span> <span data-ttu-id="e3ef5-111">Schließlich projiziert das Beispiel XML mit einer anderen Form.</span><span class="sxs-lookup"><span data-stu-id="e3ef5-111">Finally, the example projects XML with a different shape.</span></span> <span data-ttu-id="e3ef5-112">Das Beispiel baut auf den vorherigen Beispielen dieses Lernprogramms auf.</span><span class="sxs-lookup"><span data-stu-id="e3ef5-112">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="e3ef5-113">Die neue Anweisung, die die Projektion ausführt, wird im Code unten durch entsprechende Kommentare gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e3ef5-113">The new statement that does the projection is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="e3ef5-114">Eine Anleitung zum Erstellen des Quelldokuments für dieses Beispiel finden Sie unter [Creating the Source Office Open XML Document (C#) (Erstellen eines Office Open-Quell-XML-Dokuments (C#))](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="e3ef5-114">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="e3ef5-115">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="e3ef5-115">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="e3ef5-116">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3ef5-116">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static string StringConcatenate(this IEnumerable<string> source)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item));  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate(this IEnumerable<string> source, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s).Append(separator);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item)).Append(separator);  
        return sb.ToString();  
    }  
}  
  
class Program  
{  
    public static string ParagraphText(XElement e)  
    {  
        XNamespace w = e.Name.Namespace;  
        return e  
               .Elements(w + "r")  
               .Elements(w + "t")  
               .StringConcatenate(element => (string)element);  
    }  
  
    static void Main(string[] args)  
    {  
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
                    Uri styleUri =  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
                    PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
                    //  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
                }  
            }  
        }  
  
        string defaultStyle =  
            (string)(  
                from style in styleDoc.Root.Elements(w + "style")  
                where (string)style.Attribute(w + "type") == "paragraph" &&  
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
  
        // Retrieve the text of each paragraph.  
        var paraWithText =  
            from para in paragraphs  
            select new  
            {  
                ParagraphNode = para.ParagraphNode,  
                StyleName = para.StyleName,  
                Text = ParagraphText(para.ParagraphNode)  
            };  
  
        // The following is the new code that projects XML in a new shape.  
        XElement root = new XElement("Root",  
            from p in paraWithText  
            select new XElement("Paragraph",  
                new XElement("StyleName", p.StyleName),  
                new XElement("Text", p.Text)  
            )  
        );  
  
        Console.WriteLine(root);  
    }  
}  
```  
  
 <span data-ttu-id="e3ef5-117">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e3ef5-117">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Paragraph>  
    <StyleName>Heading1</StyleName>  
    <Text>Parsing WordprocessingML with LINQ to XML</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text>The following example prints to the console.</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>using System;</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>class Program {</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>    public static void (string[] args) {</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>        Console.WriteLine("Hello World");</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>    }</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>}</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text>This example produces the following output:</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>Hello World</Text>  
  </Paragraph>  
</Root>  
```  
  
## <a name="next-steps"></a><span data-ttu-id="e3ef5-118">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e3ef5-118">Next Steps</span></span>  
 <span data-ttu-id="e3ef5-119">Im nächsten Beispiel werden Sie eine Abfrage erstellen, die sämtlichen Text in einem Word-Dokument ermittelt:</span><span class="sxs-lookup"><span data-stu-id="e3ef5-119">In the next example, you'll query to find all the text in a Word document:</span></span>  
  
- [<span data-ttu-id="e3ef5-120">Finding Text in Word Documents (C#) (Suchen von Text in Word-Dokumenten (C#))</span><span class="sxs-lookup"><span data-stu-id="e3ef5-120">Finding Text in Word Documents (C#)</span></span>](./finding-text-in-word-documents.md)  
  