---
title: 'Gewusst wie: Abrufen des Werts eines Attributs (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 6ecc1368832b9c98efeae65c95438efb80f164f6
ms.contentlocale: de-de
ms.lasthandoff: 06/01/2017


---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="affbe-102">Gewusst wie: Abrufen des Werts eines Attributs (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="affbe-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="affbe-103">In diesem Thema wird gezeigt, wie Sie den Wert von Attributen abrufen können.</span><span class="sxs-lookup"><span data-stu-id="affbe-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="affbe-104">Es gibt zwei Hauptmethoden: Sie können eine Umwandlung ein <xref:System.Xml.Linq.XAttribute>auf den gewünschten Typ der explizite Konvertierungsoperator dann den Inhalt des Elements oder Attributs in den angegebenen Typ konvertiert.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="affbe-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="affbe-105">Alternativ können Sie die <xref:System.Xml.Linq.XAttribute.Value%2A>Eigenschaft.</xref:System.Xml.Linq.XAttribute.Value%2A></span><span class="sxs-lookup"><span data-stu-id="affbe-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="affbe-106">In der Regel empfiehlt sich aber die Verwendung des Umwandlungsverfahrens.</span><span class="sxs-lookup"><span data-stu-id="affbe-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="affbe-107">Wenn Sie das Attribut in einen Typ umwandeln, der NULL-Werte zulässt, ist der Code für das Abrufen des Werts eines Attributs, von dem nicht genau bekannt ist, ob es überhaupt vorhanden ist, einfacher zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="affbe-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="affbe-108">Beispiele für diese Technik, finden Sie unter [Gewusst wie: Abrufen des Werts eines Elements (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="affbe-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="affbe-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affbe-109">Example</span></span>  
 <span data-ttu-id="affbe-110">In Visual Basic können Sie zum Abrufen des Werts eines Attributs die integrierte Attributeigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="affbe-110">In Visual Basic, you can use the integrated attribute property to retrieve the value of an attribute.</span></span>  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="affbe-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="affbe-111">This example produces the following output:</span></span>  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="affbe-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affbe-112">Example</span></span>  
 <span data-ttu-id="affbe-113">In Visual Basic können Sie zum Festlegen des Werts eines Attributs die integrierte Attributeigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="affbe-113">In Visual Basic, you can use the integrated attribute property to set the value of an attribute.</span></span> <span data-ttu-id="affbe-114">Wenn Sie die integrierte Attributeigenschaft verwenden und den Wert eines Attributs festlegen, das nicht existiert, wird dieses Attribut erstellt.</span><span class="sxs-lookup"><span data-stu-id="affbe-114">Further, if you use the integrated attribute property to set the value of an attribute that does not exist, the attribute will be created.</span></span>  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="affbe-115">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="affbe-115">This example produces the following output:</span></span>  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a><span data-ttu-id="affbe-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affbe-116">Example</span></span>  
 <span data-ttu-id="affbe-117">Im folgenden Beispiel wird gezeigt, wie Sie den Wert eines Attributs für den Fall abrufen können, dass sich das Attribut in einem Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="affbe-117">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="affbe-118">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="affbe-118">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
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
  
 <span data-ttu-id="affbe-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="affbe-119">This example produces the following output:</span></span>  
  
```  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="affbe-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="affbe-120">See Also</span></span>  
 [<span data-ttu-id="affbe-121">LINQ to XML-Achsen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="affbe-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
