---
title: 'Gewusst wie: Steuern von Namespacepräfixen (Visual Basic) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: f60f90ef6742dfd725f51ff7e760436117346e85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641679"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="9e9bd-102">Gewusst wie: Steuern von Namespacepräfixen (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="9e9bd-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="9e9bd-103">In diesem Thema wird beschrieben, wie Sie Namespacepräfixe steuern können.</span><span class="sxs-lookup"><span data-stu-id="9e9bd-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e9bd-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9e9bd-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9e9bd-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e9bd-105">Description</span></span>  
 <span data-ttu-id="9e9bd-106">Dieses Beispiel deklariert zwei Namespaces.</span><span class="sxs-lookup"><span data-stu-id="9e9bd-106">This example declares two namespaces.</span></span> <span data-ttu-id="9e9bd-107">Gibt an, dass die `http://www.adventure-works.com` Namespace verfügt über das Präfix `aw`, und dass die `www.fourthcoffee.com` Namespace verfügt über das Präfix des `fc`.</span><span class="sxs-lookup"><span data-stu-id="9e9bd-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9e9bd-108">Code</span><span class="sxs-lookup"><span data-stu-id="9e9bd-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="9e9bd-109">Kommentare</span><span class="sxs-lookup"><span data-stu-id="9e9bd-109">Comments</span></span>  
 <span data-ttu-id="9e9bd-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9e9bd-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e9bd-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e9bd-111">See Also</span></span>  
 [<span data-ttu-id="9e9bd-112">Arbeiten mit XML-Namespaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e9bd-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
