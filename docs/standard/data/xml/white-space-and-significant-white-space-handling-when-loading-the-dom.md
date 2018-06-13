---
title: Behandlung von Leerräumen und signifikanten Leerräumen beim Laden des DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8e2279023029b5047cc7d9b4d0d97ac1f21e3f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569069"
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a><span data-ttu-id="2d27f-102">Behandlung von Leerräumen und signifikanten Leerräumen beim Laden des DOM</span><span class="sxs-lookup"><span data-stu-id="2d27f-102">White Space and Significant White Space Handling when Loading the DOM</span></span>
<span data-ttu-id="2d27f-103">Beim Laden des Dokuments können Sie festlegen, dass Leerraum beibehalten wird und in der Dokumentstruktur **XmlWhitespace**-Knoten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2d27f-103">When loading the document, you can set the option to preserve white space and create **XmlWhitespace** nodes in the document tree.</span></span> <span data-ttu-id="2d27f-104">Legen Sie die **PreserveWhitespace**-Eigenschaft auf „true“ fest, wenn Leerraumknoten erstellen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2d27f-104">To create white space nodes, set the **PreserveWhitespace** property to true.</span></span> <span data-ttu-id="2d27f-105">Wenn die Eigenschaft auf **false** festgelegt wird (Standardeinstellung), werden keine Leerraumknoten erstellt.</span><span class="sxs-lookup"><span data-stu-id="2d27f-105">If the property is set to **false**, which is the default, white space nodes are not created.</span></span> <span data-ttu-id="2d27f-106">Knoten für signifikante Leerräume bleiben stets erhalten, und **XmlSignificantWhitespace**-Knoten werden ungeachtet der Einstellung des **PreserveWhitespace**-Flags stets im Speicher erstellt, um diese Daten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="2d27f-106">Significant white spaces nodes are always preserved, and **XmlSignificantWhitespace** nodes are always created in memory to represent this data, regardless of the setting of the **PreserveWhitespace** flag.</span></span>  
  
 <span data-ttu-id="2d27f-107">Wenn das Dokument aus einem Reader geladen wird, beeinflusst die Einstellung der **PreserveWhitespace**-Eigenschaft für die **XmlDocument**-Klasse nur dann das Erstellen von **XmlWhitespace**-Knoten, wenn die **WhitespaceHandling**-Eigenschaft des **XmlTextReader** nicht auf **WhitespaceHandling.None** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2d27f-107">If the document is loaded from a reader, then setting of the **PreserveWhitespace** flag property on the **XmlDocument** class affects the creation of **XmlWhitespace** nodes only when the **WhitespaceHandling** property on the **XmlTextReader** is not set to **WhitespaceHandling.None**.</span></span> <span data-ttu-id="2d27f-108">Der Wert der **WhitespaceHandling**-Eigenschaft des Readers hat Vorrang vor der Einstellung dieses Flags für das **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="2d27f-108">It is the value of the **WhitespaceHandling** property on the reader that takes precedence over the setting of that flag on the **XmlDocument**.</span></span> <span data-ttu-id="2d27f-109">Weitere Informationen zu **XmlSignificantWhitespace** finden Sie unter <xref:System.Xml.XmlSignificantWhitespace>.</span><span class="sxs-lookup"><span data-stu-id="2d27f-109">For more information on **XmlSignificantWhitespace**, see <xref:System.Xml.XmlSignificantWhitespace>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d27f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d27f-110">See Also</span></span>  
 [<span data-ttu-id="2d27f-111">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="2d27f-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
