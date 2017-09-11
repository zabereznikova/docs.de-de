---
title: "Gewusst wie: Steuern von Namespace-Präfixe (Visual Basic) (LINQ to XML) | Microsoft-Dokumentation"
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
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
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
ms.openlocfilehash: 87db9e5384bee835ca4fde141765eabf9a7cfedb
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="a45b1-102">Gewusst wie: Steuern von Namespacepräfixen (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="a45b1-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="a45b1-103">In diesem Thema wird beschrieben, wie Sie Namespacepräfixe steuern können.</span><span class="sxs-lookup"><span data-stu-id="a45b1-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a45b1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a45b1-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a45b1-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a45b1-105">Description</span></span>  
 <span data-ttu-id="a45b1-106">Dieses Beispiel deklariert zwei Namespaces.</span><span class="sxs-lookup"><span data-stu-id="a45b1-106">This example declares two namespaces.</span></span> <span data-ttu-id="a45b1-107">Gibt an, dass die `http://www.adventure-works.com` Namespace verfügt über das Präfix `aw`, und dass die `www.fourthcoffee.com` Namespace verfügt über das Präfix des `fc`.</span><span class="sxs-lookup"><span data-stu-id="a45b1-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a45b1-108">Code</span><span class="sxs-lookup"><span data-stu-id="a45b1-108">Code</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="a45b1-109">Kommentare</span><span class="sxs-lookup"><span data-stu-id="a45b1-109">Comments</span></span>  
 <span data-ttu-id="a45b1-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a45b1-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a45b1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a45b1-111">See Also</span></span>  
 [<span data-ttu-id="a45b1-112">Arbeiten mit XML-Namespaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a45b1-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
