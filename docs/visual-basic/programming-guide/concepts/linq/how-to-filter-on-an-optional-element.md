---
title: 'Vorgehensweise: Filtern nach einem optionalen Element'
ms.date: 07/20/2015
ms.assetid: a74b76ad-6889-4185-a189-d6ef2c63841e
ms.openlocfilehash: 9f03eee479e7c47e528a145d370472de6dfddd39
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394362"
---
# <a name="how-to-filter-on-an-optional-element-visual-basic"></a><span data-ttu-id="92f18-102">Gewusst wie: Filtern nach einem optionalen Element (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92f18-102">How to: Filter on an Optional Element (Visual Basic)</span></span>
<span data-ttu-id="92f18-103">Es kann vorkommen, dass Sie nach einem Element filtern möchten, ohne genau zu wissen, ob dieses Element in Ihrem XML-Dokument tatsächlich existiert.</span><span class="sxs-lookup"><span data-stu-id="92f18-103">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="92f18-104">Die Suche sollte dann so ausgeführt werden, dass für den Fall, dass das Element das gesuchte untergeordnete Element nicht besitzt, beim Filtern keine Ausnahme wegen eines NULL-Verweises ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="92f18-104">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="92f18-105">Im folgenden Beispiel besitzt das `Child5`-Element kein untergeordnetes `Type`-Element, dennoch wird die Abfrage korrekt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="92f18-105">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92f18-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92f18-106">Example</span></span>  
 <span data-ttu-id="92f18-107">Dieses Beispiel verwendet die <xref:System.Xml.Linq.Extensions.Elements%2A>-Erweiterungsmethode:</span><span class="sxs-lookup"><span data-stu-id="92f18-107">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
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
  
 <span data-ttu-id="92f18-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="92f18-108">This code produces the following output:</span></span>  
  
```console  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="92f18-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92f18-109">Example</span></span>  
 <span data-ttu-id="92f18-110">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="92f18-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="92f18-111">Weitere Informationen finden Sie unter [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="92f18-111">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="92f18-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="92f18-112">This code produces the following output:</span></span>  
  
```console  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="92f18-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92f18-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="92f18-114">Grundlegende Abfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92f18-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](basic-queries-linq-to-xml.md)
- [<span data-ttu-id="92f18-115">XML Child Axis Property</span><span class="sxs-lookup"><span data-stu-id="92f18-115">XML Child Axis Property</span></span>](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="92f18-116">XML Attribute Axis Property</span><span class="sxs-lookup"><span data-stu-id="92f18-116">XML Attribute Axis Property</span></span>](../../../language-reference/xml-axis/xml-attribute-axis-property.md)
- [<span data-ttu-id="92f18-117">XML-Value-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="92f18-117">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="92f18-118">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="92f18-118">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="92f18-119">Projektions Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92f18-119">Projection Operations (Visual Basic)</span></span>](projection-operations.md)
