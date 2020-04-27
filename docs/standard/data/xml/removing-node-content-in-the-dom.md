---
title: Entfernen von Knoteninhalt im Dokumentobjektmodell
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
ms.openlocfilehash: f5086bdea8ff1f0ee5329f347223ebb4a6bd71da
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710335"
---
# <a name="removing-node-content-in-the-dom"></a><span data-ttu-id="3e041-102">Entfernen von Knoteninhalt im Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="3e041-102">Removing Node Content in the DOM</span></span>
<span data-ttu-id="3e041-103">Bei Knotentypen, die von <xref:System.Xml.XmlCharacterData> erben (die Knotentypen <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace> und <xref:System.Xml.XmlSignificantWhitespace>), können Sie Zeichen mithilfe der <xref:System.Xml.XmlCharacterData.DeleteData%2A>-Methode entfernen. Diese löscht einen Bereich von Zeichen aus dem Knoten.</span><span class="sxs-lookup"><span data-stu-id="3e041-103">For node types that inherit from <xref:System.Xml.XmlCharacterData>, which are the <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, and <xref:System.Xml.XmlSignificantWhitespace> node types, you can remove characters using the <xref:System.Xml.XmlCharacterData.DeleteData%2A> method, which removes a range of characters from the node.</span></span> <span data-ttu-id="3e041-104">Wenn Sie Inhalte vollständig löschen möchten, entfernen Sie den Knoten, in dem der betreffende Inhalt vorliegt.</span><span class="sxs-lookup"><span data-stu-id="3e041-104">If you want to remove content completely, you remove the node that contains the content.</span></span> <span data-ttu-id="3e041-105">Wenn der Knoten erhalten bleiben soll, der Inhalt jedoch falsch ist, dann ändern Sie den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="3e041-105">If you want to keep the node, but the content is incorrect, then modify the content.</span></span> <span data-ttu-id="3e041-106">Weitere Informationen zum Ändern des Inhalts eines Knotens finden Sie unter [Ändern von Knoten, Inhalten und Werten in einem XML-Dokument](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="3e041-106">For information on modifying the content of a node, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e041-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e041-107">See also</span></span>

- [<span data-ttu-id="3e041-108">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="3e041-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
