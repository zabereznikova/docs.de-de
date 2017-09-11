---
title: 'Vorgehensweise: Auffangen von Parsingfehlern (C#)'
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
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 240bc9770475bdf7b6da2102bd8b552a0991eea6
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-catch-parsing-errors-c"></a><span data-ttu-id="e31c8-102">Vorgehensweise: Auffangen von Parsingfehlern (C#)</span><span class="sxs-lookup"><span data-stu-id="e31c8-102">How to: Catch Parsing Errors (C#)</span></span>
<span data-ttu-id="e31c8-103">In diesem Thema wird gezeigt, wie nicht wohlgeformter oder ungültiger XML-Code erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e31c8-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="e31c8-104"> wird mithilfe von <xref:System.Xml.XmlReader> implementiert.</span><span class="sxs-lookup"><span data-stu-id="e31c8-104"> is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="e31c8-105">Wenn nicht wohlgeformter oder ungültiger XML-Code an [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] übergeben wird, löst die zugrunde liegende <xref:System.Xml.XmlReader>-Klasse eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="e31c8-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="e31c8-106">Die verschiedenen Methoden, die XML analysieren, z.B. <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, fangen die Ausnahme nicht ab. Die Ausnahme kann dann von Ihrer Anwendung abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="e31c8-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e31c8-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e31c8-107">Example</span></span>  
 <span data-ttu-id="e31c8-108">Der folgende Code versucht, ungültiges XML zu analysieren:</span><span class="sxs-lookup"><span data-stu-id="e31c8-108">The following code tries to parse invalid XML:</span></span>  
  
```csharp  
try {  
    XElement contacts = XElement.Parse(  
        @"<Contacts>  
            <Contact>  
                <Name>Jim Wilson</Name>  
            </Contact>  
          </Contcts>");  
  
    Console.WriteLine(contacts);  
}  
catch (System.Xml.XmlException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
 <span data-ttu-id="e31c8-109">Wenn Sie diesen Code ausführen, wird die folgende Ausnahme ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="e31c8-109">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="e31c8-110">Weitere Informationen zu den Ausnahmen, von denen Sie ausgehen können, dass sie von den Methoden <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> und <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> ausgelöst werden, finden Sie in der <xref:System.Xml.XmlReader>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="e31c8-110">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e31c8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e31c8-111">See Also</span></span>  
 [<span data-ttu-id="e31c8-112">Analysieren von XML (C#)</span><span class="sxs-lookup"><span data-stu-id="e31c8-112">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)

