---
title: 'Gewusst wie: Steuern von Namespace Präfixen (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 5ba415452a8671466c3a4c71a88731e5bd3cda60
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348379"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="32935-102">Gewusst wie: Steuern von Namespacepräfixen (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="32935-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="32935-103">In diesem Thema wird beschrieben, wie Sie Namespacepräfixe steuern können.</span><span class="sxs-lookup"><span data-stu-id="32935-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32935-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="32935-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="32935-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32935-105">Description</span></span>  
 <span data-ttu-id="32935-106">Dieses Beispiel deklariert zwei Namespaces.</span><span class="sxs-lookup"><span data-stu-id="32935-106">This example declares two namespaces.</span></span> <span data-ttu-id="32935-107">Er gibt an, dass der `http://www.adventure-works.com` Namespace das Präfix `aw`hat und dass der `www.fourthcoffee.com` Namespace das Präfix `fc`hat.</span><span class="sxs-lookup"><span data-stu-id="32935-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="32935-108">Code</span><span class="sxs-lookup"><span data-stu-id="32935-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="32935-109">Comments</span><span class="sxs-lookup"><span data-stu-id="32935-109">Comments</span></span>  
 <span data-ttu-id="32935-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="32935-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="32935-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32935-111">See also</span></span>

- [<span data-ttu-id="32935-112">Übersicht über Namespaces (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32935-112">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
