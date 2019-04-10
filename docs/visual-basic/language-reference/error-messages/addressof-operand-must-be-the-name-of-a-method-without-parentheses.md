---
title: Der AddressOf-Operand muss dem Namen einer Methode entsprechen (ohne Klammern).
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: b8c67c2390df91c6a4af66e020365544e6bf369b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323823"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="41d54-102">Der AddressOf-Operand muss dem Namen einer Methode entsprechen (ohne Klammern).</span><span class="sxs-lookup"><span data-stu-id="41d54-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="41d54-103">Der `AddressOf` -Operator erstellt eine Delegatinstanz einer Prozedur, die auf eine bestimmte Prozedur verweist.</span><span class="sxs-lookup"><span data-stu-id="41d54-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="41d54-104">Die Syntax lautet wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="41d54-104">The syntax is as follows.</span></span>  
  
 `AddressOf` `procedurename`  
  
 <span data-ttu-id="41d54-105">Runden Klammern Folgendes Argument `AddressOf`, wo keine erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="41d54-105">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="41d54-106">**Fehler-ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="41d54-106">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="41d54-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="41d54-107">To correct this error</span></span>  
  
1. <span data-ttu-id="41d54-108">Entfernen Sie die Klammern um die folgenden Argument `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="41d54-108">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2. <span data-ttu-id="41d54-109">Stellen Sie sicher, dass das Argument den Namen einer Methode ist.</span><span class="sxs-lookup"><span data-stu-id="41d54-109">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d54-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41d54-110">See also</span></span>

- [<span data-ttu-id="41d54-111">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="41d54-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="41d54-112">Delegaten</span><span class="sxs-lookup"><span data-stu-id="41d54-112">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
