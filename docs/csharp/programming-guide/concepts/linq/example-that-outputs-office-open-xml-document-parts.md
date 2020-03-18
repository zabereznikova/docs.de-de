---
title: Beispiel für die Ausgabe von Office Open-XML-Dokumentbausteinen (C#)
ms.date: 07/20/2015
ms.assetid: 6cd37055-89b4-42e8-bf27-5a29717e35f3
ms.openlocfilehash: be4c0ba2ce2a007fa6e19a65d7d86854d85851c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "66486002"
---
# <a name="example-that-outputs-office-open-xml-document-parts-c"></a><span data-ttu-id="1fc22-102">Beispiel für die Ausgabe von Office Open-XML-Dokumentbausteinen (C#)</span><span class="sxs-lookup"><span data-stu-id="1fc22-102">Example that Outputs Office Open XML Document Parts (C#)</span></span>
<span data-ttu-id="1fc22-103">In diesem Thema wird gezeigt, wie Sie ein Office Open XML-Dokument öffnen und auf Teile davon zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1fc22-103">This topic shows how to open an Office Open XML document and access parts within it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fc22-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1fc22-104">Example</span></span>  
 <span data-ttu-id="1fc22-105">Das folgende Beispiel öffnet ein Office Open XML-Dokument und gibt den Dokumentteil und den Formatvorlagenteil auf der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="1fc22-105">The following example opens an Office Open XML document, and prints the document part and the style part to the console.</span></span>  
  
 <span data-ttu-id="1fc22-106">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="1fc22-106">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="1fc22-107">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="1fc22-107">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
