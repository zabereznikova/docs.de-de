---
title: 'Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 6593639dcdc234ddda808cfdb5e85ebe1a771b62
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248946"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="18204-102">Gewusst wie: Abrufen des Werts eines Attributs (LINQ zu XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18204-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="18204-103">In diesem Thema wird gezeigt, wie Sie den Wert von Attributen abrufen können.</span><span class="sxs-lookup"><span data-stu-id="18204-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="18204-104">Im Wesentlichen gibt es dafür zwei Möglichkeiten: Sie können ein <xref:System.Xml.Linq.XAttribute> in den gewünschten Typ umwandeln. Die Umwandlung des Inhalts des Elements oder Attributs in den angegebenen Typ erfolgt dann durch den expliziten Konvertierungsoperator.</span><span class="sxs-lookup"><span data-stu-id="18204-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="18204-105">Die andere Möglichkeit besteht darin, die <xref:System.Xml.Linq.XAttribute.Value%2A>-Eigenschaft zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="18204-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="18204-106">In der Regel empfiehlt sich aber die Verwendung des Umwandlungsverfahrens.</span><span class="sxs-lookup"><span data-stu-id="18204-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="18204-107">Wenn Sie das Attribut in einen NULL-Werttyp umlegen, ist der Code einfacher zu schreiben, wenn der Wert eines Attributs abgerufen wird, das möglicherweise nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="18204-107">If you cast the attribute to a nullable value type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="18204-108">Beispiele für diese Technik finden Sie unter [Gewusst wie: Abrufen des Werts eines Elements (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="18204-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18204-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18204-109">Example</span></span>  
 <span data-ttu-id="18204-110">In Visual Basic können Sie zum Abrufen des Werts eines Attributs die integrierte Attributeigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="18204-110">In Visual Basic, you can use the integrated attribute property to retrieve the value of an attribute.</span></span>  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="18204-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="18204-111">This example produces the following output:</span></span>  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="18204-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18204-112">Example</span></span>  
 <span data-ttu-id="18204-113">In Visual Basic können Sie zum Festlegen des Werts eines Attributs die integrierte Attributeigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="18204-113">In Visual Basic, you can use the integrated attribute property to set the value of an attribute.</span></span> <span data-ttu-id="18204-114">Wenn Sie die integrierte Attributeigenschaft verwenden und den Wert eines Attributs festlegen, das nicht existiert, wird dieses Attribut erstellt.</span><span class="sxs-lookup"><span data-stu-id="18204-114">Further, if you use the integrated attribute property to set the value of an attribute that does not exist, the attribute will be created.</span></span>  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="18204-115">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="18204-115">This example produces the following output:</span></span>  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a><span data-ttu-id="18204-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18204-116">Example</span></span>  
 <span data-ttu-id="18204-117">Im folgenden Beispiel wird gezeigt, wie Sie den Wert eines Attributs für den Fall abrufen können, dass sich das Attribut in einem Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="18204-117">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="18204-118">Weitere Informationen finden Sie unter [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="18204-118">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="18204-119">Hierdurch wird folgende Ausgabe generiert:</span><span class="sxs-lookup"><span data-stu-id="18204-119">This example produces the following output:</span></span>  
  
```console  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="18204-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18204-120">See also</span></span>

- [<span data-ttu-id="18204-121">LINQ to XML-Achsen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18204-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
