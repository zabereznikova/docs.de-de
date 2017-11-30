---
title: "Behandlung von Leerräumen und signifikanten Leerräumen beim Laden des DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 82401a18132801f9aa5368832b96be3cb67a8642
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a><span data-ttu-id="5dc85-102">Behandlung von Leerräumen und signifikanten Leerräumen beim Laden des DOM</span><span class="sxs-lookup"><span data-stu-id="5dc85-102">White Space and Significant White Space Handling when Loading the DOM</span></span>
<span data-ttu-id="5dc85-103">Beim Laden des Dokuments können Sie festlegen, dass die Option aus, um Leerraum beizubehalten, und erstellen Sie **XmlWhitespace** Knoten in der Dokumentstruktur.</span><span class="sxs-lookup"><span data-stu-id="5dc85-103">When loading the document, you can set the option to preserve white space and create **XmlWhitespace** nodes in the document tree.</span></span> <span data-ttu-id="5dc85-104">Zum Erstellen von Leerraumknoten legen die **PreserveWhitespace** Eigenschaft auf "true".</span><span class="sxs-lookup"><span data-stu-id="5dc85-104">To create white space nodes, set the **PreserveWhitespace** property to true.</span></span> <span data-ttu-id="5dc85-105">Wenn die Eigenschaft, um festgelegt wird **"false"**, Hierbei handelt es sich um die Standardeinstellung, Leerraumknoten nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5dc85-105">If the property is set to **false**, which is the default, white space nodes are not created.</span></span> <span data-ttu-id="5dc85-106">Knoten für signifikante Leerräume bleiben stets erhalten, und **XmlSignificantWhitespace** Knoten werden immer im Arbeitsspeicher, um diese Daten unabhängig von der Einstellung der darstellen, erstellt der **PreserveWhitespace** das Flag.</span><span class="sxs-lookup"><span data-stu-id="5dc85-106">Significant white spaces nodes are always preserved, and **XmlSignificantWhitespace** nodes are always created in memory to represent this data, regardless of the setting of the **PreserveWhitespace** flag.</span></span>  
  
 <span data-ttu-id="5dc85-107">Wenn das Dokument von einem Reader geladen wird, klicken Sie dann der Festlegen der **PreserveWhitespace** flag der Eigenschaft für die **XmlDocument** Klasse wirkt sich auf die Erstellung von **XmlWhitespace** Knoten nur, wenn die **WhitespaceHandling** Eigenschaft auf die **XmlTextReader** nicht festgelegt ist, um **WhitespaceHandling.None**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-107">If the document is loaded from a reader, then setting of the **PreserveWhitespace** flag property on the **XmlDocument** class affects the creation of **XmlWhitespace** nodes only when the **WhitespaceHandling** property on the **XmlTextReader** is not set to **WhitespaceHandling.None**.</span></span> <span data-ttu-id="5dc85-108">Ist der Wert, der die **WhitespaceHandling** Eigenschaft für den Reader an, die Vorrang vor der Einstellung dieses Flags auf enthält die **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-108">It is the value of the **WhitespaceHandling** property on the reader that takes precedence over the setting of that flag on the **XmlDocument**.</span></span> <span data-ttu-id="5dc85-109">Weitere Informationen zu **XmlSignificantWhitespace**, finden Sie unter <xref:System.Xml.XmlSignificantWhitespace>.</span><span class="sxs-lookup"><span data-stu-id="5dc85-109">For more information on **XmlSignificantWhitespace**, see <xref:System.Xml.XmlSignificantWhitespace>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc85-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dc85-110">See Also</span></span>  
 [<span data-ttu-id="5dc85-111">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="5dc85-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
