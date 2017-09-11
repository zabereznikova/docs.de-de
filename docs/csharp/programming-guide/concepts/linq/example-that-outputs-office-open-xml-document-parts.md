---
title: "Beispiel für die Ausgabe von Office Open-XML-Dokumentbausteinen (C#)"
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
ms.assetid: 6cd37055-89b4-42e8-bf27-5a29717e35f3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e7b2135a0894e1fa5a553552fa128809d740dea2
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="example-that-outputs-office-open-xml-document-parts-c"></a><span data-ttu-id="276af-102">Beispiel für die Ausgabe von Office Open-XML-Dokumentbausteinen (C#)</span><span class="sxs-lookup"><span data-stu-id="276af-102">Example that Outputs Office Open XML Document Parts (C#)</span></span>
<span data-ttu-id="276af-103">In diesem Thema wird gezeigt, wie Sie ein Office Open XML-Dokument öffnen und auf Teile davon zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="276af-103">This topic shows how to open an Office Open XML document and access parts within it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="276af-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="276af-104">Example</span></span>  
 <span data-ttu-id="276af-105">Das folgende Beispiel öffnet ein Office Open XML-Dokument und gibt den Dokumentteil und den Formatvorlagenteil auf der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="276af-105">The following example opens an Office Open XML document, and prints the document part and the style part to the console.</span></span>  
  
 <span data-ttu-id="276af-106">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="276af-106">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="276af-107">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=fullName>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="276af-107">It uses types in the <xref:System.IO.Packaging?displayProperty=fullName> namespace.</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
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
        XDocument xdoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        Console.WriteLine("TargetUri:{0}", docPackageRelationship.TargetUri);  
        Console.WriteLine("==================================================================");  
        Console.WriteLine(xdoc.Root);  
        Console.WriteLine();  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation =  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            XDocument styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
  
            Console.WriteLine("TargetUri:{0}", styleRelation.TargetUri);  
            Console.WriteLine("==================================================================");  
            Console.WriteLine(styleDoc.Root);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="276af-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="276af-108">See Also</span></span>  
 [<span data-ttu-id="276af-109">Details of Office Open XML WordprocessingML Documents (C#) (Details eines Office Open XML-WordprocessingML-Dokuments (C#))</span><span class="sxs-lookup"><span data-stu-id="276af-109">Details of Office Open XML WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)

