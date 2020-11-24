---
title: Kopieren von vorhandenen Knoten
ms.date: 03/30/2017
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: b4ae24f9776456033a876e8ae4d1515d2f669fe0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830947"
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="1086c-102">Kopieren von vorhandenen Knoten</span><span class="sxs-lookup"><span data-stu-id="1086c-102">Copy Existing Nodes</span></span>
<span data-ttu-id="1086c-103">Ein Knoten kann mit vielen Methoden und Eigenschaften des DOM (XML Document Object Model) ausgewählt werden, z.B. mit **SelectSingleNode**, **ChildNodes[int i]** oder **Attributes[int i]** .</span><span class="sxs-lookup"><span data-stu-id="1086c-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="1086c-104">Nachdem der Knoten ausgewählt wurde, können Sie ihn mit einer der Einfügemethoden, die für diesen speziellen Knotentyp gültig sind, in die Struktur einfügen.</span><span class="sxs-lookup"><span data-stu-id="1086c-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="1086c-105">Die einzige Bedingung für das Einfügen eines Knotens in die Struktur besteht darin, dass das Dokument nach dem Einfügen des Knotens immer noch wohlgeformt sein muss.</span><span class="sxs-lookup"><span data-stu-id="1086c-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="1086c-106">Wird ein vorhandener Knoten in die DOM-Struktur eingefügt, wird er aus seiner ursprünglichen Position entfernt und an der Zielposition eingefügt.</span><span class="sxs-lookup"><span data-stu-id="1086c-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1086c-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1086c-107">See also</span></span>

- [<span data-ttu-id="1086c-108">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="1086c-108">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
