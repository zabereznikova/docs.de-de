---
title: 'Gewusst wie: Abfangen von Analysefehlern (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6065bb7656151392e4a5b7ad1078706284ba5616
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-catch-parsing-errors-visual-basic"></a><span data-ttu-id="9acf3-102">Gewusst wie: Abfangen von Analysefehlern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9acf3-102">How to: Catch Parsing Errors (Visual Basic)</span></span>
<span data-ttu-id="9acf3-103">In diesem Thema wird gezeigt, wie nicht wohlgeformter oder ungültiger XML-Code erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9acf3-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="9acf3-104">wird mithilfe von <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> implementiert</span><span class="sxs-lookup"><span data-stu-id="9acf3-104"> is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="9acf3-105">Wenn nicht wohlgeformtes oder ungültiges XML an übergeben wird [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], die zugrunde liegende <xref:System.Xml.XmlReader>Klasse wird eine Ausnahme ausgelöst.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="9acf3-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="9acf3-106">Die verschiedenen Methoden, die XML, z. B. analysieren <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, fangen die Ausnahme nicht; die Ausnahme kann dann von Ihrer Anwendung abgefangen werden.</xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9acf3-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
 <span data-ttu-id="9acf3-107">Beachten Sie, dass Sie bei Verwendung von XML-Literalen keine Analysefehler abrufen können.</span><span class="sxs-lookup"><span data-stu-id="9acf3-107">Note that you cannot get parse errors if you use XML literals.</span></span> <span data-ttu-id="9acf3-108">Der Visual Basic-Compiler fängt Fehler von nicht wohlgeformtem oder ungültigem XML ab.</span><span class="sxs-lookup"><span data-stu-id="9acf3-108">The Visual Basic compiler will catch errors of badly formed or invalid XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9acf3-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9acf3-109">Example</span></span>  
 <span data-ttu-id="9acf3-110">Der folgende Code versucht, ungültiges XML zu analysieren:</span><span class="sxs-lookup"><span data-stu-id="9acf3-110">The following code tries to parse invalid XML:</span></span>  
  
```vb  
Try  
    Dim contacts As XElement = XElement.Parse("<Contacts>" & vbCrLf & _  
        "    <Contact>" & vbCrLf & _  
        "        <Name>Jim Wilson</Name>" & vbCrLf & _  
        "    </Contact>" & vbCrLf & _  
        "</Contcts>")  
  
    Console.WriteLine(contacts)  
Catch e As System.Xml.XmlException  
    Console.WriteLine(e.Message)  
End Try  
```  
  
 <span data-ttu-id="9acf3-111">Wenn Sie diesen Code ausführen, wird die folgende Ausnahme ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="9acf3-111">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="9acf3-112">Weitere Informationen zu den Ausnahmen, die Sie erwarten können die <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, und <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>Methoden ausgelöst werden, finden Sie unter der <xref:System.Xml.XmlReader>Dokumentation.</xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9acf3-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9acf3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9acf3-113">See Also</span></span>  
 [<span data-ttu-id="9acf3-114">Analysieren von XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9acf3-114">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
