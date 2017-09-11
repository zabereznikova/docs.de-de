---
title: 'Gewusst wie: Suchen eines einzelnen Nachfolgers mit der Descendants-Methode (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 0c03468c-efc8-4140-98f3-fb67acd9e8e1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7f0b2fd3a14f1401e88b4f0ca6b5feab69182770
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-visual-basic"></a><span data-ttu-id="79b93-102">Gewusst wie: Suchen eines einzelnen Nachfolgers mit der Descendants-Methode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79b93-102">How to: Find a Single Descendant Using the Descendants Method (Visual Basic)</span></span>
<span data-ttu-id="79b93-103">Sie können die <xref:System.Xml.Linq.XContainer.Descendants%2A>Achsenmethode schnell Schreiben von Code zum Suchen nach einem einzelnen eindeutig benannten Element.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="79b93-103">You can use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to quickly write code to find a single uniquely named element.</span></span> <span data-ttu-id="79b93-104">Diese Technik ist besonders nützlich, wenn Sie einen bestimmten Nachfolger mit einem bestimmten Namen ermitteln möchten.</span><span class="sxs-lookup"><span data-stu-id="79b93-104">This technique is especially useful when you want to find a particular descendant with a specific name.</span></span> <span data-ttu-id="79b93-105">Schreiben Sie Code, navigieren Sie zum gewünschten Element könnte, aber es ist häufig schneller und einfacher zu schreiben den Code mit der <xref:System.Xml.Linq.XContainer.Descendants%2A>Achse.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="79b93-105">You could write the code to navigate to the desired element, but it is often faster and easier to write the code using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79b93-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79b93-106">Example</span></span>  
 <span data-ttu-id="79b93-107">Dieses Beispiel verwendet die <xref:System.Linq.Enumerable.First%2A>Standardabfrageoperator.</xref:System.Linq.Enumerable.First%2A></span><span class="sxs-lookup"><span data-stu-id="79b93-107">This example uses the <xref:System.Linq.Enumerable.First%2A> standard query operator.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1>GC1 Value</GrandChild1>  
        </Child1>  
        <Child2>  
            <GrandChild2>GC2 Value</GrandChild2>  
        </Child2>  
        <Child3>  
            <GrandChild3>GC3 Value</GrandChild3>  
        </Child3>  
        <Child4>  
            <GrandChild4>GC4 Value</GrandChild4>  
        </Child4>  
    </Root>  
Dim grandChild3 As String = _  
    (From el In root...<GrandChild3> _  
    Select el).First()  
Console.WriteLine(grandChild3)  
```  
  
 <span data-ttu-id="79b93-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="79b93-108">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="example"></a><span data-ttu-id="79b93-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79b93-109">Example</span></span>  
 <span data-ttu-id="79b93-110">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="79b93-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="79b93-111">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="79b93-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child1>  
                    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
                </aw:Child1>  
                <aw:Child2>  
                    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
                </aw:Child2>  
                <aw:Child3>  
                    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
                </aw:Child3>  
                <aw:Child4>  
                    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
                </aw:Child4>  
            </aw:Root>  
        Dim grandChild3 As String = _  
            (From el In root...<aw:GrandChild3> _  
            Select el).First()  
        Console.WriteLine(grandChild3)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="79b93-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="79b93-112">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="see-also"></a><span data-ttu-id="79b93-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79b93-113">See Also</span></span>  
 [<span data-ttu-id="79b93-114">Standardabfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79b93-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
