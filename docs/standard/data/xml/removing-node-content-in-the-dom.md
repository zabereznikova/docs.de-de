---
title: Entfernen von Knoteninhalt im Dokumentobjektmodell
ms.date: 03/30/2017
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
ms.openlocfilehash: 7b33ebfea244dbe81879c61be3809adcb2a1f5d3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828867"
---
# <a name="removing-node-content-in-the-dom"></a><span data-ttu-id="32183-102">Entfernen von Knoteninhalt im Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="32183-102">Removing Node Content in the DOM</span></span>
<span data-ttu-id="32183-103">Bei Knotentypen, die von <xref:System.Xml.XmlCharacterData> erben (die Knotentypen <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace> und <xref:System.Xml.XmlSignificantWhitespace>), können Sie Zeichen mithilfe der <xref:System.Xml.XmlCharacterData.DeleteData%2A>-Methode entfernen. Diese löscht einen Bereich von Zeichen aus dem Knoten.</span><span class="sxs-lookup"><span data-stu-id="32183-103">For node types that inherit from <xref:System.Xml.XmlCharacterData>, which are the <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, and <xref:System.Xml.XmlSignificantWhitespace> node types, you can remove characters using the <xref:System.Xml.XmlCharacterData.DeleteData%2A> method, which removes a range of characters from the node.</span></span> <span data-ttu-id="32183-104">Wenn Sie Inhalte vollständig löschen möchten, entfernen Sie den Knoten, in dem der betreffende Inhalt vorliegt.</span><span class="sxs-lookup"><span data-stu-id="32183-104">If you want to remove content completely, you remove the node that contains the content.</span></span> <span data-ttu-id="32183-105">Wenn der Knoten erhalten bleiben soll, der Inhalt jedoch falsch ist, dann ändern Sie den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="32183-105">If you want to keep the node, but the content is incorrect, then modify the content.</span></span> <span data-ttu-id="32183-106">Weitere Informationen zum Ändern des Inhalts eines Knotens finden Sie unter [Ändern von Knoten, Inhalten und Werten in einem XML-Dokument](modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="32183-106">For information on modifying the content of a node, see [Modifying Nodes, Content, and Values in an XML Document](modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32183-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32183-107">See also</span></span>

- [<span data-ttu-id="32183-108">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="32183-108">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
