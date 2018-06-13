---
title: 'Vorgehensweise: Suchen nach Nachfolgern mit einem bestimmten Elementnamen (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 78915518-0d25-4051-ab55-929779989510
ms.openlocfilehash: c6f702c121f6a8b9aa5750b4c5ff70c00e681b82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643161"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-visual-basic"></a><span data-ttu-id="73d0d-102">Vorgehensweise: Suchen nach Nachfolgern mit einem bestimmten Elementnamen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73d0d-102">How to: Find Descendants with a Specific Element Name (Visual Basic)</span></span>
<span data-ttu-id="73d0d-103">Es kann vorkommen, dass Sie alle Nachfolgerelemente mit einem bestimmten Namen ermitteln möchten.</span><span class="sxs-lookup"><span data-stu-id="73d0d-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="73d0d-104">Dazu könnten Sie Code schreiben, der alle Nachfolgerelemente durchläuft, einfacher ist es aber, die <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="73d0d-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73d0d-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73d0d-105">Example</span></span>  
 <span data-ttu-id="73d0d-106">Im folgenden Beispiel wird gezeigt, wie Sie Nachfolgerelemente anhand des Elementnamens ermitteln können:</span><span class="sxs-lookup"><span data-stu-id="73d0d-106">The following example shows how to find descendants based on the element name.</span></span>  
  
```vb  
Dim root As XElement = _  
    <root>  
        <para>  
            <r>  
                <t>Some text </t>  
            </r>  
            <n>  
                <r>  
                    <t>that is broken up into </t>  
                </r>  
            </n>  
            <n>  
                <r>  
                    <t>multiple segments.</t>  
                </r>  
            </n>  
        </para>  
    </root>  
  
Dim textSegs As IEnumerable(Of String) = _  
    From seg In root...<t> _  
    Select seg.Value  
  
Dim str As String = textSegs.Aggregate( _  
    New StringBuilder, _  
    Function(sb, i) sb.Append(i), _  
    Function(sb) sb.ToString)  
  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="73d0d-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="73d0d-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="73d0d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73d0d-108">Example</span></span>  
 <span data-ttu-id="73d0d-109">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="73d0d-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="73d0d-110">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="73d0d-110">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <root>  
                <para>  
                    <r>  
                        <t>Some text </t>  
                    </r>  
                    <n>  
                        <r>  
                            <t>that is broken up into </t>  
                        </r>  
                    </n>  
                    <n>  
                        <r>  
                            <t>multiple segments.</t>  
                        </r>  
                    </n>  
                </para>  
            </root>  
  
        Dim textSegs As IEnumerable(Of String) = _  
            From seg In root...<t> _  
            Select seg.Value  
  
        Dim str As String = textSegs.Aggregate( _  
            New StringBuilder, _  
            Function(sb, i) sb.Append(i), _  
            Function(sb) sb.ToString)  
  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="73d0d-111">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="73d0d-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="73d0d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73d0d-112">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A>  
 [<span data-ttu-id="73d0d-113">Standardabfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73d0d-113">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
