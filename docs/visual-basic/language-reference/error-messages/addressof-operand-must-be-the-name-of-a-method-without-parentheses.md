---
title: '&#39;AddressOf&#39; Operand muss der Name einer Methode (ohne Klammern)'
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 701d86e03d9b14236eec8436d99ec40cebbbcd44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583811"
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="a6253-102">&#39;AddressOf&#39; Operand muss der Name einer Methode (ohne Klammern)</span><span class="sxs-lookup"><span data-stu-id="a6253-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="a6253-103">Der `AddressOf` -Operator erstellt eine Delegatinstanz einer Prozedur, die auf eine bestimmte Prozedur verweist.</span><span class="sxs-lookup"><span data-stu-id="a6253-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="a6253-104">Die Syntax lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="a6253-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="a6253-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="a6253-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="a6253-106">Runden Klammern folgende Argument `AddressOf`, wobei keine erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a6253-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="a6253-107">**Fehler-ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="a6253-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a6253-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a6253-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="a6253-109">Entfernen Sie die Klammern um das folgende Argument `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="a6253-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="a6253-110">Stellen Sie sicher, dass das Argument ein Methodenname ist.</span><span class="sxs-lookup"><span data-stu-id="a6253-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6253-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6253-111">See Also</span></span>  
 [<span data-ttu-id="a6253-112">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="a6253-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="a6253-113">Delegaten</span><span class="sxs-lookup"><span data-stu-id="a6253-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
