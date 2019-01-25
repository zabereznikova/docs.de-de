---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 1858411e5543448e6d822c97b6e5c18da4a6c11e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639600"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="5544c-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5544c-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="5544c-103">Die Schlüsselwortkombination `Protected Friend` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="5544c-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="5544c-104">Es bietet sowohl [Friend](friend.md) Zugriff und [geschützte](protected.md) der deklarierten Elemente, damit sie über eine beliebige Stelle in der gleichen Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen zugänglich sind.</span><span class="sxs-lookup"><span data-stu-id="5544c-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="5544c-105">Sie können angeben, `Protected Friend` nur auf Member von Klassen; Sie können nicht angewendet werden `Protected Friend` zu Membern einer Struktur da Strukturen nicht geerbt werden können.</span><span class="sxs-lookup"><span data-stu-id="5544c-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="5544c-106">Wählen Sie in Visual Studio F1-Hilfe auf `protected friend` enthält die Hilfe für entweder [geschützt](protected.md) oder [Friend](friend.md).</span><span class="sxs-lookup"><span data-stu-id="5544c-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="5544c-107">Die IDE wählt die einzelne Token unter dem Cursor anstatt der zusammengesetzte Begriff.</span><span class="sxs-lookup"><span data-stu-id="5544c-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="5544c-108">Regeln</span><span class="sxs-lookup"><span data-stu-id="5544c-108">Rules</span></span>

- <span data-ttu-id="5544c-109">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="5544c-109">**Declaration Context.**</span></span> <span data-ttu-id="5544c-110">Sie können `Protected Friend` nur auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="5544c-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="5544c-111">Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="5544c-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 


## <a name="see-also"></a><span data-ttu-id="5544c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5544c-112">See also</span></span>

- [<span data-ttu-id="5544c-113">Public</span><span class="sxs-lookup"><span data-stu-id="5544c-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="5544c-114">Protected</span><span class="sxs-lookup"><span data-stu-id="5544c-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="5544c-115">Friend</span><span class="sxs-lookup"><span data-stu-id="5544c-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="5544c-116">Private</span><span class="sxs-lookup"><span data-stu-id="5544c-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="5544c-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="5544c-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="5544c-118">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5544c-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="5544c-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="5544c-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="5544c-120">Strukturen</span><span class="sxs-lookup"><span data-stu-id="5544c-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="5544c-121">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="5544c-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
