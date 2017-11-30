---
title: "Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c041d5d2830222f3fae09a39f1ea10eb08772388
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="49f2e-102">Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten</span><span class="sxs-lookup"><span data-stu-id="49f2e-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="49f2e-103">Das Dokumentobjektmodell (DOM) überprüft beim Erstellen neuer Element- oder Attributknoten die Gültigkeit der Namen.</span><span class="sxs-lookup"><span data-stu-id="49f2e-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="49f2e-104">Wenn die Namen ungültige Zeichen enthalten, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="49f2e-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="49f2e-105">Um sicherzustellen, dass die Namen sind gültig und codierte ordnungsgemäß, müssen Sie die **XmlConvert** Klasse, um den Namen codieren und auf Anwendungsebene wieder decodieren.</span><span class="sxs-lookup"><span data-stu-id="49f2e-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="49f2e-106">Die **"XmlWriter"** Methoden stellen durch weitere Aktionen sicher, dass wohlgeformter XML-Code generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="49f2e-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f2e-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49f2e-107">See Also</span></span>  
 [<span data-ttu-id="49f2e-108">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="49f2e-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
