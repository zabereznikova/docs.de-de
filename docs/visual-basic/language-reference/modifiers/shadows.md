---
title: Shadows
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: e9a423fa69ad1dcd8c1d4a5b7085e5b5da548f93
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351264"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="2691f-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2691f-102">Shadows (Visual Basic)</span></span>

<span data-ttu-id="2691f-103">Gibt an, dass ein deklariertes Programmier Element ein identisch benanntes Element oder einen Satz überladener Elemente in einer Basisklasse erneut deklariert und verbirgt.</span><span class="sxs-lookup"><span data-stu-id="2691f-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>

## <a name="remarks"></a><span data-ttu-id="2691f-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2691f-104">Remarks</span></span>

<span data-ttu-id="2691f-105">Der Hauptzweck von Shadowing(das auch als ausblenden *nach Name*bezeichnet wird) besteht darin, die Definition der Klassenmember beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="2691f-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="2691f-106">Die Basisklasse kann einer Änderung unterzogen werden, die ein Element mit dem gleichen Namen erstellt, den Sie bereits definiert haben.</span><span class="sxs-lookup"><span data-stu-id="2691f-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="2691f-107">In diesem Fall erzwingt der `Shadows` Modifizierer, dass Verweise durch Ihre Klasse in den von Ihnen definierten Member aufgelöst werden, anstatt das neue Basisklassen Element zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2691f-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>

<span data-ttu-id="2691f-108">Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="2691f-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="2691f-109">Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="2691f-109">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>

## <a name="rules"></a><span data-ttu-id="2691f-110">Regeln</span><span class="sxs-lookup"><span data-stu-id="2691f-110">Rules</span></span>

- <span data-ttu-id="2691f-111">**Deklarations Kontext.**</span><span class="sxs-lookup"><span data-stu-id="2691f-111">**Declaration Context.**</span></span> <span data-ttu-id="2691f-112">Sie können `Shadows` nur auf Klassenebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="2691f-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="2691f-113">Dies bedeutet, dass der Deklarations Kontext für ein `Shadows` Element eine Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="2691f-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

  <span data-ttu-id="2691f-114">Sie können nur ein Shadowingelement in einer einzelnen Deklarations Anweisung deklarieren.</span><span class="sxs-lookup"><span data-stu-id="2691f-114">You can declare only one shadowing element in a single declaration statement.</span></span>

- <span data-ttu-id="2691f-115">**Kombinierte modifiziererer.**</span><span class="sxs-lookup"><span data-stu-id="2691f-115">**Combined Modifiers.**</span></span> <span data-ttu-id="2691f-116">Sie können `Shadows` nicht mit `Overloads`, `Overrides`oder `Static` in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="2691f-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>

- <span data-ttu-id="2691f-117">**Element Typen.**</span><span class="sxs-lookup"><span data-stu-id="2691f-117">**Element Types.**</span></span> <span data-ttu-id="2691f-118">Sie können ein Shadowing von jedem deklarierten Element mit einer anderen Art vornehmen.</span><span class="sxs-lookup"><span data-stu-id="2691f-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="2691f-119">Wenn Sie eine Eigenschaft oder Prozedur mit einer anderen Eigenschaft oder Prozedur überschatten, müssen die Parameter und der Rückgabetyp nicht mit denen in der Basisklassen Eigenschaft oder-Prozedur identisch sein.</span><span class="sxs-lookup"><span data-stu-id="2691f-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>

- <span data-ttu-id="2691f-120">**Den.**</span><span class="sxs-lookup"><span data-stu-id="2691f-120">**Accessing.**</span></span> <span data-ttu-id="2691f-121">Das Shadowing-Element in der Basisklasse ist normalerweise nicht in der abgeleiteten Klasse verfügbar, die es Shadowing durchführt.</span><span class="sxs-lookup"><span data-stu-id="2691f-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="2691f-122">Es gelten jedoch die folgenden Überlegungen.</span><span class="sxs-lookup"><span data-stu-id="2691f-122">However, the following considerations apply.</span></span>

  - <span data-ttu-id="2691f-123">Wenn auf das Shadowing-Element nicht über den Code zugegriffen werden kann, auf das verwiesen wird, wird der Verweis in das Shadowing-Element aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="2691f-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="2691f-124">Wenn z. b. ein `Private` Element ein Basisklassen Element Shadowing, greift Code, der nicht über die Berechtigung für den Zugriff auf das `Private` Element verfügt, stattdessen auf das Basisklassen Element zu.</span><span class="sxs-lookup"><span data-stu-id="2691f-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>

  - <span data-ttu-id="2691f-125">Wenn Sie einen Schatten für ein Element durchlaufen, können Sie weiterhin auf das Shadowing Element über ein Objekt zugreifen, das mit dem Typ der Basisklasse deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="2691f-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="2691f-126">Sie können auch über `MyBase`darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2691f-126">You can also access it through `MyBase`.</span></span>

<span data-ttu-id="2691f-127">Der `Shadows`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="2691f-127">The `Shadows` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="2691f-128">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2691f-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)

- [<span data-ttu-id="2691f-129">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2691f-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="2691f-130">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2691f-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- [<span data-ttu-id="2691f-131">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2691f-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [<span data-ttu-id="2691f-132">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2691f-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- [<span data-ttu-id="2691f-133">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2691f-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)

- [<span data-ttu-id="2691f-134">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2691f-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="2691f-135">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2691f-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="2691f-136">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2691f-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)

- [<span data-ttu-id="2691f-137">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2691f-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="2691f-138">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2691f-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

- [<span data-ttu-id="2691f-139">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2691f-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="2691f-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2691f-140">See also</span></span>

- [<span data-ttu-id="2691f-141">Shared</span><span class="sxs-lookup"><span data-stu-id="2691f-141">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="2691f-142">Static</span><span class="sxs-lookup"><span data-stu-id="2691f-142">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="2691f-143">Private</span><span class="sxs-lookup"><span data-stu-id="2691f-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="2691f-144">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="2691f-144">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="2691f-145">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="2691f-145">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="2691f-146">MustOverride</span><span class="sxs-lookup"><span data-stu-id="2691f-146">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="2691f-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="2691f-147">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="2691f-148">Overloads</span><span class="sxs-lookup"><span data-stu-id="2691f-148">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="2691f-149">Overrides</span><span class="sxs-lookup"><span data-stu-id="2691f-149">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="2691f-150">Overrides</span><span class="sxs-lookup"><span data-stu-id="2691f-150">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="2691f-151">Shadodown in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2691f-151">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
