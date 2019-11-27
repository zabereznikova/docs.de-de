---
title: Außerkraftsetzungen
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
ms.openlocfilehash: 04f1cb27d6a8366c2dd13f8fdc1d975d382f1cfd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351388"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="63b21-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63b21-102">Overrides (Visual Basic)</span></span>

<span data-ttu-id="63b21-103">Gibt an, dass eine Eigenschaft oder Prozedur eine Eigenschaft oder Prozedur mit dem gleichen Namen überschreibt, die von einer Basisklasse geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="63b21-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="63b21-104">Regeln</span><span class="sxs-lookup"><span data-stu-id="63b21-104">Rules</span></span>

- <span data-ttu-id="63b21-105">**Deklarations Kontext.**</span><span class="sxs-lookup"><span data-stu-id="63b21-105">**Declaration Context.**</span></span> <span data-ttu-id="63b21-106">Sie können `Overrides` nur in einer Eigenschaft oder Prozedur Deklarations Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="63b21-106">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="63b21-107">**Kombinierte modifiziererer.**</span><span class="sxs-lookup"><span data-stu-id="63b21-107">**Combined Modifiers.**</span></span> <span data-ttu-id="63b21-108">Sie können `Overrides` nicht mit `Shadows` oder `Shared` in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="63b21-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="63b21-109">Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="63b21-109">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="63b21-110">**Übereinstimmende Signaturen.**</span><span class="sxs-lookup"><span data-stu-id="63b21-110">**Matching Signatures.**</span></span> <span data-ttu-id="63b21-111">Die Signatur dieser Deklaration muss genau mit der *Signatur* der Eigenschaft oder Prozedur übereinstimmen, die Sie überschreibt.</span><span class="sxs-lookup"><span data-stu-id="63b21-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="63b21-112">Das bedeutet, dass die Anzahl, die Reihenfolge und die Datentypen der Parameter in den Parameterlisten gleich sein müssen.</span><span class="sxs-lookup"><span data-stu-id="63b21-112">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="63b21-113">Neben der Signatur müssen auch die folgenden Elemente der überschreibenden Deklaration genau übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="63b21-113">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="63b21-114">Die Zugriffsebene</span><span class="sxs-lookup"><span data-stu-id="63b21-114">The access level</span></span>

  - <span data-ttu-id="63b21-115">Der Rückgabetyp, falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="63b21-115">The return type, if any</span></span>

- <span data-ttu-id="63b21-116">**Generische Signaturen.**</span><span class="sxs-lookup"><span data-stu-id="63b21-116">**Generic Signatures.**</span></span> <span data-ttu-id="63b21-117">Bei einer generischen Prozedur umfasst die Signatur die Anzahl der Typparameter.</span><span class="sxs-lookup"><span data-stu-id="63b21-117">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="63b21-118">Daher muss die überschreibende Deklaration auch in dieser Hinsicht mit der Basisklassenversion übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="63b21-118">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="63b21-119">**Weitere Übereinstimmungen.**</span><span class="sxs-lookup"><span data-stu-id="63b21-119">**Additional Matching.**</span></span> <span data-ttu-id="63b21-120">Diese Deklaration muss nicht nur in Bezug auf die Signatur, sondern auch in folgenden Punkten mit der Basisklassenversion übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="63b21-120">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="63b21-121">Modifizierer auf Zugriffsebene (z. b. [Public](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="63b21-121">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>

  - <span data-ttu-id="63b21-122">Übergabe Mechanismus jedes Parameters ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="63b21-122">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>

  - <span data-ttu-id="63b21-123">Einschränkungslisten für jeden Typparameter einer generischen Prozedur</span><span class="sxs-lookup"><span data-stu-id="63b21-123">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="63b21-124">**Shadogerichteten und überschreiben.**</span><span class="sxs-lookup"><span data-stu-id="63b21-124">**Shadowing and Overriding.**</span></span> <span data-ttu-id="63b21-125">Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="63b21-125">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="63b21-126">Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="63b21-126">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="63b21-127">Beim Verwenden von `Overrides` fügt der Compiler implizit `Overloads` hinzu, sodass Ihre Bibliotheks-APIs leichter mit C# verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="63b21-127">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="63b21-128">Der `Overrides`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="63b21-128">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="63b21-129">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="63b21-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="63b21-130">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="63b21-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="63b21-131">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="63b21-131">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="63b21-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63b21-132">See also</span></span>

- [<span data-ttu-id="63b21-133">MustOverride</span><span class="sxs-lookup"><span data-stu-id="63b21-133">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="63b21-134">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="63b21-134">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="63b21-135">Overrides</span><span class="sxs-lookup"><span data-stu-id="63b21-135">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="63b21-136">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="63b21-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="63b21-137">Shadodown in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63b21-137">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="63b21-138">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63b21-138">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="63b21-139">Typliste</span><span class="sxs-lookup"><span data-stu-id="63b21-139">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
