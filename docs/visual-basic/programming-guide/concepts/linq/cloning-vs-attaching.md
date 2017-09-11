---
title: "Klonen oder Anfügen (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 3c3bd105-c9d3-49bd-875b-27ab4e8bc7a3
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9c86a75b1c9b4dc25e29d8323d23f89232b8de80
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="cloning-vs-attaching-visual-basic"></a><span data-ttu-id="89850-102">Klonen oder Anfügen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89850-102">Cloning vs. Attaching (Visual Basic)</span></span>
<span data-ttu-id="89850-103">Beim Hinzufügen von <xref:System.Xml.Linq.XNode>(einschließlich <xref:System.Xml.Linq.XElement>) oder <xref:System.Xml.Linq.XAttribute>Objekte zu einer neuen Struktur, der neue Inhalt kein übergeordnetes Element besitzt, werden die Objekte einfach an die XML-Struktur angefügt.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="89850-103">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects to a new tree, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="89850-104">Wenn der neue Inhalt bereits ein übergeordnetes Element besitzt und Bestandteil einer anderen XML-Struktur ist, wird er geklont.</span><span class="sxs-lookup"><span data-stu-id="89850-104">If the new content already is parented, and is part of another XML tree, the new content is cloned.</span></span> <span data-ttu-id="89850-105">Der neu geklonte Inhalt wird dann an die XML-Struktur angefügt.</span><span class="sxs-lookup"><span data-stu-id="89850-105">The newly cloned content is then attached to the XML tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89850-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89850-106">Example</span></span>  
 <span data-ttu-id="89850-107">Der folgende Code zeigt das Verhalten, wenn Sie einer Struktur ein übergeordnetes Element und ein Element ohne übergeordnetes Element hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="89850-107">The following code demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 <span data-ttu-id="89850-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="89850-108">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="89850-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89850-109">See Also</span></span>  
 [<span data-ttu-id="89850-110">Erstellen von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89850-110">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
