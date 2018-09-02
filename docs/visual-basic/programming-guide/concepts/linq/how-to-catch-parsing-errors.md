---
title: 'Vorgehensweise: Auffangen von Parsingfehlern (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
ms.openlocfilehash: aa72b914d4640410a4d47ba49e774dcee31a54c0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406547"
---
# <a name="how-to-catch-parsing-errors-visual-basic"></a><span data-ttu-id="c184c-102">Vorgehensweise: Auffangen von Parsingfehlern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c184c-102">How to: Catch Parsing Errors (Visual Basic)</span></span>
<span data-ttu-id="c184c-103">In diesem Thema wird gezeigt, wie nicht wohlgeformter oder ungültiger XML-Code erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c184c-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="c184c-104"> wird mithilfe von <xref:System.Xml.XmlReader> implementiert.</span><span class="sxs-lookup"><span data-stu-id="c184c-104"> is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="c184c-105">Wenn nicht wohlgeformter oder ungültiger XML-Code an [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] übergeben wird, löst die zugrunde liegende <xref:System.Xml.XmlReader>-Klasse eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="c184c-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="c184c-106">Die verschiedenen Methoden, die XML analysieren, z.B. <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, fangen die Ausnahme nicht ab. Die Ausnahme kann dann von Ihrer Anwendung abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="c184c-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
 <span data-ttu-id="c184c-107">Beachten Sie, dass Sie bei Verwendung von XML-Literalen keine Analysefehler abrufen können.</span><span class="sxs-lookup"><span data-stu-id="c184c-107">Note that you cannot get parse errors if you use XML literals.</span></span> <span data-ttu-id="c184c-108">Der Visual Basic-Compiler fängt Fehler von nicht wohlgeformtem oder ungültigem XML ab.</span><span class="sxs-lookup"><span data-stu-id="c184c-108">The Visual Basic compiler will catch errors of badly formed or invalid XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c184c-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c184c-109">Example</span></span>  
 <span data-ttu-id="c184c-110">Der folgende Code versucht, ungültiges XML zu analysieren:</span><span class="sxs-lookup"><span data-stu-id="c184c-110">The following code tries to parse invalid XML:</span></span>  
  
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
  
 <span data-ttu-id="c184c-111">Wenn Sie diesen Code ausführen, wird die folgende Ausnahme ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="c184c-111">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="c184c-112">Weitere Informationen zu den Ausnahmen, von denen Sie ausgehen können, dass sie von den Methoden <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> und <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> ausgelöst werden, finden Sie in der <xref:System.Xml.XmlReader>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="c184c-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c184c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c184c-113">See Also</span></span>  
 [<span data-ttu-id="c184c-114">Analysieren von XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c184c-114">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
