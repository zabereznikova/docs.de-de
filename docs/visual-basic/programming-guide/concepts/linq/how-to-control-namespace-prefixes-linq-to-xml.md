---
title: 'Vorgehensweise: Steuerelement-Namespace Präfixe (Visual Basic) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 2b89b49aa76df526c08143cad49685386ffd5e7c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2019
ms.locfileid: "68709822"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a>Vorgehensweise: Steuerelement-Namespace Präfixe (Visual Basic) (LINQ to XML)
In diesem Thema wird beschrieben, wie Sie Namespacepräfixe steuern können.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Dieses Beispiel deklariert zwei Namespaces. Er gibt an `http://www.adventure-works.com` `www.fourthcoffee.com` `aw` ,dassderNamespacedasPräfixhatunddassderNamespacedas`fc`Präfix hat.  
  
### <a name="code"></a>Code  
  
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
  
### <a name="comments"></a>Kommentare  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
