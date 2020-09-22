---
title: Vorangestellte "." oder "!" können nur in einer With-Anweisung verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: c39339a49c4aad4ba643facc2372333e7379ffa7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873845"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="80e21-102">Vorangestellte "." oder "!" können nur in einer With-Anweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="80e21-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>

<span data-ttu-id="80e21-103">Ein Punkt (.) oder ein Ausrufezeichen (!), das sich nicht in einem-Block befindet, `With` tritt ohne einen Ausdruck auf der linken Seite auf.</span><span class="sxs-lookup"><span data-stu-id="80e21-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="80e21-104">Member Access ( `.` ) und Dictionary Member Access ( `!` ) erfordern einen Ausdruck, der das Element angibt, das den Member enthält.</span><span class="sxs-lookup"><span data-stu-id="80e21-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="80e21-105">Dieser muss direkt links neben dem-Accessor oder als Ziel eines Blocks angezeigt werden, der `With` den Member-Zugriff enthält.</span><span class="sxs-lookup"><span data-stu-id="80e21-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="80e21-106">**Fehler-ID:** BC30157</span><span class="sxs-lookup"><span data-stu-id="80e21-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="80e21-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="80e21-107">To correct this error</span></span>  
  
1. <span data-ttu-id="80e21-108">Stellen Sie sicher, dass der `With` Block korrekt formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="80e21-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2. <span data-ttu-id="80e21-109">Wenn kein-Block vorhanden ist `With` , fügen Sie links neben dem Accessor einen Ausdruck hinzu, der zu einem definierten Element ausgewertet wird, das den Member enthält.</span><span class="sxs-lookup"><span data-stu-id="80e21-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80e21-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80e21-110">See also</span></span>

- [<span data-ttu-id="80e21-111">Sonderzeichen in Code</span><span class="sxs-lookup"><span data-stu-id="80e21-111">Special Characters in Code</span></span>](../../programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="80e21-112">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="80e21-112">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
