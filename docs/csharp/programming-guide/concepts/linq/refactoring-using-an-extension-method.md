---
title: Refactoring mit einer Erweiterungsmethode (C#)
description: Erfahren Sie, wie Sie Code mithilfe einer Erweiterungsmethode umgestalten. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
ms.assetid: c5fc123d-af10-4a2f-b8e4-db921efb2639
ms.openlocfilehash: e786f0e1514156535fd6a6033e37ed8879e99709
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381943"
---
# <a name="refactoring-using-an-extension-method-c"></a><span data-ttu-id="ae2a4-104">Refactoring mit einer Erweiterungsmethode (C#)</span><span class="sxs-lookup"><span data-stu-id="ae2a4-104">Refactoring Using an Extension Method (C#)</span></span>
<span data-ttu-id="ae2a4-105">Dieses Beispiel baut auf dem vorhergehenden Beispiel, [Retrieving the Text of the Paragraphs (C#) (Abrufen des Textes der Absätze (C#))](./retrieving-the-text-of-the-paragraphs.md), auf. Es gestaltet die Verkettung von Zeichenfolgen mit einer reinen Funktion um, die als Erweiterungsmethode implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-105">This example builds on the previous example, [Retrieving the Text of the Paragraphs (C#)](./retrieving-the-text-of-the-paragraphs.md), by refactoring the concatenation of strings using a pure function that is implemented as an extension method.</span></span>  
  
 <span data-ttu-id="ae2a4-106">Im vorherigen Beispiel wurde zum Verketten mehrerer Zeichenfolgen zu einer Zeichenfolge der <xref:System.Linq.Enumerable.Aggregate%2A>-Standardabfrageoperator verwendet.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-106">The previous example used the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span> <span data-ttu-id="ae2a4-107">Bequemer ist es aber, dafür eine Erweiterungsmethode zu schreiben, weil die Abfrage dadurch kleiner und einfacher wird.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-107">However, it is more convenient to write an extension method to do this, because the resulting query smaller and more simple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae2a4-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ae2a4-108">Example</span></span>  
 <span data-ttu-id="ae2a4-109">Dieses Beispiel verarbeitet ein WordprocessingML-Dokument, indem es die Absätze, die Formatvorlagen der Absätze und den Text der einzelnen Absätze abruft.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-109">This example processes a WordprocessingML document, retrieving the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="ae2a4-110">Das Beispiel baut auf den vorherigen Beispielen dieses Lernprogramms auf.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-110">This example builds on the previous examples in this tutorial.</span></span>  
  
 <span data-ttu-id="ae2a4-111">Das Beispiel enthält mehrere Überladungen der `StringConcatenate`-Methode.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-111">The example contains multiple overloads of the `StringConcatenate` method.</span></span>  
  
 <span data-ttu-id="ae2a4-112">Eine Anleitung zum Erstellen des Quelldokuments für dieses Beispiel finden Sie unter [Creating the Source Office Open XML Document (C#) (Erstellen eines Office Open-Quell-XML-Dokuments (C#))](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="ae2a4-112">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="ae2a4-113">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-113">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="ae2a4-114">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-114">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
```  
  
## <a name="example"></a><span data-ttu-id="ae2a4-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ae2a4-115">Example</span></span>  
 <span data-ttu-id="ae2a4-116">Es gibt vier Überladungen der `StringConcatenate`-Methode.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-116">There are four overloads of the `StringConcatenate` method.</span></span> <span data-ttu-id="ae2a4-117">Eine Überladung nimmt einfach eine Auflistung von Zeichenfolgen und gibt eine einzelne Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-117">One overload simply takes a collection of strings and returns a single string.</span></span> <span data-ttu-id="ae2a4-118">Eine andere Überladung kann eine Auflistung eines beliebigen Typs und einen Delegat nehmen, der von einem Singleton der Auflistung in eine Zeichenfolge projiziert.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-118">Another overload can take a collection of any type, and a delegate that projects from a singleton of the collection to a string.</span></span> <span data-ttu-id="ae2a4-119">Es gibt zwei weitere Überladungen, die es Ihnen ermöglichen, eine Trennzeichenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-119">There are two more overloads that allow you to specify a separator string.</span></span>  
  
 <span data-ttu-id="ae2a4-120">Der folgende Code verwendet alle vier Überladungen:</span><span class="sxs-lookup"><span data-stu-id="ae2a4-120">The following code uses all four overloads.</span></span>  
  
```csharp  
string[] numbers = { "one", "two", "three" };  
  
Console.WriteLine("{0}", numbers.StringConcatenate());  
Console.WriteLine("{0}", numbers.StringConcatenate(":"));  
  
int[] intNumbers = { 1, 2, 3 };  
Console.WriteLine("{0}", intNumbers.StringConcatenate(i => i.ToString()));  
Console.WriteLine("{0}", intNumbers.StringConcatenate(i => i.ToString(), ":"));  
```  
  
 <span data-ttu-id="ae2a4-121">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ae2a4-121">This example produces the following output:</span></span>  
  
```output  
onetwothree  
one:two:three:  
123  
1:2:3:  
```  
  
## <a name="example"></a><span data-ttu-id="ae2a4-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ae2a4-122">Example</span></span>  
 <span data-ttu-id="ae2a4-123">Jetzt kann das Beispiel so geändert werden, dass es die neue Erweiterungsmethode nutzt:</span><span class="sxs-lookup"><span data-stu-id="ae2a4-123">Now, the example can be modified to take advantage of the new extension method:</span></span>  
  
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
                Text = para  
                       .ParagraphNode  
                       .Elements(w + "r")  
                       .Elements(w + "t")  
                       .StringConcatenate(e => (string)e)  
            };  
  
        foreach (var p in paraWithText)  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
    }  
}  
```  
  
 <span data-ttu-id="ae2a4-124">Dieses Beispiel generiert bei Anwendung auf das in [Erstellen eines Office Open-Quell-XML-Dokuments (C#)](./creating-the-source-office-open-xml-document.md) beschriebene Dokument die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-124">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
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
  
 <span data-ttu-id="ae2a4-125">Beachten Sie, dass dieses Refactoring eine Variante des Refactorings in eine reine Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-125">Note that this refactoring is a variant of refactoring into a pure function.</span></span> <span data-ttu-id="ae2a4-126">Das Umgestalten in reine Funktionen wird im nächsten Thema ausführlicher erläutert.</span><span class="sxs-lookup"><span data-stu-id="ae2a4-126">The next topic will introduce the idea of factoring into pure functions in more detail.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ae2a4-127">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ae2a4-127">Next Steps</span></span>  
 <span data-ttu-id="ae2a4-128">Im nächsten Beispiel wird gezeigt, wie dieser Code durch Verwendung von reinen Funktionen umgestaltet werden kann:</span><span class="sxs-lookup"><span data-stu-id="ae2a4-128">The next example shows how to refactor this code in another way, by using pure functions:</span></span>  
  
- [<span data-ttu-id="ae2a4-129">Refactoring mit einer reinen Funktion (C#)</span><span class="sxs-lookup"><span data-stu-id="ae2a4-129">Refactoring Using a Pure Function (C#)</span></span>](./refactoring-using-a-pure-function.md)
  
## <a name="see-also"></a><span data-ttu-id="ae2a4-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae2a4-130">See also</span></span>

- [<span data-ttu-id="ae2a4-131">Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#)</span><span class="sxs-lookup"><span data-stu-id="ae2a4-131">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
- [<span data-ttu-id="ae2a4-132">Refactoring in reine Funktionen (C#)</span><span class="sxs-lookup"><span data-stu-id="ae2a4-132">Refactoring Into Pure Functions (C#)</span></span>](./refactoring-into-pure-functions.md)
