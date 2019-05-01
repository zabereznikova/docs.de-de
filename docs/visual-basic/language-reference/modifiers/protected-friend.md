---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 331c63dc290d4096e8158f265ee869b47743a273
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053885"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="d7172-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7172-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="d7172-103">Die Schlüsselwortkombination `Protected Friend` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="d7172-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="d7172-104">Es bietet sowohl [Friend](friend.md) Zugriff und [geschützte](protected.md) der deklarierten Elemente, damit sie über eine beliebige Stelle in der gleichen Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen zugänglich sind.</span><span class="sxs-lookup"><span data-stu-id="d7172-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="d7172-105">Sie können angeben, `Protected Friend` nur auf Member von Klassen; Sie können nicht angewendet werden `Protected Friend` zu Membern einer Struktur da Strukturen nicht geerbt werden können.</span><span class="sxs-lookup"><span data-stu-id="d7172-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="d7172-106">Wählen Sie in Visual Studio F1-Hilfe auf `protected friend` enthält die Hilfe für entweder [geschützt](protected.md) oder [Friend](friend.md).</span><span class="sxs-lookup"><span data-stu-id="d7172-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="d7172-107">Die IDE wählt die einzelne Token unter dem Cursor anstatt der zusammengesetzte Begriff.</span><span class="sxs-lookup"><span data-stu-id="d7172-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="d7172-108">Regeln</span><span class="sxs-lookup"><span data-stu-id="d7172-108">Rules</span></span>

- <span data-ttu-id="d7172-109">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="d7172-109">**Declaration Context.**</span></span> <span data-ttu-id="d7172-110">Sie können `Protected Friend` nur auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="d7172-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="d7172-111">Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="d7172-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 

## <a name="see-also"></a><span data-ttu-id="d7172-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7172-112">See also</span></span>

- [<span data-ttu-id="d7172-113">Public</span><span class="sxs-lookup"><span data-stu-id="d7172-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="d7172-114">Protected</span><span class="sxs-lookup"><span data-stu-id="d7172-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="d7172-115">Friend</span><span class="sxs-lookup"><span data-stu-id="d7172-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="d7172-116">Private</span><span class="sxs-lookup"><span data-stu-id="d7172-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="d7172-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="d7172-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="d7172-118">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7172-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="d7172-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d7172-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="d7172-120">Strukturen</span><span class="sxs-lookup"><span data-stu-id="d7172-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="d7172-121">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="d7172-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
