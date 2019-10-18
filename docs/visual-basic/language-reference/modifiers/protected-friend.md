---
title: Geschützter Freund (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: d3592feaece1d5ce85ee6e2657d8a2715c4097a3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524773"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="0ad7a-102">Geschützter Freund (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ad7a-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="0ad7a-103">Die Schlüsselwortkombination `Protected Friend` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="0ad7a-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="0ad7a-104">Sie überträgt sowohl [Friend](friend.md) -als auch [geschützten](protected.md) Zugriff auf die deklarierten Elemente, sodass Sie von überall in derselben Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen aus darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0ad7a-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="0ad7a-105">Sie können `Protected Friend` nur für Member von Klassen angeben. Sie können `Protected Friend` nicht auf Member einer Struktur anwenden, da Strukturen nicht vererbt werden können.</span><span class="sxs-lookup"><span data-stu-id="0ad7a-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="0ad7a-106">Wenn Sie in Visual Studio die F1-Hilfe auf `protected friend` auswählen, finden Sie Hilfe für den [geschützten](protected.md) oder den [Friend](friend.md)-.</span><span class="sxs-lookup"><span data-stu-id="0ad7a-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="0ad7a-107">Die IDE wählt anstelle des Verbund Worts das einzelne Token unter dem Cursor aus.</span><span class="sxs-lookup"><span data-stu-id="0ad7a-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="0ad7a-108">Regeln</span><span class="sxs-lookup"><span data-stu-id="0ad7a-108">Rules</span></span>

<span data-ttu-id="0ad7a-109">**Deklarations Kontext.**</span><span class="sxs-lookup"><span data-stu-id="0ad7a-109">**Declaration Context.**</span></span> <span data-ttu-id="0ad7a-110">Sie können `Protected Friend` nur auf Klassenebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ad7a-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="0ad7a-111">Dies bedeutet, dass der Deklarations Kontext für ein `Protected` Element eine Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="0ad7a-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ad7a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ad7a-112">See also</span></span>

- [<span data-ttu-id="0ad7a-113">Public</span><span class="sxs-lookup"><span data-stu-id="0ad7a-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="0ad7a-114">Protected</span><span class="sxs-lookup"><span data-stu-id="0ad7a-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="0ad7a-115">Friend</span><span class="sxs-lookup"><span data-stu-id="0ad7a-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="0ad7a-116">Private</span><span class="sxs-lookup"><span data-stu-id="0ad7a-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="0ad7a-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="0ad7a-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="0ad7a-118">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ad7a-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="0ad7a-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0ad7a-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="0ad7a-120">Strukturen</span><span class="sxs-lookup"><span data-stu-id="0ad7a-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="0ad7a-121">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="0ad7a-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
