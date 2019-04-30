---
title: 'Vorgehensweise: Erstellen einer Add-Erweiterungsmethode, die einen Auflistungsinitialisierer (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: a5af41e25b8f82aa173e2df28cc41b313c8d68dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907074"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="0ef01-102">Vorgehensweise: Erstellen einer Add-Erweiterungsmethode, die einen Auflistungsinitialisierer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ef01-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="0ef01-103">Wenn Sie einen Auflistungsinitialisierer verwenden, um eine Sammlung erstellen, sucht Visual Basic-Compiler nach einer `Add` Methode des Auflistungstyps, für die die Parameter für die `Add` Methode entsprechen den Typen der Werte im Auflistungsinitialisierer.</span><span class="sxs-lookup"><span data-stu-id="0ef01-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="0ef01-104">Dies `Add` Methode zum Auffüllen der Auflistung mit den Werten aus der Auflistungsinitialisierer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ef01-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="0ef01-105">Wenn kein übereinstimmendes `Add` Methode vorhanden ist und Sie können den Code für die Sammlung können nicht ändern, können Sie eine Erweiterungsmethode namens hinzufügen `Add` , akzeptiert die Parameter, die den Auflistungsinitialisierer erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0ef01-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="0ef01-106">Dies ist normalerweise das, was Sie tun, wenn Sie die Auflistungsinitialisierer für generische Auflistungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ef01-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ef01-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ef01-107">Example</span></span>  
 <span data-ttu-id="0ef01-108">Das folgende Beispiel zeigt, wie Sie eine Erweiterungsmethode zu den allgemeinen hinzufügen <xref:System.Collections.Generic.List%601> geben, damit ein Auflistungsinitialisierer verwendet werden kann, zum Hinzufügen von Objekten des Typs `Employee`.</span><span class="sxs-lookup"><span data-stu-id="0ef01-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="0ef01-109">Die Erweiterungsmethode können Sie die gekürzte Auflistungsinitialisierersyntax zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ef01-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="0ef01-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ef01-110">See also</span></span>

- [<span data-ttu-id="0ef01-111">Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="0ef01-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="0ef01-112">Vorgehensweise: Erstellen Sie von einem Auflistungsinitialisierer verwendete Auflistung</span><span class="sxs-lookup"><span data-stu-id="0ef01-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
