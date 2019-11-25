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
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="a9b03-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9b03-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="a9b03-103">Die Schlüsselwortkombination `Protected Friend` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="a9b03-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="a9b03-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span><span class="sxs-lookup"><span data-stu-id="a9b03-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="a9b03-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span><span class="sxs-lookup"><span data-stu-id="a9b03-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="a9b03-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span><span class="sxs-lookup"><span data-stu-id="a9b03-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="a9b03-107">The IDE picks the single token under the cursor rather than the compound word.</span><span class="sxs-lookup"><span data-stu-id="a9b03-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="a9b03-108">Regeln</span><span class="sxs-lookup"><span data-stu-id="a9b03-108">Rules</span></span>

<span data-ttu-id="a9b03-109">**Declaration Context.**</span><span class="sxs-lookup"><span data-stu-id="a9b03-109">**Declaration Context.**</span></span> <span data-ttu-id="a9b03-110">You can use `Protected Friend` only at the class level.</span><span class="sxs-lookup"><span data-stu-id="a9b03-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="a9b03-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span><span class="sxs-lookup"><span data-stu-id="a9b03-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9b03-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9b03-112">See also</span></span>

- [<span data-ttu-id="a9b03-113">Public</span><span class="sxs-lookup"><span data-stu-id="a9b03-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="a9b03-114">Protected</span><span class="sxs-lookup"><span data-stu-id="a9b03-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="a9b03-115">Friend</span><span class="sxs-lookup"><span data-stu-id="a9b03-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="a9b03-116">Private</span><span class="sxs-lookup"><span data-stu-id="a9b03-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="a9b03-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="a9b03-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="a9b03-118">Access levels in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9b03-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="a9b03-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="a9b03-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="a9b03-120">Strukturen</span><span class="sxs-lookup"><span data-stu-id="a9b03-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a9b03-121">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="a9b03-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
