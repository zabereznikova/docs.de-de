---
title: Refactoring mithilfe einer reinen Funktion (C#)
ms.date: 07/20/2015
ms.assetid: a3416a45-9e12-4e4a-9747-897f06eef510
ms.openlocfilehash: f264a0028ed265a5a4fbe1dc32f430c648724c20
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253076"
---
# <a name="refactoring-using-a-pure-function-c"></a><span data-ttu-id="c11e1-102">Refactoring mithilfe einer reinen Funktion (C#)</span><span class="sxs-lookup"><span data-stu-id="c11e1-102">Refactoring Using a Pure Function (C#)</span></span>
<span data-ttu-id="c11e1-103">Das folgende Beispiel gestaltet das vorherige Beispiel, [Refactoring Using an Extension Method (Refactoring mit einer Erweiterungsmethode (C#))](./refactoring-using-an-extension-method.md) so um, dass es eine reine Funktion verwendet. In diesem Beispiel wird der Code, der den Text eines Absatzes ermitteln soll, in die reine statische Methode `ParagraphText` verschoben.</span><span class="sxs-lookup"><span data-stu-id="c11e1-103">The following example refactors the previous example, [Refactoring Using an Extension Method (C#)](./refactoring-using-an-extension-method.md), to use a pure function In this example, the code to find the text of a paragraph is moved to the pure static method `ParagraphText`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c11e1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c11e1-104">Example</span></span>  
 <span data-ttu-id="c11e1-105">Dieses Beispiel verarbeitet ein WordprocessingML-Dokument, indem es die Absatzknoten aus einem WordprocessingML-Dokument abruft.</span><span class="sxs-lookup"><span data-stu-id="c11e1-105">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="c11e1-106">Außerdem ermittelt es für jeden Absatz die verwendete Formatvorlage.</span><span class="sxs-lookup"><span data-stu-id="c11e1-106">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="c11e1-107">Das Beispiel baut auf den vorherigen Beispielen dieses Lernprogramms auf.</span><span class="sxs-lookup"><span data-stu-id="c11e1-107">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="c11e1-108">Der umgestaltete Code wird im Code durch entsprechende Kommentare gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="c11e1-108">The refactored code is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="c11e1-109">Eine Anleitung zum Erstellen des Quelldokuments für dieses Beispiel finden Sie unter [Creating the Source Office Open XML Document (C#) (Erstellen eines Office Open-Quell-XML-Dokuments (C#))](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="c11e1-109">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="c11e1-110">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="c11e1-110">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="c11e1-111">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="c11e1-111">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
    // This is a new method that assembles the paragraph text.  
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
                    Uri styleUri = PackUriHelper.ResolvePartUri(documentUri,  
                      styleRelation.TargetUri);  
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
  
        foreach (var p in paraWithText)  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
    }  
}  
```  
  
 <span data-ttu-id="c11e1-112">Dieses Beispiel erzeugt dieselbe Ausgabe wie vor dem Refactoring:</span><span class="sxs-lookup"><span data-stu-id="c11e1-112">This example produces the same output as before the refactoring:</span></span>  
  
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
  
### <a name="next-steps"></a><span data-ttu-id="c11e1-113">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c11e1-113">Next Steps</span></span>  
 <span data-ttu-id="c11e1-114">Im nächsten Beispiel wird gezeigt, wie Sie XML in eine andere Form projizieren können:</span><span class="sxs-lookup"><span data-stu-id="c11e1-114">The next example shows how to project XML into a different shape:</span></span>  
  
- [<span data-ttu-id="c11e1-115">Projecting XML in a Different Shape (C#) (Projektieren von XML in eine andere Form (C#))</span><span class="sxs-lookup"><span data-stu-id="c11e1-115">Projecting XML in a Different Shape (C#)</span></span>](./projecting-xml-in-a-different-shape.md)  
  
## <a name="see-also"></a><span data-ttu-id="c11e1-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c11e1-116">See also</span></span>

- [<span data-ttu-id="c11e1-117">Tutorial: Manipulating Content in a WordprocessingML Document (C#) (Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#))</span><span class="sxs-lookup"><span data-stu-id="c11e1-117">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
- [<span data-ttu-id="c11e1-118">Refactoring mit einer Erweiterungsmethode (C#)</span><span class="sxs-lookup"><span data-stu-id="c11e1-118">Refactoring Using an Extension Method (C#)</span></span>](./refactoring-using-an-extension-method.md)
- [<span data-ttu-id="c11e1-119">Refactoring Into Pure Functions (Refactoring in reine Funktionen (C#))</span><span class="sxs-lookup"><span data-stu-id="c11e1-119">Refactoring Into Pure Functions (C#)</span></span>](./refactoring-into-pure-functions.md)
