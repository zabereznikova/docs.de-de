---
title: Protected Friend
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: f92021f5f0dab9762470c270bdd5182187d587e5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351324"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="62ba1-102">Geschützter Freund (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62ba1-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="62ba1-103">Die Schlüsselwortkombination `Protected Friend` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="62ba1-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="62ba1-104">Sie überträgt sowohl [Friend](friend.md) -als auch [geschützten](protected.md) Zugriff auf die deklarierten Elemente, sodass Sie von überall in derselben Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen aus darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="62ba1-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="62ba1-105">Sie können `Protected Friend` nur für Member von Klassen angeben. Sie können `Protected Friend` nicht auf Member einer Struktur anwenden, da Strukturen nicht vererbt werden können.</span><span class="sxs-lookup"><span data-stu-id="62ba1-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="62ba1-106">Wenn Sie in Visual Studio die F1-Hilfe auf `protected friend` auswählen, finden Sie Hilfe für den [geschützten](protected.md) oder den [Friend](friend.md)-.</span><span class="sxs-lookup"><span data-stu-id="62ba1-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="62ba1-107">Die IDE wählt anstelle des Verbund Worts das einzelne Token unter dem Cursor aus.</span><span class="sxs-lookup"><span data-stu-id="62ba1-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="62ba1-108">Regeln</span><span class="sxs-lookup"><span data-stu-id="62ba1-108">Rules</span></span>

<span data-ttu-id="62ba1-109">**Deklarations Kontext.**</span><span class="sxs-lookup"><span data-stu-id="62ba1-109">**Declaration Context.**</span></span> <span data-ttu-id="62ba1-110">Sie können `Protected Friend` nur auf Klassenebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="62ba1-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="62ba1-111">Dies bedeutet, dass der Deklarations Kontext für ein `Protected` Element eine Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="62ba1-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="62ba1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62ba1-112">See also</span></span>

- [<span data-ttu-id="62ba1-113">Public</span><span class="sxs-lookup"><span data-stu-id="62ba1-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="62ba1-114">Protected</span><span class="sxs-lookup"><span data-stu-id="62ba1-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="62ba1-115">Friend</span><span class="sxs-lookup"><span data-stu-id="62ba1-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="62ba1-116">Private</span><span class="sxs-lookup"><span data-stu-id="62ba1-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="62ba1-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="62ba1-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="62ba1-118">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62ba1-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="62ba1-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="62ba1-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="62ba1-120">Strukturen</span><span class="sxs-lookup"><span data-stu-id="62ba1-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="62ba1-121">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="62ba1-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
