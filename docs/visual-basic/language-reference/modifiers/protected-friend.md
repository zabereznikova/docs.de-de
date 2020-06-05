---
title: Protected Friend
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 202d4f4a3a05a64ab1d74621268f28f6b55e8952
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404835"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="4a189-102">Geschützter Freund (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a189-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="4a189-103">Die Schlüsselwortkombination `Protected Friend` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="4a189-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="4a189-104">Sie überträgt sowohl [Friend](friend.md) -als auch [geschützten](protected.md) Zugriff auf die deklarierten Elemente, sodass Sie von überall in derselben Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen aus darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="4a189-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="4a189-105">Sie können `Protected Friend` nur für Member von Klassen angeben. Sie können nicht auf Member einer Struktur anwenden, `Protected Friend` da Strukturen nicht vererbt werden können.</span><span class="sxs-lookup"><span data-stu-id="4a189-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="4a189-106">Wenn Sie in Visual Studio die F1-Hilfe in auswählen, erhalten Sie `protected friend` Hilfe für den [geschützten](protected.md) oder einen [Friend](friend.md)-.</span><span class="sxs-lookup"><span data-stu-id="4a189-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="4a189-107">Die IDE wählt anstelle des Verbund Worts das einzelne Token unter dem Cursor aus.</span><span class="sxs-lookup"><span data-stu-id="4a189-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="4a189-108">Regeln</span><span class="sxs-lookup"><span data-stu-id="4a189-108">Rules</span></span>

<span data-ttu-id="4a189-109">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="4a189-109">**Declaration Context.**</span></span> <span data-ttu-id="4a189-110">Sie können `Protected Friend` nur auf Klassenebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a189-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="4a189-111">Dies bedeutet, dass der Deklarations Kontext für ein `Protected` -Element eine-Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="4a189-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a189-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a189-112">See also</span></span>

- [<span data-ttu-id="4a189-113">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="4a189-113">Public</span></span>](public.md)
- [<span data-ttu-id="4a189-114">Gebieten</span><span class="sxs-lookup"><span data-stu-id="4a189-114">Protected</span></span>](protected.md)
- [<span data-ttu-id="4a189-115">Kollegen</span><span class="sxs-lookup"><span data-stu-id="4a189-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="4a189-116">Privat</span><span class="sxs-lookup"><span data-stu-id="4a189-116">Private</span></span>](private.md)
- [<span data-ttu-id="4a189-117">Privat geschützt</span><span class="sxs-lookup"><span data-stu-id="4a189-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="4a189-118">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a189-118">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="4a189-119">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="4a189-119">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="4a189-120">Strukturen</span><span class="sxs-lookup"><span data-stu-id="4a189-120">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="4a189-121">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="4a189-121">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
