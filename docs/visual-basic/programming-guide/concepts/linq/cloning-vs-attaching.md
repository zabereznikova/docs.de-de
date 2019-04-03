---
title: Klonen oder Anfügen (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 3c3bd105-c9d3-49bd-875b-27ab4e8bc7a3
ms.openlocfilehash: 59ffedfdbb2820683f1e6cc232154688f5c29fc8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832293"
---
# <a name="cloning-vs-attaching-visual-basic"></a><span data-ttu-id="9bf8a-102">Klonen oder Anfügen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bf8a-102">Cloning vs. Attaching (Visual Basic)</span></span>
<span data-ttu-id="9bf8a-103">Beim Hinzufügen von <xref:System.Xml.Linq.XNode> (inklusive <xref:System.Xml.Linq.XElement>)-Objekten oder <xref:System.Xml.Linq.XAttribute>-Objekten zu einer neuen Struktur werden die Objekte einfach an die XML-Struktur angefügt, falls der neue Inhalt kein übergeordnetes Element besitzt.</span><span class="sxs-lookup"><span data-stu-id="9bf8a-103">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects to a new tree, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="9bf8a-104">Wenn der neue Inhalt bereits ein übergeordnetes Element besitzt und Bestandteil einer anderen XML-Struktur ist, wird er geklont.</span><span class="sxs-lookup"><span data-stu-id="9bf8a-104">If the new content already is parented, and is part of another XML tree, the new content is cloned.</span></span> <span data-ttu-id="9bf8a-105">Der neu geklonte Inhalt wird dann an die XML-Struktur angefügt.</span><span class="sxs-lookup"><span data-stu-id="9bf8a-105">The newly cloned content is then attached to the XML tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bf8a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bf8a-106">Example</span></span>  
 <span data-ttu-id="9bf8a-107">Der folgende Code zeigt das Verhalten, wenn Sie einer Struktur ein übergeordnetes Element und ein Element ohne übergeordnetes Element hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9bf8a-107">The following code demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>  
  
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
  
 <span data-ttu-id="9bf8a-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9bf8a-108">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bf8a-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bf8a-109">See also</span></span>

- [<span data-ttu-id="9bf8a-110">Erstellen von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bf8a-110">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
