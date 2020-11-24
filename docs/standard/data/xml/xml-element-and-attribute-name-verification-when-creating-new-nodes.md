---
title: Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten
ms.date: 03/30/2017
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
ms.openlocfilehash: 0678f7daf5276a905ce890a5f6a0f64993fb08b0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828816"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="bc4a1-102">Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten</span><span class="sxs-lookup"><span data-stu-id="bc4a1-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="bc4a1-103">Das Dokumentobjektmodell (DOM) überprüft beim Erstellen neuer Element- oder Attributknoten die Gültigkeit der Namen.</span><span class="sxs-lookup"><span data-stu-id="bc4a1-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="bc4a1-104">Wenn die Namen ungültige Zeichen enthalten, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="bc4a1-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="bc4a1-105">Wenn Sie sicherstellen möchten, dass die Namen gültig und korrekt codiert sind, müssen Sie diese mithilfe der **XmlConvert**-Klasse codieren und auf Anwendungsebene wieder decodieren.</span><span class="sxs-lookup"><span data-stu-id="bc4a1-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="bc4a1-106">Die in **XmlWriter** enthaltenen Methoden stellen durch weitere Aktionen sicher, dass wohlgeformter XML-Code generiert wird.</span><span class="sxs-lookup"><span data-stu-id="bc4a1-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc4a1-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc4a1-107">See also</span></span>

- [<span data-ttu-id="bc4a1-108">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="bc4a1-108">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
