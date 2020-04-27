---
title: Entfernen von Knoten aus dem DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
ms.openlocfilehash: a34b92abc59215c3cb2b94afd88e2e30405b4e9a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710309"
---
# <a name="removing-nodes-from-the-dom"></a><span data-ttu-id="1af70-102">Entfernen von Knoten aus dem DOM</span><span class="sxs-lookup"><span data-stu-id="1af70-102">Removing Nodes from the DOM</span></span>
<span data-ttu-id="1af70-103">Verwenden Sie zum Entfernen eines bestimmten Knotens aus dem XML-DOM (Document Object Model) die <xref:System.Xml.XmlNode.RemoveChild%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="1af70-103">To remove a node from the XML Document Object Model (DOM), use the <xref:System.Xml.XmlNode.RemoveChild%2A> method to remove a specific node.</span></span> <span data-ttu-id="1af70-104">Beim Entfernen eines Knotens entfernt die Methode auch die zu diesem Knoten gehörende Teilstruktur, wenn es sich nicht um einen Endknoten handelt.</span><span class="sxs-lookup"><span data-stu-id="1af70-104">When you remove a node, the method removes the subtree belonging to the node being removed; that is, if it is not a leaf node.</span></span>  
  
 <span data-ttu-id="1af70-105">Wenn mehrere Knoten aus dem DOM entfernt werden sollen, entfernen Sie mit der <xref:System.Xml.XmlNode.RemoveAll%2A>-Methode alle untergeordneten Knoten und Attribute des aktuellen Knotens, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1af70-105">To remove multiple nodes from the DOM, use the <xref:System.Xml.XmlNode.RemoveAll%2A> method to remove all the children and attributes, if applicable, of the current node.</span></span>  
  
 <span data-ttu-id="1af70-106">Wenn Sie mit einer <xref:System.Xml.XmlNamedNodeMap> arbeiten, können Sie einen Knoten mit der <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A>-Methode entfernen.</span><span class="sxs-lookup"><span data-stu-id="1af70-106">If you are working with an <xref:System.Xml.XmlNamedNodeMap>, you can remove a node using the <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> method.</span></span>  
  
 <span data-ttu-id="1af70-107">Weitere Informationen zum Entfernen von Attributen finden Sie unter [Entfernen von Attributen aus einem Elementknoten im DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="1af70-107">To remove attributes, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af70-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1af70-108">See also</span></span>

- [<span data-ttu-id="1af70-109">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="1af70-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
