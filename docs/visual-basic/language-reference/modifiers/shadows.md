---
title: Shadows (Visual Basic)
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
ms.openlocfilehash: e879819d945f3e7256edd34e87b9cae4a04c0829
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512735"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="79796-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79796-102">Shadows (Visual Basic)</span></span>
<span data-ttu-id="79796-103">Gibt an, dass ein deklariertes Programmierelement ein Element Blendet eine mit dem gleichen Namen oder einen Satz überladener Elemente in einer Basisklasse erneut deklariert.</span><span class="sxs-lookup"><span data-stu-id="79796-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79796-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79796-104">Remarks</span></span>  
 <span data-ttu-id="79796-105">Der Hauptzweck des shadowings (Dies ist auch bekannt als *Ausblenden von Namen*) besteht darin, die Definition von Klassenmembern beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="79796-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="79796-106">Die Basisklasse kann eine Änderung durchlaufen, die ein Element mit dem gleichen Namen wie eine erstellt wird, die Sie bereits definiert haben.</span><span class="sxs-lookup"><span data-stu-id="79796-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="79796-107">In diesem Fall die `Shadows` Modifizierer erzwingt, dass Verweise über die Klasse, um der Member aufgelöst werden Sie definiert, statt auf das neue Element der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="79796-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
 <span data-ttu-id="79796-108">Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="79796-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="79796-109">Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="79796-109">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="79796-110">Regeln</span><span class="sxs-lookup"><span data-stu-id="79796-110">Rules</span></span>  
  
-   <span data-ttu-id="79796-111">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="79796-111">**Declaration Context.**</span></span> <span data-ttu-id="79796-112">Sie können `Shadows` nur auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="79796-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="79796-113">Dies bedeutet, dass der Deklarationskontext für eine `Shadows` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="79796-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
     <span data-ttu-id="79796-114">Sie können nur ein shadowing-Element in einer einzigen deklarationsanweisung deklarieren.</span><span class="sxs-lookup"><span data-stu-id="79796-114">You can declare only one shadowing element in a single declaration statement.</span></span>  
  
-   <span data-ttu-id="79796-115">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="79796-115">**Combined Modifiers.**</span></span> <span data-ttu-id="79796-116">Sie können keine angeben `Shadows` zusammen mit `Overloads`, `Overrides`, oder `Static` in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="79796-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>  
  
-   <span data-ttu-id="79796-117">**Elementtypen.**</span><span class="sxs-lookup"><span data-stu-id="79796-117">**Element Types.**</span></span> <span data-ttu-id="79796-118">Sie können ein Shadowing von jedem deklarierten Element mit einer anderen Art vornehmen.</span><span class="sxs-lookup"><span data-stu-id="79796-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="79796-119">Wenn Sie Shadowing für eine Eigenschaft oder Prozedur mit einer anderen Eigenschaft oder Prozedur, müssen die Parameter sowie des Rückgabetyps nicht mit denen in der Basisklasse-Eigenschaft oder Prozedur übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="79796-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>  
  
-   <span data-ttu-id="79796-120">**Zugriff auf.**</span><span class="sxs-lookup"><span data-stu-id="79796-120">**Accessing.**</span></span> <span data-ttu-id="79796-121">Das Shadowing-Element in der Basisklasse ist normalerweise nicht verfügbar, in der abgeleiteten Klasse, die es Shadowing durchführt.</span><span class="sxs-lookup"><span data-stu-id="79796-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="79796-122">Allerdings gelten die folgenden Überlegungen.</span><span class="sxs-lookup"><span data-stu-id="79796-122">However, the following considerations apply.</span></span>  
  
    -   <span data-ttu-id="79796-123">Ist das shadowing-Element nicht zugegriffen werden kann, aus dem Code, der darauf verweist, wird der Verweis auf das Shadowing-Element aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="79796-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="79796-124">Z. B. wenn ein `Private` Element führt Shadowing für eine Basisklasse-Element, Code, der keine Berechtigung zum Zugriff auf die `Private` Element greift stattdessen auf das Basisklasse-Element.</span><span class="sxs-lookup"><span data-stu-id="79796-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>  
  
    -   <span data-ttu-id="79796-125">Wenn Sie ein Element spiegeln, können Sie weiterhin das Shadowing-Element durch ein Objekt mit dem Typ der Basisklasse deklariert zugreifen.</span><span class="sxs-lookup"><span data-stu-id="79796-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="79796-126">Sie können auch über zugreifen `MyBase`.</span><span class="sxs-lookup"><span data-stu-id="79796-126">You can also access it through `MyBase`.</span></span>  
  
 <span data-ttu-id="79796-127">Der `Shadows`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="79796-127">The `Shadows` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="79796-128">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="79796-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="79796-129">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="79796-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="79796-130">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="79796-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="79796-131">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="79796-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="79796-132">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="79796-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="79796-133">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="79796-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="79796-134">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="79796-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="79796-135">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="79796-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="79796-136">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="79796-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="79796-137">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="79796-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="79796-138">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="79796-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="79796-139">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="79796-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="79796-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79796-140">See also</span></span>
- [<span data-ttu-id="79796-141">Shared</span><span class="sxs-lookup"><span data-stu-id="79796-141">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="79796-142">Static</span><span class="sxs-lookup"><span data-stu-id="79796-142">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="79796-143">Private</span><span class="sxs-lookup"><span data-stu-id="79796-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="79796-144">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="79796-144">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="79796-145">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="79796-145">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="79796-146">MustOverride</span><span class="sxs-lookup"><span data-stu-id="79796-146">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="79796-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="79796-147">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="79796-148">Overloads</span><span class="sxs-lookup"><span data-stu-id="79796-148">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="79796-149">Overridable</span><span class="sxs-lookup"><span data-stu-id="79796-149">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="79796-150">Overrides</span><span class="sxs-lookup"><span data-stu-id="79796-150">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="79796-151">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79796-151">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
