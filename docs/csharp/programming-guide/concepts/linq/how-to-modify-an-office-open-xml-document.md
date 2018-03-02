---
title: "Vorgehensweise: Ändern eines Office Open-XML-Dokuments (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 467d489c-2b1b-453b-a757-8ac180e82a96
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a6bfa60cce332deef2a72da836f96dbe37e65d2a
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2018
---
# <a name="how-to-modify-an-office-open-xml-document-c"></a><span data-ttu-id="711b9-102">Vorgehensweise: Ändern eines Office Open-XML-Dokuments (C#)</span><span class="sxs-lookup"><span data-stu-id="711b9-102">How to: Modify an Office Open XML Document (C#)</span></span>
<span data-ttu-id="711b9-103">Dieses Thema enthält ein Beispiel, das ein Office Open XML-Dokument öffnet, ändert und speichert.</span><span class="sxs-lookup"><span data-stu-id="711b9-103">This topic presents an example that opens an Office Open XML document, modifies it, and saves it.</span></span>  
  
 <span data-ttu-id="711b9-104">Weitere Informationen zu Office Open XML finden Sie unter [Open XML SDK](https://github.com/OfficeDev/Open-XML-SDK) (Open XML-SDK) und [www.ericwhite.com](http://ericwhite.com/).</span><span class="sxs-lookup"><span data-stu-id="711b9-104">For more information on Office Open XML, see [Open XML SDK](https://github.com/OfficeDev/Open-XML-SDK) and [www.ericwhite.com](http://ericwhite.com/).</span></span>  
  
## <a name="example"></a><span data-ttu-id="711b9-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="711b9-105">Example</span></span>  
 <span data-ttu-id="711b9-106">Dieses Beispiel sucht nach dem ersten Absatzelement im Dokument,</span><span class="sxs-lookup"><span data-stu-id="711b9-106">This example finds the first paragraph element in the document.</span></span> <span data-ttu-id="711b9-107">ruft den Text aus dem Absatz ab und löscht dann alle Textruns im Absatz.</span><span class="sxs-lookup"><span data-stu-id="711b9-107">It retrieves the text from the paragraph, and then deletes all text runs in the paragraph.</span></span> <span data-ttu-id="711b9-108">Daraufhin wird ein neuer Textrun erstellt, der aus dem Text des ersten Absatzes, umgewandelt in Großbuchstaben, besteht.</span><span class="sxs-lookup"><span data-stu-id="711b9-108">It creates a new text run that consists of the first paragraph text that has been converted to upper case.</span></span> <span data-ttu-id="711b9-109">Anschließend wird das geänderte XML in ein Open XML-Paket serialisiert und das Paket wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="711b9-109">It then serializes the changed XML into the Open XML package and closes it.</span></span>  
  
 <span data-ttu-id="711b9-110">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="711b9-110">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="711b9-111">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="711b9-111">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
  
        using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.ReadWrite))  
        {  
            PackageRelationship docPackageRelationship =  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
            if (docPackageRelationship != null)  
            {  
                Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
                  docPackageRelationship.TargetUri);  
                PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
                //  Load the document XML in the part into an XDocument instance.  
                XDocument xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
                //  Find the styles part. There will only be one.  
                PackageRelationship styleRelation =  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
                PackagePart stylePart = null;  
                XDocument styleDoc = null;  
  
                if (styleRelation != null)  
                {  
                    Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
                    stylePart = wdPackage.GetPart(styleUri);  
  
                    //  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
                }  
  
                XElement paraNode = xDoc  
                                    .Root  
                                    .Element(w + "body")  
                                    .Descendants(w + "p")  
                                    .FirstOrDefault();  
  
                string paraText = ParagraphText(paraNode);  
  
                // remove all text runs  
                paraNode.Descendants(w + "r").Remove();  
  
                paraNode.Add(  
                    new XElement(w + "r",  
                        new XElement(w + "t", paraText.ToUpper())  
                    )  
                );  
  
                //  Save the XML into the package  
                using (XmlWriter xw =  
                  XmlWriter.Create(documentPart.GetStream(FileMode.Create, FileAccess.Write)))  
                {  
                    xDoc.Save(xw);  
                }  
  
                Console.WriteLine("New first paragraph: >{0}<", paraText.ToUpper());  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="711b9-112">Wenn Sie `SampleDoc.docx` nach der Ausführung dieses Programms öffnen, sehen Sie, dass der erste Absatz des Dokuments in Großbuchstaben umgewandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="711b9-112">If you open `SampleDoc.docx` after running this program, you can see that this program converted the first paragraph in the document to upper case.</span></span>  
  
 <span data-ttu-id="711b9-113">Dieses Beispiel erzeugt bei Anwendung auf das in [Creating the Source Office Open XML Document (C#) (Erstellen eines Office Open-Quell-XML-Dokuments (C#))](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md) beschriebene Dokument die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="711b9-113">When run with the sample Open XML document described in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md), this example produces the following output:</span></span>  
  
```  
New first paragraph: >PARSING WORDPROCESSINGML WITH LINQ TO XML<  
```  
  
## <a name="see-also"></a><span data-ttu-id="711b9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="711b9-114">See Also</span></span>  
 [<span data-ttu-id="711b9-115">Erweiterte Abfragetechniken (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="711b9-115">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
