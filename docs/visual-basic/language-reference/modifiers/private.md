---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 524f03e77e075bef08a1b41b563985de41baacb6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404809"
---
# <a name="private-visual-basic"></a><span data-ttu-id="d58e6-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d58e6-102">Private (Visual Basic)</span></span>
<span data-ttu-id="d58e6-103">Gibt an, dass auf ein oder mehrere deklarierte Programmier Elemente nur innerhalb Ihres Deklarations Kontexts zugegriffen werden kann, einschließlich aus allen enthaltenen Typen.</span><span class="sxs-lookup"><span data-stu-id="d58e6-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d58e6-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d58e6-104">Remarks</span></span>  
 <span data-ttu-id="d58e6-105">Wenn ein Programmier Element proprietäre Funktionen darstellt oder vertrauliche Daten enthält, sollten Sie den Zugriff auf das Element in der Regel so streng wie möglich einschränken.</span><span class="sxs-lookup"><span data-stu-id="d58e6-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="d58e6-106">Die maximale Beschränkung erreichen Sie, indem nur das Modul, die Klasse oder die Struktur, die das Modul definiert, für den Zugriff zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="d58e6-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="d58e6-107">Um den Zugriff auf ein Element auf diese Weise einzuschränken, können Sie es mit deklarieren `Private` .</span><span class="sxs-lookup"><span data-stu-id="d58e6-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="d58e6-108">Sie können auch den [privaten geschützten](private-protected.md) Zugriffsmodifizierer verwenden, wodurch ein Member innerhalb dieser Klasse und aus abgeleiteten Klassen, die sich in der enthaltenden Assembly befinden, zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="d58e6-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="d58e6-109">Regeln</span><span class="sxs-lookup"><span data-stu-id="d58e6-109">Rules</span></span>  

- <span data-ttu-id="d58e6-110">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="d58e6-110">**Declaration Context.**</span></span> <span data-ttu-id="d58e6-111">Sie können `Private` nur auf Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="d58e6-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="d58e6-112">Dies bedeutet, dass der Deklarations Kontext für ein- `Private` Element ein Modul, eine Klasse oder eine Struktur sein muss und nicht eine Quelldatei, ein Namespace, eine Schnittstelle oder eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="d58e6-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d58e6-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="d58e6-113">Behavior</span></span>  
  
- <span data-ttu-id="d58e6-114">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="d58e6-114">**Access Level.**</span></span> <span data-ttu-id="d58e6-115">Der gesamte Code in einem Deklarations Kontext kann auf seine `Private` Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d58e6-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="d58e6-116">Dies schließt Code in einem enthaltenen Typ ein, z. b. eine geschachtelte Klasse oder einen Zuweisungs Ausdruck in einer Enumeration.</span><span class="sxs-lookup"><span data-stu-id="d58e6-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="d58e6-117">Kein Code außerhalb des Deklarations Kontexts kann auf seine `Private` Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d58e6-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="d58e6-118">**Zugriffsmodifizierer**</span><span class="sxs-lookup"><span data-stu-id="d58e6-118">**Access Modifiers.**</span></span> <span data-ttu-id="d58e6-119">Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d58e6-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="d58e6-120">Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d58e6-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="d58e6-121">Der `Private`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="d58e6-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="d58e6-122">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d58e6-122">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="d58e6-123">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d58e6-123">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="d58e6-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="d58e6-124">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="d58e6-125">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d58e6-125">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="d58e6-126">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d58e6-126">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="d58e6-127">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d58e6-127">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="d58e6-128">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d58e6-128">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="d58e6-129">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d58e6-129">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="d58e6-130">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d58e6-130">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="d58e6-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="d58e6-131">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="d58e6-132">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="d58e6-132">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="d58e6-133">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d58e6-133">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d58e6-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d58e6-134">See also</span></span>

- [<span data-ttu-id="d58e6-135">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="d58e6-135">Public</span></span>](public.md)
- [<span data-ttu-id="d58e6-136">Gebieten</span><span class="sxs-lookup"><span data-stu-id="d58e6-136">Protected</span></span>](protected.md)
- [<span data-ttu-id="d58e6-137">Kollegen</span><span class="sxs-lookup"><span data-stu-id="d58e6-137">Friend</span></span>](friend.md)
- [<span data-ttu-id="d58e6-138">Privat geschützt</span><span class="sxs-lookup"><span data-stu-id="d58e6-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="d58e6-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="d58e6-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="d58e6-140">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d58e6-140">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="d58e6-141">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="d58e6-141">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="d58e6-142">Strukturen</span><span class="sxs-lookup"><span data-stu-id="d58e6-142">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="d58e6-143">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="d58e6-143">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
