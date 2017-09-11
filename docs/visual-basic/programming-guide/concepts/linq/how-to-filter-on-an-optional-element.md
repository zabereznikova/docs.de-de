---
title: 'Gewusst wie: Filtern nach einem optionalen Element (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: a74b76ad-6889-4185-a189-d6ef2c63841e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7534ccc197dd4a8f2603e12f13d69d2fec30df80
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017


---
# <a name="how-to-filter-on-an-optional-element-visual-basic"></a><span data-ttu-id="e38d3-102">Gewusst wie: Filtern nach einem optionalen Element (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e38d3-102">How to: Filter on an Optional Element (Visual Basic)</span></span>
<span data-ttu-id="e38d3-103">Es kann vorkommen, dass Sie nach einem Element filtern möchten, ohne genau zu wissen, ob dieses Element in Ihrem XML-Dokument tatsächlich existiert.</span><span class="sxs-lookup"><span data-stu-id="e38d3-103">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="e38d3-104">Die Suche sollte dann so ausgeführt werden, dass für den Fall, dass das Element das gesuchte untergeordnete Element nicht besitzt, beim Filtern keine Ausnahme wegen eines NULL-Verweises ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e38d3-104">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="e38d3-105">Im folgenden Beispiel besitzt das `Child5`-Element kein untergeordnetes `Type`-Element, dennoch wird die Abfrage korrekt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e38d3-105">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e38d3-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e38d3-106">Example</span></span>  
 <span data-ttu-id="e38d3-107">Dieses Beispiel verwendet die <xref:System.Xml.Linq.Extensions.Elements%2A>-Erweiterungsmethode.</xref:System.Xml.Linq.Extensions.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="e38d3-107">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
```vb  
Dim root As XElement = _   
    <Root>  
        <Child1>  
            <Text>Child One Text</Text>  
            <Type Value="Yes"/>  
        </Child1>  
        <Child2>  
            <Text>Child Two Text</Text>  
            <Type Value="Yes"/>  
        </Child2>  
        <Child3>  
            <Text>Child Three Text</Text>  
            <Type Value="No"/>  
        </Child3>  
        <Child4>  
            <Text>Child Four Text</Text>  
            <Type Value="Yes"/>  
        </Child4>  
        <Child5>  
            <Text>Child Five Text</Text>  
        </Child5>  
    </Root>  
Dim cList As IEnumerable(Of String) = _  
    From typeElement In root.Elements().<Type> _  
    Where typeElement.@Value = "Yes" _  
    Select typeElement.Parent.<Text>.Value  
Dim str As String  
For Each str In cList  
    Console.WriteLine(str)  
Next  
```  
  
 <span data-ttu-id="e38d3-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e38d3-108">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="e38d3-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e38d3-109">Example</span></span>  
 <span data-ttu-id="e38d3-110">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e38d3-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="e38d3-111">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="e38d3-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child1>  
                    <Text>Child One Text</Text>  
                    <Type Value="Yes"/>  
                </Child1>  
                <Child2>  
                    <Text>Child Two Text</Text>  
                    <Type Value="Yes"/>  
                </Child2>  
                <Child3>  
                    <Text>Child Three Text</Text>  
                    <Type Value="No"/>  
                </Child3>  
                <Child4>  
                    <Text>Child Four Text</Text>  
                    <Type Value="Yes"/>  
                </Child4>  
                <Child5>  
                    <Text>Child Five Text</Text>  
                </Child5>  
            </Root>  
        Dim cList As IEnumerable(Of String) = _  
            From typeElement In root.Elements().<Type> _  
            Where typeElement.@Value = "Yes" _  
            Select typeElement.Parent.<Text>.Value  
        Dim str As String  
        For Each str In cList  
            Console.WriteLine(str)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="e38d3-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e38d3-112">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="e38d3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e38d3-113">See Also</span></span>  
 <span data-ttu-id="e38d3-114"><xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e38d3-114"><xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="e38d3-115"><xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e38d3-115"><xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="e38d3-116"><xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName></xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e38d3-116"><xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName></span></span>   
<span data-ttu-id="e38d3-117"> [Standardabfragen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="e38d3-117"> [Basic Queries (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span></span>  
<span data-ttu-id="e38d3-118"> [Untergeordnete XML-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="e38d3-118"> [XML Child Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md) </span></span>  
<span data-ttu-id="e38d3-119"> [XML-Attributachseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="e38d3-119"> [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span></span>  
<span data-ttu-id="e38d3-120"> [XML-Value-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md) </span><span class="sxs-lookup"><span data-stu-id="e38d3-120"> [XML Value Property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md) </span></span>  
<span data-ttu-id="e38d3-121"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="e38d3-121"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="e38d3-122"> [Projektionsvorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)</span><span class="sxs-lookup"><span data-stu-id="e38d3-122"> [Projection Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)</span></span>
