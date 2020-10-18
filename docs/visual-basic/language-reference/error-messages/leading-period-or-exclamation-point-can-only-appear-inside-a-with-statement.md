---
title: Vorangestellte "." oder "!" können nur in einer With-Anweisung verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 4ff273d5930fe58a5bccf0f4f4c10e971d777d01
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162504"
---
# <a name="bc30157-leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="18274-102">BC30157: die führende "." oder "!" können nur in einer with-Anweisung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="18274-102">BC30157: Leading '.' or '!' can only appear inside a 'With' statement</span></span>

<span data-ttu-id="18274-103">Ein Punkt (.) oder ein Ausrufezeichen (!), das sich nicht in einem-Block befindet, `With` tritt ohne einen Ausdruck auf der linken Seite auf.</span><span class="sxs-lookup"><span data-stu-id="18274-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="18274-104">Member Access ( `.` ) und Dictionary Member Access ( `!` ) erfordern einen Ausdruck, der das Element angibt, das den Member enthält.</span><span class="sxs-lookup"><span data-stu-id="18274-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="18274-105">Dieser muss direkt links neben dem-Accessor oder als Ziel eines Blocks angezeigt werden, der `With` den Member-Zugriff enthält.</span><span class="sxs-lookup"><span data-stu-id="18274-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>

 <span data-ttu-id="18274-106">**Fehler-ID:** BC30157</span><span class="sxs-lookup"><span data-stu-id="18274-106">**Error ID:** BC30157</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="18274-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="18274-107">To correct this error</span></span>

1. <span data-ttu-id="18274-108">Stellen Sie sicher, dass der `With` Block korrekt formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="18274-108">Ensure that the `With` block is correctly formatted.</span></span>

2. <span data-ttu-id="18274-109">Wenn kein-Block vorhanden ist `With` , fügen Sie links neben dem Accessor einen Ausdruck hinzu, der zu einem definierten Element ausgewertet wird, das den Member enthält.</span><span class="sxs-lookup"><span data-stu-id="18274-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>

## <a name="see-also"></a><span data-ttu-id="18274-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18274-110">See also</span></span>

- [<span data-ttu-id="18274-111">Sonderzeichen in Code</span><span class="sxs-lookup"><span data-stu-id="18274-111">Special Characters in Code</span></span>](../../programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="18274-112">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="18274-112">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
