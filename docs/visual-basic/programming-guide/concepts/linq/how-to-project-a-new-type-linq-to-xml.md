---
title: 'Vorgehensweise: Projektieren eines neuen Typs (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 8cfb24f5-89b2-4cfb-b85d-e7963f8f1845
ms.openlocfilehash: 48fb82e870a4fc4fa16cfb48a127f364e6d81f13
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396505"
---
# <a name="how-to-project-a-new-type-linq-to-xml-visual-basic"></a><span data-ttu-id="b7d14-102">Vorgehensweise: Projizieren eines neuen Typs (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7d14-102">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="b7d14-103">In anderen Beispielen dieses Abschnitts wurden Abfragen gezeigt, die Ergebnisse als eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement>, eine <xref:System.Collections.Generic.IEnumerable%601> von `string` und eine <xref:System.Collections.Generic.IEnumerable%601> von `int` zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b7d14-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="b7d14-104">Dabei handelt es sich zwar um gängige Ergebnistypen, die sich aber nicht für jedes Szenario eignen.</span><span class="sxs-lookup"><span data-stu-id="b7d14-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="b7d14-105">In vielen Fällen besteht Ihr Ziel darin, dass Ihre Abfragen als eine <xref:System.Collections.Generic.IEnumerable%601> eines anderen Typs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b7d14-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7d14-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7d14-106">Example</span></span>  
 <span data-ttu-id="b7d14-107">In diesem Beispiel wird gezeigt, wie Sie Objekte in der `Select`-Klausel instanziieren können.</span><span class="sxs-lookup"><span data-stu-id="b7d14-107">This example shows how to instantiate objects in the `Select` clause.</span></span> <span data-ttu-id="b7d14-108">Der Code definiert zuerst mit einem Konstruktor eine neue Klasse und ändert anschließend die `Select`-Anweisung so, dass der Ausdruck zu einer neuen Instanz der neuen Klasse wird.</span><span class="sxs-lookup"><span data-stu-id="b7d14-108">The code first defines a new class with a constructor, and then modifies the `Select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="b7d14-109">Dieses Beispiel verwendet das folgende XML-Dokument: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b7d14-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Public Class NameQty  
    Public name As String  
    Public qty As Integer  
    Public Sub New(ByVal n As String, ByVal q As Integer)  
        name = n  
        qty = q  
    End Sub  
End Class  
  
Public Class Program  
    Shared Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
  
        Dim nqList As IEnumerable(Of NameQty) = _  
            From n In po...<Item> _  
            Select New NameQty( _  
                n.<ProductName>.Value, CInt(n.<Quantity>.Value))  
  
        For Each n As NameQty In nqList  
            Console.WriteLine(n.name & ":" & n.qty)  
        Next  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="b7d14-110">In diesem Beispiel wird die- `M:System.Xml.Linq.XElement.Element` Methode verwendet, die im Thema Gewusst [wie: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic)](how-to-retrieve-a-single-child-element-linq-to-xml.md)vorgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b7d14-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="b7d14-111">Außerdem verwendet das Beispiel Umwandlungen, um die Werte der Elemente abzurufen, die von der `M:System.Xml.Linq.XElement.Element`-Methode zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b7d14-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="b7d14-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b7d14-112">This example produces the following output:</span></span>  
  
```console  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7d14-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7d14-113">See also</span></span>

- [<span data-ttu-id="b7d14-114">Projektionen und Transformationen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7d14-114">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](projections-and-transformations-linq-to-xml.md)
