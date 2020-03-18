---
title: Suchen von Text in Word-Dokumenten (C#)
ms.date: 07/20/2015
ms.assetid: 82f86677-560b-49dc-a089-610409939b2a
ms.openlocfilehash: 173472b9dbd669476c3e5529655d111b88b0dba2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70205394"
---
# <a name="finding-text-in-word-documents-c"></a><span data-ttu-id="5b987-102">Suchen von Text in Word-Dokumenten (C#)</span><span class="sxs-lookup"><span data-stu-id="5b987-102">Finding Text in Word Documents (C#)</span></span>
<span data-ttu-id="5b987-103">In diesem Thema werden die vorherigen Abfragen so erweitert, dass sie etwas Sinnvolles tun, nämlich alle Stellen im Dokument zu finden, an denen eine bestimmte Zeichenfolge vorkommt.</span><span class="sxs-lookup"><span data-stu-id="5b987-103">This topic extends the previous queries to do something useful: find all occurrences of a string in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b987-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5b987-104">Example</span></span>  
 <span data-ttu-id="5b987-105">Dieses Beispiel verarbeitet ein WordprocessingML-Dokument, um alle Vorkommnisse eines bestimmten Textstücks im Dokument zu finden.</span><span class="sxs-lookup"><span data-stu-id="5b987-105">This example processes a WordprocessingML document, to find all the occurrences of a specific piece of text in the document.</span></span> <span data-ttu-id="5b987-106">Dazu wird eine Abfrage verwendet, die nach der Zeichenfolge "Hello" sucht.</span><span class="sxs-lookup"><span data-stu-id="5b987-106">To do this, we use a query that finds the string "Hello".</span></span> <span data-ttu-id="5b987-107">Das Beispiel baut auf den vorherigen Beispielen dieses Lernprogramms auf.</span><span class="sxs-lookup"><span data-stu-id="5b987-107">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="5b987-108">Die neue Abfrage wird im Code unten durch entsprechende Kommentare gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="5b987-108">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="5b987-109">Eine Anleitung zum Erstellen des Quelldokuments für dieses Beispiel finden Sie unter [Creating the Source Office Open XML Document (C#) (Erstellen eines Office Open-Quell-XML-Dokuments (C#))](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="5b987-109">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="5b987-110">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="5b987-110">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="5b987-111">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b987-111">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
  
        // Following is the new query that retrieves all paragraphs  
        // that have specific text in them.  
        var helloParagraphs =  
            from para in paraWithText  
            where para.Text.Contains("Hello")  
            select new  
            {  
                ParagraphNode = para.ParagraphNode,  
                StyleName = para.StyleName,  
                Text = para.Text  
            };  
  
        foreach (var p in helloParagraphs)  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
    }  
}  
```  
  
 <span data-ttu-id="5b987-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5b987-112">This example produces the following output:</span></span>  
  
```output  
StyleName:Code >        Console.WriteLine("Hello World");<  
StyleName:Code >Hello World<  
```  
  
 <span data-ttu-id="5b987-113">Sie können die Suche natürlich auch so ändern, dass nach Zeilen gesucht wird, die mit einer bestimmten Formatvorlage formatiert sind.</span><span class="sxs-lookup"><span data-stu-id="5b987-113">You can, of course, modify the search so that it searches for lines with a specific style.</span></span> <span data-ttu-id="5b987-114">Die folgende Abfrage sucht nach allen Leerzeilen, die mit der Formatvorlage <legacyBold>Code</legacyBold> formatiert sind:</span><span class="sxs-lookup"><span data-stu-id="5b987-114">The following query finds all blank lines that have the Code style:</span></span>  
  
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
  
        // Retrieve all paragraphs that have no text and are styled Code.  
        var blankCodeParagraphs =  
            from para in paraWithText  
            where para.Text == "" && para.StyleName == "Code"  
            select new  
            {  
                ParagraphNode = para.ParagraphNode,  
                StyleName = para.StyleName,  
                Text = para.Text  
            };  
  
        foreach (var p in blankCodeParagraphs)  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
    }  
}  
```  
  
 <span data-ttu-id="5b987-115">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5b987-115">This example produces the following output:</span></span>  
  
```output  
StyleName:Code ><  
```  
  
 <span data-ttu-id="5b987-116">Natürlich kann dieses Beispiel auf vielfältige Weise erweitert und angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="5b987-116">Of course, this example could be enhanced in a number of ways.</span></span> <span data-ttu-id="5b987-117">So ist es z. B. möglich, für die Suche nach Text reguläre Ausdrücke zu verwenden, alle Word-Dateien in einem bestimmten Verzeichnis zu durchlaufen usw.</span><span class="sxs-lookup"><span data-stu-id="5b987-117">For example, we could use regular expressions to search for text, we could iterate through all the Word files in a particular directory, and so on.</span></span>  
  
 <span data-ttu-id="5b987-118">Hinsichtlich der Arbeitsgeschwindigkeit gibt es keine wesentlichen Unterschiede zwischen dem Beispiel in der angegebenen Form und dem Beispiel, wenn es als einzelne Abfrage geschrieben worden wäre.</span><span class="sxs-lookup"><span data-stu-id="5b987-118">Note that this example performs approximately as well as if it were written as a single query.</span></span> <span data-ttu-id="5b987-119">Da die Abfragen mit verzögerter Auswertung implementiert werden, geben sie ihre Ergebnisse auch erst dann zurück, wenn sie die Iteration durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="5b987-119">Because each query is implemented in a lazy, deferred fashion, each query does not yield its results until the query is iterated.</span></span> <span data-ttu-id="5b987-120">Weitere Informationen zur Ausführung und verzögerten Auswertung finden Sie unter [Deferred Execution and Lazy Evaluation in LINQ to XML (C#) (Verzögerte Ausführung und Auswertung in LINQ to XML (C#))](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5b987-120">For more information about execution and lazy evaluation, see [Deferred Execution and Lazy Evaluation in LINQ to XML (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5b987-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5b987-121">Next Steps</span></span>  
 <span data-ttu-id="5b987-122">Der nächste Abschnitt enthält ausführlichere Informationen zu WordprocessingML-Dokumenten:</span><span class="sxs-lookup"><span data-stu-id="5b987-122">The next section provides more information about WordprocessingML documents:</span></span>  
  
- [<span data-ttu-id="5b987-123">Details of Office Open XML WordprocessingML Documents (C#) (Details eines Office Open XML-WordprocessingML-Dokuments (C#))</span><span class="sxs-lookup"><span data-stu-id="5b987-123">Details of Office Open XML WordprocessingML Documents (C#)</span></span>](./wordprocessingml-document-with-styles.md)  
  
## <a name="see-also"></a><span data-ttu-id="5b987-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b987-124">See also</span></span>

- [<span data-ttu-id="5b987-125">Tutorial: Manipulating Content in a WordprocessingML Document (C#) (Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#))</span><span class="sxs-lookup"><span data-stu-id="5b987-125">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
- [<span data-ttu-id="5b987-126">Refactoring mit einer reinen Funktion (C#)</span><span class="sxs-lookup"><span data-stu-id="5b987-126">Refactoring Using a Pure Function (C#)</span></span>](./refactoring-using-a-pure-function.md)
- [<span data-ttu-id="5b987-127">Deferred Execution and Lazy Evaluation in LINQ to XML (C#) (Verzögerte Ausführung und Auswertung in LINQ to XML (C#))</span><span class="sxs-lookup"><span data-stu-id="5b987-127">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
