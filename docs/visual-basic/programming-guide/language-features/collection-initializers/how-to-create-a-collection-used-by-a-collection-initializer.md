---
title: 'Vorgehensweise: Erstellen einer Auflistung für einen Auflistungsinitialisierer'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: b332ffb44ebc20ce8431e586fc380b8c6a29967d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086373"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="449fe-102">Gewusst wie: Erstellen einer Auflistung für einen Auflistungsinitialisierer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="449fe-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>

<span data-ttu-id="449fe-103">Wenn Sie einen Auflistungsinitialisierer zum Erstellen einer Auflistung verwenden, sucht der Visual Basic Compiler nach einer Methode des Auflistungs `Add` Typs, für den die Parameter für die `Add` Methode mit den Typen der Werte im sammlungsinitialisierer verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="449fe-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="449fe-104">Diese `Add` Methode wird verwendet, um die Auflistung mit den Werten aus dem Auflistungsinitialisierer aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="449fe-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="449fe-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="449fe-105">Example</span></span>  

 <span data-ttu-id="449fe-106">Das folgende Beispiel zeigt eine-Auflistung `OrderCollection` , die eine öffentliche `Add` Methode enthält, die ein Auflistungsinitialisierer zum Hinzufügen von Objekten des Typs verwenden kann `Order` .</span><span class="sxs-lookup"><span data-stu-id="449fe-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="449fe-107">Mit der- `Add` Methode können Sie die gekürzte sammlungsinitialisierersyntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="449fe-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="449fe-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="449fe-108">See also</span></span>

- [<span data-ttu-id="449fe-109">Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="449fe-109">Collection Initializers</span></span>](index.md)
- [<span data-ttu-id="449fe-110">Vorgehensweise: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="449fe-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
