---
title: "Suchen der standardmäßigen Absatzformatvorlage (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 834654837b5c7fc747b0df1ee9dc645664a77351
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="finding-the-default-paragraph-style-c"></a><span data-ttu-id="d3e8d-102">Suchen der standardmäßigen Absatzformatvorlage (C#)</span><span class="sxs-lookup"><span data-stu-id="d3e8d-102">Finding the Default Paragraph Style (C#)</span></span>
<span data-ttu-id="d3e8d-103">Die erste Aufgabe im Tutorial „Bearbeiten des Inhalts eines WordprocessingML-Dokuments“ besteht darin, die Standardabsatzformatvorlage im Dokument zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="d3e8d-103">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3e8d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d3e8d-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d3e8d-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3e8d-105">Description</span></span>  
 <span data-ttu-id="d3e8d-106">Das folgende Beispiel öffnet ein Office Open XML-WordprocessingML-Dokument, bestimmt den Dokument- und den Formatvorlagenteil des Pakets und führt dann eine Abfrage aus, um den Namen der Standardformatvorlage zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="d3e8d-106">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="d3e8d-107">Informationen zu Office Open-XML-Dokumentpaketen und deren Bestandteilen finden Sie unter [Details of Office Open XML WordprocessingML Documents (C#) (Details eines Office Open-XML-WordprocessingML-Dokuments (C#))](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="d3e8d-107">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (C#)](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span></span>  
  
 <span data-ttu-id="d3e8d-108">Die Abfrage sucht nach einem Knoten mit dem Namen `w:style`, der ein `w:type`-Attribut mit dem Wert "paragraph" und ein `w:default`-Attribut mit dem Wert "1" besitzt.</span><span class="sxs-lookup"><span data-stu-id="d3e8d-108">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="d3e8d-109">Da es nur einen XML-Knoten mit diesen Attributen gibt, verwendet die Abfrage den <xref:System.Linq.Enumerable.First%2A?displayProperty=fullName>-Operator, um eine Auflistung in ein Singleton umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="d3e8d-109">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=fullName> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="d3e8d-110">Dann ruft die Abfrage den Wert des Attributs mit dem Namen `w:styleId` ab.</span><span class="sxs-lookup"><span data-stu-id="d3e8d-110">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="d3e8d-111">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="d3e8d-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="d3e8d-112">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=fullName>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3e8d-112">It uses types in the <xref:System.IO.Packaging?displayProperty=fullName> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d3e8d-113">Code</span><span class="sxs-lookup"><span data-stu-id="d3e8d-113">Code</span></span>  
  
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
  
// The following query finds all the paragraphs that have the default style.  
string defaultStyle =   
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
Console.WriteLine("The default style is: {0}", defaultStyle);  
```  
  
### <a name="comments"></a><span data-ttu-id="d3e8d-114">Kommentare</span><span class="sxs-lookup"><span data-stu-id="d3e8d-114">Comments</span></span>  
 <span data-ttu-id="d3e8d-115">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d3e8d-115">This example produces the following output:</span></span>  
  
```  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="d3e8d-116">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d3e8d-116">Next Steps</span></span>  
 <span data-ttu-id="d3e8d-117">Im nächsten Beispiel erstellen Sie eine ähnliche Abfrage. Diese Abfrage sucht nach allen Absätzen eines Dokuments und deren Formatvorlagen:</span><span class="sxs-lookup"><span data-stu-id="d3e8d-117">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
-   [<span data-ttu-id="d3e8d-118">Retrieving the Paragraphs and Their Styles (C#) (Abrufen der Absätze und ihrer Formate (C#))</span><span class="sxs-lookup"><span data-stu-id="d3e8d-118">Retrieving the Paragraphs and Their Styles (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a><span data-ttu-id="d3e8d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3e8d-119">See Also</span></span>  
 [<span data-ttu-id="d3e8d-120">Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument</span><span class="sxs-lookup"><span data-stu-id="d3e8d-120">Tutorial: Manipulating Content in a WordprocessingML Document</span></span>](http://msdn.microsoft.com/library/2696355e-4f83-4eaf-91b2-baa721f42fb4)

