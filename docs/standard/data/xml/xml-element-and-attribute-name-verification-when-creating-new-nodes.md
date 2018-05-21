---
title: Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de11c190310dec90bd23d044f77d0c38e3a34fcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="494e8-102">Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten</span><span class="sxs-lookup"><span data-stu-id="494e8-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="494e8-103">Das Dokumentobjektmodell (DOM) überprüft beim Erstellen neuer Element- oder Attributknoten die Gültigkeit der Namen.</span><span class="sxs-lookup"><span data-stu-id="494e8-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="494e8-104">Wenn die Namen ungültige Zeichen enthalten, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="494e8-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="494e8-105">Wenn Sie sicherstellen möchten, dass die Namen gültig und korrekt codiert sind, müssen Sie diese mithilfe der **XmlConvert**-Klasse codieren und auf Anwendungsebene wieder decodieren.</span><span class="sxs-lookup"><span data-stu-id="494e8-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="494e8-106">Die in **XmlWriter** enthaltenen Methoden stellen durch weitere Aktionen sicher, dass wohlgeformter XML-Code generiert wird.</span><span class="sxs-lookup"><span data-stu-id="494e8-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="494e8-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="494e8-107">See Also</span></span>  
 [<span data-ttu-id="494e8-108">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="494e8-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
