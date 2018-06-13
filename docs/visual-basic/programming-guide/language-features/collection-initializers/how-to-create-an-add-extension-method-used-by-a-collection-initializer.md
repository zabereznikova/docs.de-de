---
title: 'Gewusst wie: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 5e35ad80037e843fd3cbd9caa68dcb2a09d707e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646239"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="7b673-102">Gewusst wie: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b673-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="7b673-103">Wenn Sie einen Auflistungsinitialisierer verwenden, um eine Sammlung erstellen, sucht Visual Basic-Compiler für eine `Add` Methode des Auflistungstyps, für die die Parameter für die `Add` Methode überein, die die Typen der Werte im Auflistungsinitialisierer.</span><span class="sxs-lookup"><span data-stu-id="7b673-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="7b673-104">Dies `Add` Methode beim Auffüllen der Auflistung mit den Werten aus den Auflistungsinitialisierer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7b673-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="7b673-105">Wenn kein übereinstimmender `Add` Methode vorhanden ist und den Code für die Sammlung kann nicht geändert, können Sie eine Erweiterungsmethode namens hinzufügen `Add` , akzeptiert der Parameter, die für den Auflistungsinitialisierer erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7b673-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="7b673-106">Dies ist in der Regel an, was Sie tun, wenn Sie Auflistungsinitialisierer für generische Auflistungen verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="7b673-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b673-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b673-107">Example</span></span>  
 <span data-ttu-id="7b673-108">Im folgende Beispiel wird gezeigt, wie die generische Erweiterungsmethode hinzuzufügende <xref:System.Collections.Generic.List%601> geben, sodass ein Auflistungsinitialisierer verwendet werden kann, um Objekte eines Typs hinzuzufügen `Employee`.</span><span class="sxs-lookup"><span data-stu-id="7b673-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="7b673-109">Die Erweiterungsmethode können Sie die gekürzte Auflistungsinitialisierersyntax zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b673-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7b673-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b673-110">See Also</span></span>  
 [<span data-ttu-id="7b673-111">Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="7b673-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [<span data-ttu-id="7b673-112">Gewusst wie: Erstellen einer Auflistung für einen Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="7b673-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
