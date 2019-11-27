---
title: Overloads
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: 44823b409cfa81dc889aabacf101fac90bf851e0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351407"
---
# <a name="overloads-visual-basic"></a><span data-ttu-id="3c31a-102">Overloads (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c31a-102">Overloads (Visual Basic)</span></span>

<span data-ttu-id="3c31a-103">Gibt an, dass eine Eigenschaft oder Prozedur eine Eigenschaft oder Prozedur bzw. mehrere mit dem gleichen Namen neu deklariert.</span><span class="sxs-lookup"><span data-stu-id="3c31a-103">Specifies that a property or procedure redeclares one or more existing properties or procedures with the same name.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c31a-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c31a-104">Remarks</span></span>

<span data-ttu-id="3c31a-105">Bei der *Überladung* wird die Bereitstellung von mehr als einer Definition für eine bestimmte Eigenschaft oder einen bestimmten Prozedur Namen im selben Bereich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3c31a-105">*Overloading* is the practice of supplying more than one definition for a given property or procedure name in the same scope.</span></span> <span data-ttu-id="3c31a-106">Das erneute Deklarieren einer Eigenschaft oder Prozedur mit einer anderen Signatur wird manchmal als ausblenden *nach Signatur*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3c31a-106">Redeclaring a property or procedure with a different signature is sometimes called *hiding by signature*.</span></span>

## <a name="rules"></a><span data-ttu-id="3c31a-107">Regeln</span><span class="sxs-lookup"><span data-stu-id="3c31a-107">Rules</span></span>

- <span data-ttu-id="3c31a-108">**Deklarations Kontext.**</span><span class="sxs-lookup"><span data-stu-id="3c31a-108">**Declaration Context.**</span></span> <span data-ttu-id="3c31a-109">Sie können `Overloads` nur in einer Eigenschaft oder Prozedur Deklarations Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c31a-109">You can use `Overloads` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="3c31a-110">**Kombinierte modifiziererer.**</span><span class="sxs-lookup"><span data-stu-id="3c31a-110">**Combined Modifiers.**</span></span> <span data-ttu-id="3c31a-111">Sie können `Overloads` [nicht mit](../../../visual-basic/language-reference/modifiers/shadows.md) Shadowing in derselben Prozedur Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="3c31a-111">You cannot specify `Overloads` together with [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) in the same procedure declaration.</span></span>

- <span data-ttu-id="3c31a-112">**Erforderliche Unterschiede.**</span><span class="sxs-lookup"><span data-stu-id="3c31a-112">**Required Differences.**</span></span> <span data-ttu-id="3c31a-113">Die *Signatur* in dieser Deklaration muss sich von der Signatur jeder Eigenschaft oder Prozedur unterscheiden, die Sie über lädt.</span><span class="sxs-lookup"><span data-stu-id="3c31a-113">The *signature* in this declaration must be different from the signature of every property or procedure that it overloads.</span></span> <span data-ttu-id="3c31a-114">Die Signatur besteht aus der Eigenschaft oder dem Prozedurnamen und dem Folgenden:</span><span class="sxs-lookup"><span data-stu-id="3c31a-114">The signature comprises the property or procedure name together with the following:</span></span>

  - <span data-ttu-id="3c31a-115">der Anzahl der Parameter</span><span class="sxs-lookup"><span data-stu-id="3c31a-115">the number of parameters</span></span>

  - <span data-ttu-id="3c31a-116">Der Reihenfolge der Parameter</span><span class="sxs-lookup"><span data-stu-id="3c31a-116">the order of the parameters</span></span>

  - <span data-ttu-id="3c31a-117">der Datentypen der Parameter</span><span class="sxs-lookup"><span data-stu-id="3c31a-117">the data types of the parameters</span></span>

  - <span data-ttu-id="3c31a-118">der Anzahl der Typparameter (für eine generische Prozedur)</span><span class="sxs-lookup"><span data-stu-id="3c31a-118">the number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="3c31a-119">der Rückgabetyp (nur für eine Konvertierungsoperatorprozedur)</span><span class="sxs-lookup"><span data-stu-id="3c31a-119">the return type (only for a conversion operator procedure)</span></span>

  <span data-ttu-id="3c31a-120">Alle Überladungen müssen denselben Namen aufweisen. Jede muss sich jedoch von allen anderen in mindestens einem der vorstehenden Punkte unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="3c31a-120">All overloads must have the same name, but each must differ from all the others in one or more of the preceding respects.</span></span> <span data-ttu-id="3c31a-121">Dadurch kann der Compiler unterscheiden, welche Version verwendet werden muss, wenn der Code die Eigenschaft oder Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="3c31a-121">This allows the compiler to distinguish which version to use when code calls the property or procedure.</span></span>

- <span data-ttu-id="3c31a-122">**Unzulässige Unterschiede.**</span><span class="sxs-lookup"><span data-stu-id="3c31a-122">**Disallowed Differences.**</span></span> <span data-ttu-id="3c31a-123">Das Ändern von mindestens einem der folgenden Punkte ist für das Überladen einer Eigenschaft oder Prozedur nicht gültig, da sie kein Bestandteil der Signatur sind:</span><span class="sxs-lookup"><span data-stu-id="3c31a-123">Changing one or more of the following is not valid for overloading a property or procedure, because they are not part of the signature:</span></span>

  - <span data-ttu-id="3c31a-124">ob ein Wert (für eine Prozedur) zurückgegeben wird</span><span class="sxs-lookup"><span data-stu-id="3c31a-124">whether or not it returns a value (for a procedure)</span></span>

  - <span data-ttu-id="3c31a-125">der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungsoperators)</span><span class="sxs-lookup"><span data-stu-id="3c31a-125">the data type of the return value (except for a conversion operator)</span></span>

  - <span data-ttu-id="3c31a-126">die Namen der Parameter oder Typparameter</span><span class="sxs-lookup"><span data-stu-id="3c31a-126">the names of the parameters or type parameters</span></span>

  - <span data-ttu-id="3c31a-127">die Einschränkungen hinsichtlich der Typparameter (für eine generische Prozedur)</span><span class="sxs-lookup"><span data-stu-id="3c31a-127">the constraints on the type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="3c31a-128">Parametermodifiziererschlüsselwörter (wie `ByRef` oder `Optional`)</span><span class="sxs-lookup"><span data-stu-id="3c31a-128">parameter modifier keywords (such as `ByRef` or `Optional`)</span></span>

  - <span data-ttu-id="3c31a-129">Eigenschaft oder Prozedurmodifiziererschlüsselwörter (wie `Public` oder `Shared`)</span><span class="sxs-lookup"><span data-stu-id="3c31a-129">property or procedure modifier keywords (such as `Public` or `Shared`)</span></span>

- <span data-ttu-id="3c31a-130">**Optionaler Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="3c31a-130">**Optional Modifier.**</span></span> <span data-ttu-id="3c31a-131">Sie müssen den `Overloads` Modifizierer nicht verwenden, wenn Sie mehrere überladene Eigenschaften oder Prozeduren in derselben Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="3c31a-131">You do not have to use the `Overloads` modifier when you are defining multiple overloaded properties or procedures in the same class.</span></span> <span data-ttu-id="3c31a-132">Wenn Sie jedoch `Overloads` in einer der Deklarationen verwenden, müssen Sie sie in allen davon verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c31a-132">However, if you use `Overloads` in one of the declarations, you must use it in all of them.</span></span>

- <span data-ttu-id="3c31a-133">**Shadoading und überladen.**</span><span class="sxs-lookup"><span data-stu-id="3c31a-133">**Shadowing and Overloading.**</span></span> <span data-ttu-id="3c31a-134">`Overloads` können auch verwendet werden, um ein vorhandenes Element oder einen Satz überladener Member in einer Basisklasse zu überschatten.</span><span class="sxs-lookup"><span data-stu-id="3c31a-134">`Overloads` can also be used to shadow an existing member, or set of overloaded members, in a base class.</span></span> <span data-ttu-id="3c31a-135">Wenn Sie `Overloads` auf diese Art und Weise verwenden, deklarieren Sie die Eigenschaft oder Methode mit demselben Namen und derselben Parameterliste als Basisklassenmember, und Sie stellen das `Shadows`-Schlüsselwort nicht bereit.</span><span class="sxs-lookup"><span data-stu-id="3c31a-135">When you use `Overloads` in this way, you declare the property or method with the same name and the same parameter list as the base class member, and you do not supply the `Shadows` keyword.</span></span>

<span data-ttu-id="3c31a-136">Beim Verwenden von `Overrides` fügt der Compiler implizit `Overloads` hinzu, sodass Ihre Bibliotheks-APIs leichter mit C# verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3c31a-136">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="3c31a-137">Der `Overloads`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3c31a-137">The `Overloads` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="3c31a-138">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3c31a-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="3c31a-139">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="3c31a-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)

- [<span data-ttu-id="3c31a-140">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3c31a-140">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="3c31a-141">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3c31a-141">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="3c31a-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c31a-142">See also</span></span>

- [<span data-ttu-id="3c31a-143">Shadows</span><span class="sxs-lookup"><span data-stu-id="3c31a-143">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="3c31a-144">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="3c31a-144">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="3c31a-145">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c31a-145">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="3c31a-146">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="3c31a-146">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="3c31a-147">Gewusst wie: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="3c31a-147">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
