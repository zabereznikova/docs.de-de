---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: b72cbee0394043620e792d1c014bfe55121e175e
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/18/2018
ms.locfileid: "34306541"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="f2fbd-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2fbd-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="f2fbd-103">Die Schlüsselwortkombination `Protected Friend` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="f2fbd-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="f2fbd-104">Er überträgt sowohl ["Friend"](friend.md) Zugriff und [geschützte](protected.md) Zugriff auf deklarierte Elemente, sodass sie über eine beliebige Stelle in der gleichen Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen zugänglich sind.</span><span class="sxs-lookup"><span data-stu-id="f2fbd-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="f2fbd-105">Sie können angeben, `Protected Friend` nur auf Member von Klassen; können nicht angewendet `Protected Friend` zu Membern einer Struktur da Strukturen können nicht vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="f2fbd-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="f2fbd-106">Wählen Sie in Visual Studio F1-Hilfe auf `protected friend` enthält die Hilfe für entweder [geschützt](protected.md) oder ["Friend"](friend.md).</span><span class="sxs-lookup"><span data-stu-id="f2fbd-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="f2fbd-107">Die IDE wählt der einzelnen Tokens, das unter den Cursor und nicht als zusammengesetztes Wort.</span><span class="sxs-lookup"><span data-stu-id="f2fbd-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="f2fbd-108">Regeln</span><span class="sxs-lookup"><span data-stu-id="f2fbd-108">Rules</span></span>

- <span data-ttu-id="f2fbd-109">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="f2fbd-109">**Declaration Context.**</span></span> <span data-ttu-id="f2fbd-110">Sie können `Protected Friend` nur auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="f2fbd-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="f2fbd-111">Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="f2fbd-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 


## <a name="see-also"></a><span data-ttu-id="f2fbd-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2fbd-112">See Also</span></span>

[<span data-ttu-id="f2fbd-113">Public</span><span class="sxs-lookup"><span data-stu-id="f2fbd-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
[<span data-ttu-id="f2fbd-114">Protected</span><span class="sxs-lookup"><span data-stu-id="f2fbd-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
<span data-ttu-id="f2fbd-115">["Friend"](friend.md) </span><span class="sxs-lookup"><span data-stu-id="f2fbd-115">[Friend](friend.md) </span></span>  
[<span data-ttu-id="f2fbd-116">Private</span><span class="sxs-lookup"><span data-stu-id="f2fbd-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
<span data-ttu-id="f2fbd-117">[Geschützt privat](./private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="f2fbd-117">[Private Protected](./private-protected.md) </span></span>  
[<span data-ttu-id="f2fbd-118">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f2fbd-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[<span data-ttu-id="f2fbd-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="f2fbd-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[<span data-ttu-id="f2fbd-120">Strukturen</span><span class="sxs-lookup"><span data-stu-id="f2fbd-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[<span data-ttu-id="f2fbd-121">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="f2fbd-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
