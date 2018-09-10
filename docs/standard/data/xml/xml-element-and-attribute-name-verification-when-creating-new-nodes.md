---
title: Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 008cf14e63b8458feebf26eaf27be516bb79f933
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216040"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="deb2e-102">Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten</span><span class="sxs-lookup"><span data-stu-id="deb2e-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="deb2e-103">Das Dokumentobjektmodell (DOM) überprüft beim Erstellen neuer Element- oder Attributknoten die Gültigkeit der Namen.</span><span class="sxs-lookup"><span data-stu-id="deb2e-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="deb2e-104">Wenn die Namen ungültige Zeichen enthalten, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="deb2e-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="deb2e-105">Wenn Sie sicherstellen möchten, dass die Namen gültig und korrekt codiert sind, müssen Sie diese mithilfe der **XmlConvert**-Klasse codieren und auf Anwendungsebene wieder decodieren.</span><span class="sxs-lookup"><span data-stu-id="deb2e-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="deb2e-106">Die in **XmlWriter** enthaltenen Methoden stellen durch weitere Aktionen sicher, dass wohlgeformter XML-Code generiert wird.</span><span class="sxs-lookup"><span data-stu-id="deb2e-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb2e-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="deb2e-107">See also</span></span>

- [<span data-ttu-id="deb2e-108">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="deb2e-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
