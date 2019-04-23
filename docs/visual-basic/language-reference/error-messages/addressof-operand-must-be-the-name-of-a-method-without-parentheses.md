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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323823"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="230b7-102">Der AddressOf-Operand muss dem Namen einer Methode entsprechen (ohne Klammern).</span><span class="sxs-lookup"><span data-stu-id="230b7-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="230b7-103">Der `AddressOf` -Operator erstellt eine Delegatinstanz einer Prozedur, die auf eine bestimmte Prozedur verweist.</span><span class="sxs-lookup"><span data-stu-id="230b7-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="230b7-104">Die Syntax lautet wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="230b7-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="230b7-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="230b7-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="230b7-106">Runden Klammern Folgendes Argument `AddressOf`, wo keine erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="230b7-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="230b7-107">**Fehler-ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="230b7-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="230b7-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="230b7-108">To correct this error</span></span>  
  
1. <span data-ttu-id="230b7-109">Entfernen Sie die Klammern um die folgenden Argument `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="230b7-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2. <span data-ttu-id="230b7-110">Stellen Sie sicher, dass das Argument den Namen einer Methode ist.</span><span class="sxs-lookup"><span data-stu-id="230b7-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="230b7-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="230b7-111">See also</span></span>

- [<span data-ttu-id="230b7-112">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="230b7-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="230b7-113">Delegaten</span><span class="sxs-lookup"><span data-stu-id="230b7-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
