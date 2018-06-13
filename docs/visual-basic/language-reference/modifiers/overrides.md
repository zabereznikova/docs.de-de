---
title: Overrides (Visual Basic)
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
ms.openlocfilehash: 81118b9e97f320bffdbb58e5e1a2859052c4cee5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602520"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="651c7-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="651c7-102">Overrides (Visual Basic)</span></span>
<span data-ttu-id="651c7-103">Gibt an, dass eine Eigenschaft oder Prozedur eine Eigenschaft oder Prozedur mit dem gleichen Namen überschreibt, die von einer Basisklasse geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="651c7-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="651c7-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="651c7-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="651c7-105">Regeln</span><span class="sxs-lookup"><span data-stu-id="651c7-105">Rules</span></span>  
  
-   <span data-ttu-id="651c7-106">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="651c7-106">**Declaration Context.**</span></span> <span data-ttu-id="651c7-107">Sie können `Overrides` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="651c7-107">You can use `Overrides` only in a property or procedure declaration statement.</span></span>  
  
-   <span data-ttu-id="651c7-108">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="651c7-108">**Combined Modifiers.**</span></span> <span data-ttu-id="651c7-109">Sie können `Overrides` nicht zusammen mit `Shadows` oder `Shared` in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="651c7-109">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="651c7-110">Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="651c7-110">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
-   <span data-ttu-id="651c7-111">**Übereinstimmende Signaturen.**</span><span class="sxs-lookup"><span data-stu-id="651c7-111">**Matching Signatures.**</span></span> <span data-ttu-id="651c7-112">Die Signatur dieser Deklaration muss genau übereinstimmen. die *Signatur* der Eigenschaft oder Prozedur, die sie überschreibt.</span><span class="sxs-lookup"><span data-stu-id="651c7-112">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="651c7-113">Das bedeutet, dass die Anzahl, die Reihenfolge und die Datentypen der Parameter in den Parameterlisten gleich sein müssen.</span><span class="sxs-lookup"><span data-stu-id="651c7-113">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>  
  
     <span data-ttu-id="651c7-114">Neben der Signatur müssen auch die folgenden Elemente der überschreibenden Deklaration genau übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="651c7-114">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>  
  
    -   <span data-ttu-id="651c7-115">Die Zugriffsebene</span><span class="sxs-lookup"><span data-stu-id="651c7-115">The access level</span></span>  
  
    -   <span data-ttu-id="651c7-116">Der Rückgabetyp, falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="651c7-116">The return type, if any</span></span>  
  
-   <span data-ttu-id="651c7-117">**Generische Signaturen.**</span><span class="sxs-lookup"><span data-stu-id="651c7-117">**Generic Signatures.**</span></span> <span data-ttu-id="651c7-118">Bei einer generischen Prozedur umfasst die Signatur die Anzahl der Typparameter.</span><span class="sxs-lookup"><span data-stu-id="651c7-118">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="651c7-119">Daher muss die überschreibende Deklaration auch in dieser Hinsicht mit der Basisklassenversion übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="651c7-119">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>  
  
-   <span data-ttu-id="651c7-120">**Zusätzliche Übereinstimmung.**</span><span class="sxs-lookup"><span data-stu-id="651c7-120">**Additional Matching.**</span></span> <span data-ttu-id="651c7-121">Diese Deklaration muss nicht nur in Bezug auf die Signatur, sondern auch in folgenden Punkten mit der Basisklassenversion übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="651c7-121">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>  
  
    -   <span data-ttu-id="651c7-122">Zugriffsebenenmodifizierer (z. B. [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="651c7-122">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>  
  
    -   <span data-ttu-id="651c7-123">Übergabemechanismus jedes Parameters ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="651c7-123">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>  
  
    -   <span data-ttu-id="651c7-124">Einschränkungslisten für jeden Typparameter einer generischen Prozedur</span><span class="sxs-lookup"><span data-stu-id="651c7-124">Constraint lists on each type parameter of a generic procedure</span></span>  
  
-   <span data-ttu-id="651c7-125">**Shadowing und überschreiben.**</span><span class="sxs-lookup"><span data-stu-id="651c7-125">**Shadowing and Overriding.**</span></span> <span data-ttu-id="651c7-126">Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="651c7-126">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="651c7-127">Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="651c7-127">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="651c7-128">Beim Verwenden von `Overrides` fügt der Compiler implizit `Overloads` hinzu, sodass Ihre Bibliotheks-APIs leichter mit C# verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="651c7-128">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="651c7-129">Der `Overrides`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="651c7-129">The `Overrides` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="651c7-130">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="651c7-130">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="651c7-131">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="651c7-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="651c7-132">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="651c7-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="651c7-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="651c7-133">See Also</span></span>  
 [<span data-ttu-id="651c7-134">MustOverride</span><span class="sxs-lookup"><span data-stu-id="651c7-134">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="651c7-135">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="651c7-135">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [<span data-ttu-id="651c7-136">Overridable</span><span class="sxs-lookup"><span data-stu-id="651c7-136">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="651c7-137">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="651c7-137">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="651c7-138">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="651c7-138">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="651c7-139">Generische Typen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="651c7-139">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="651c7-140">Typliste</span><span class="sxs-lookup"><span data-stu-id="651c7-140">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
