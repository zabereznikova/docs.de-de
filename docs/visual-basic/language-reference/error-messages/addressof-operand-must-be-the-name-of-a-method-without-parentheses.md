---
title: Der AddressOf-Operand muss dem Namen einer Methode entsprechen (ohne Klammern).
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: af1ce858108785fa4dac6352c9e80531e86fbb23
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813963"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="4f219-102">Der AddressOf-Operand muss dem Namen einer Methode entsprechen (ohne Klammern).</span><span class="sxs-lookup"><span data-stu-id="4f219-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="4f219-103">Der `AddressOf` -Operator erstellt eine Delegatinstanz einer Prozedur, die auf eine bestimmte Prozedur verweist.</span><span class="sxs-lookup"><span data-stu-id="4f219-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="4f219-104">Die Syntax lautet wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="4f219-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="4f219-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="4f219-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="4f219-106">Runden Klammern Folgendes Argument `AddressOf`, wo keine erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4f219-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="4f219-107">**Fehler-ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="4f219-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4f219-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4f219-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="4f219-109">Entfernen Sie die Klammern um die folgenden Argument `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="4f219-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="4f219-110">Stellen Sie sicher, dass das Argument den Namen einer Methode ist.</span><span class="sxs-lookup"><span data-stu-id="4f219-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f219-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f219-111">See also</span></span>

- [<span data-ttu-id="4f219-112">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="4f219-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="4f219-113">Delegaten</span><span class="sxs-lookup"><span data-stu-id="4f219-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
