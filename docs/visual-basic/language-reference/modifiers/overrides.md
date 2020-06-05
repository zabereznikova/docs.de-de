---
title: Überschreibt
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 657f838b2959a5b6a7cef5ff18295a4ada709e9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392027"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="69723-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69723-102">Overrides (Visual Basic)</span></span>

<span data-ttu-id="69723-103">Gibt an, dass eine Eigenschaft oder Prozedur eine Eigenschaft oder Prozedur mit dem gleichen Namen überschreibt, die von einer Basisklasse geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="69723-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="69723-104">Regeln</span><span class="sxs-lookup"><span data-stu-id="69723-104">Rules</span></span>

- <span data-ttu-id="69723-105">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="69723-105">**Declaration Context.**</span></span> <span data-ttu-id="69723-106">Sie können `Overrides` nur in einer Deklarations Anweisung für eine Eigenschaft oder Prozedur verwenden.</span><span class="sxs-lookup"><span data-stu-id="69723-106">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="69723-107">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="69723-107">**Combined Modifiers.**</span></span> <span data-ttu-id="69723-108">Sie können nicht `Overrides` mit `Shadows` oder `Shared` in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="69723-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="69723-109">Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="69723-109">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="69723-110">**Übereinstimmende Signaturen.**</span><span class="sxs-lookup"><span data-stu-id="69723-110">**Matching Signatures.**</span></span> <span data-ttu-id="69723-111">Die Signatur dieser Deklaration muss genau mit der *Signatur* der Eigenschaft oder Prozedur übereinstimmen, die Sie überschreibt.</span><span class="sxs-lookup"><span data-stu-id="69723-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="69723-112">Das bedeutet, dass die Anzahl, die Reihenfolge und die Datentypen der Parameter in den Parameterlisten gleich sein müssen.</span><span class="sxs-lookup"><span data-stu-id="69723-112">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="69723-113">Neben der Signatur müssen auch die folgenden Elemente der überschreibenden Deklaration genau übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="69723-113">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="69723-114">Die Zugriffsebene</span><span class="sxs-lookup"><span data-stu-id="69723-114">The access level</span></span>

  - <span data-ttu-id="69723-115">Der Rückgabetyp, falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="69723-115">The return type, if any</span></span>

- <span data-ttu-id="69723-116">**Generische Signaturen.**</span><span class="sxs-lookup"><span data-stu-id="69723-116">**Generic Signatures.**</span></span> <span data-ttu-id="69723-117">Bei einer generischen Prozedur umfasst die Signatur die Anzahl der Typparameter.</span><span class="sxs-lookup"><span data-stu-id="69723-117">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="69723-118">Daher muss die überschreibende Deklaration auch in dieser Hinsicht mit der Basisklassenversion übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="69723-118">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="69723-119">**Zusätzliche Übereinstimmung.**</span><span class="sxs-lookup"><span data-stu-id="69723-119">**Additional Matching.**</span></span> <span data-ttu-id="69723-120">Diese Deklaration muss nicht nur in Bezug auf die Signatur, sondern auch in folgenden Punkten mit der Basisklassenversion übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="69723-120">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="69723-121">Modifizierer auf Zugriffsebene (z. b. [Public](public.md))</span><span class="sxs-lookup"><span data-stu-id="69723-121">Access-level modifier (such as [Public](public.md))</span></span>

  - <span data-ttu-id="69723-122">Übergabe Mechanismus jedes Parameters ([ByVal](byval.md) oder [ByRef](byref.md))</span><span class="sxs-lookup"><span data-stu-id="69723-122">Passing mechanism of each parameter ([ByVal](byval.md) or [ByRef](byref.md))</span></span>

  - <span data-ttu-id="69723-123">Einschränkungslisten für jeden Typparameter einer generischen Prozedur</span><span class="sxs-lookup"><span data-stu-id="69723-123">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="69723-124">**Shadowing und Überschreiben.**</span><span class="sxs-lookup"><span data-stu-id="69723-124">**Shadowing and Overriding.**</span></span> <span data-ttu-id="69723-125">Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="69723-125">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="69723-126">Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="69723-126">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="69723-127">Beim Verwenden von `Overrides` fügt der Compiler implizit `Overloads` hinzu, sodass Ihre Bibliotheks-APIs leichter mit C# verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="69723-127">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="69723-128">Der `Overrides`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="69723-128">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="69723-129">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="69723-129">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="69723-130">Property Statement</span><span class="sxs-lookup"><span data-stu-id="69723-130">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="69723-131">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="69723-131">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="69723-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69723-132">See also</span></span>

- [<span data-ttu-id="69723-133">MustOverride</span><span class="sxs-lookup"><span data-stu-id="69723-133">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="69723-134">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="69723-134">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="69723-135">Overrides</span><span class="sxs-lookup"><span data-stu-id="69723-135">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="69723-136">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="69723-136">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="69723-137">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="69723-137">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="69723-138">Generische Typen in Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69723-138">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="69723-139">Type List</span><span class="sxs-lookup"><span data-stu-id="69723-139">Type List</span></span>](../statements/type-list.md)
