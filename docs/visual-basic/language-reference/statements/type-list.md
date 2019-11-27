---
title: Type List
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 3f2aaa65293ed2bcc6c8eeb4bd77e49907d93425
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352777"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="5efb8-102">Typenliste (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5efb8-102">Type List (Visual Basic)</span></span>

<span data-ttu-id="5efb8-103">Gibt die *Typparameter* für ein *generisches* Programmier Element an.</span><span class="sxs-lookup"><span data-stu-id="5efb8-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="5efb8-104">Mehrere Parameter werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="5efb8-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="5efb8-105">Im folgenden finden Sie die Syntax für einen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="5efb8-105">Following is the syntax for one type parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="5efb8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5efb8-106">Syntax</span></span>

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a><span data-ttu-id="5efb8-107">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="5efb8-107">Parts</span></span>

|<span data-ttu-id="5efb8-108">Begriff</span><span class="sxs-lookup"><span data-stu-id="5efb8-108">Term</span></span>|<span data-ttu-id="5efb8-109">Definition</span><span class="sxs-lookup"><span data-stu-id="5efb8-109">Definition</span></span>|
|---|---|
|`genericmodifier`|<span data-ttu-id="5efb8-110">Optional.</span><span class="sxs-lookup"><span data-stu-id="5efb8-110">Optional.</span></span> <span data-ttu-id="5efb8-111">Kann nur in generischen Schnittstellen und Delegaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5efb8-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="5efb8-112">Sie können einen typkovariant deklarieren, indem Sie das Schlüsselwort [out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) oder Kontra Variant mit dem [in](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) -Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="5efb8-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="5efb8-113">Siehe [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="5efb8-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|
|`typename`|<span data-ttu-id="5efb8-114">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="5efb8-114">Required.</span></span> <span data-ttu-id="5efb8-115">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="5efb8-115">Name of the type parameter.</span></span> <span data-ttu-id="5efb8-116">Dies ist ein Platzhalter, der durch einen definierten Typ ersetzt werden soll, der durch das entsprechende Typargument bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5efb8-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|
|`constraintlist`|<span data-ttu-id="5efb8-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="5efb8-117">Optional.</span></span> <span data-ttu-id="5efb8-118">Liste der Anforderungen, die den Datentyp einschränken, der für `typename`bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5efb8-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="5efb8-119">Wenn Sie mehrere Einschränkungen haben, schließen Sie Sie in geschweiften Klammern (`{ }`) ein, und trennen Sie Sie durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="5efb8-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="5efb8-120">Sie müssen die Einschränkungs Liste mit dem [As](../../../visual-basic/language-reference/statements/as-clause.md) -Schlüsselwort einführen.</span><span class="sxs-lookup"><span data-stu-id="5efb8-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="5efb8-121">Sie verwenden `As` nur einmal am Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="5efb8-121">You use `As` only once, at the beginning of the list.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5efb8-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5efb8-122">Remarks</span></span>

<span data-ttu-id="5efb8-123">Jedes generische Programmier Element muss mindestens einen Typparameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="5efb8-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="5efb8-124">Ein Typparameter ist ein Platzhalter für einen bestimmten Typ (ein *konstruiertes Element*), das vom Client Code beim Erstellen einer Instanz des generischen Typs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5efb8-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="5efb8-125">Sie können eine generische Klasse, Struktur, Schnittstelle, Prozedur oder einen Delegaten definieren.</span><span class="sxs-lookup"><span data-stu-id="5efb8-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>

<span data-ttu-id="5efb8-126">Weitere Informationen zum Definieren eines generischen Typs finden Sie unter [generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="5efb8-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="5efb8-127">Weitere Informationen zu Typparameter Namen finden Sie unter [deklarierte Element Namen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="5efb8-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="rules"></a><span data-ttu-id="5efb8-128">Regeln</span><span class="sxs-lookup"><span data-stu-id="5efb8-128">Rules</span></span>

- <span data-ttu-id="5efb8-129">**Klammern.**</span><span class="sxs-lookup"><span data-stu-id="5efb8-129">**Parentheses.**</span></span> <span data-ttu-id="5efb8-130">Wenn Sie eine Typparameter Liste angeben, müssen Sie Sie in Klammern einschließen, und Sie müssen die Liste mit dem [of](../../../visual-basic/language-reference/statements/of-clause.md) -Schlüsselwort einführen.</span><span class="sxs-lookup"><span data-stu-id="5efb8-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="5efb8-131">Sie verwenden `Of` nur einmal am Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="5efb8-131">You use `Of` only once, at the beginning of the list.</span></span>

- <span data-ttu-id="5efb8-132">**Auflagen.**</span><span class="sxs-lookup"><span data-stu-id="5efb8-132">**Constraints.**</span></span> <span data-ttu-id="5efb8-133">Eine Liste der *Einschränkungen* für einen Typparameter kann die folgenden Elemente in beliebiger Kombination enthalten:</span><span class="sxs-lookup"><span data-stu-id="5efb8-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>

  - <span data-ttu-id="5efb8-134">Eine beliebige Anzahl von Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="5efb8-134">Any number of interfaces.</span></span> <span data-ttu-id="5efb8-135">Der angegebene Typ muss jede Schnittstelle in dieser Liste implementieren.</span><span class="sxs-lookup"><span data-stu-id="5efb8-135">The supplied type must implement every interface in this list.</span></span>

  - <span data-ttu-id="5efb8-136">Höchstens eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="5efb8-136">At most one class.</span></span> <span data-ttu-id="5efb8-137">Der angegebene Typ muss von dieser Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="5efb8-137">The supplied type must inherit from that class.</span></span>

  - <span data-ttu-id="5efb8-138">Das `New`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="5efb8-138">The `New` keyword.</span></span> <span data-ttu-id="5efb8-139">Der angegebene Typ muss einen Parameter losen Konstruktor verfügbar machen, auf den der generische Typ zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="5efb8-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="5efb8-140">Dies ist hilfreich, wenn Sie einen Typparameter durch eine oder mehrere Schnittstellen einschränken.</span><span class="sxs-lookup"><span data-stu-id="5efb8-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="5efb8-141">Ein Typ, der Schnittstellen implementiert, macht nicht notwendigerweise einen Konstruktor verfügbar, und abhängig von der Zugriffsebene eines Konstruktors kann der Code innerhalb des generischen Typs möglicherweise nicht darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5efb8-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>

  - <span data-ttu-id="5efb8-142">Entweder das `Class`-Schlüsselwort oder das `Structure`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="5efb8-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="5efb8-143">Das `Class`-Schlüsselwort Schränkt einen generischen Typparameter ein, sodass ein beliebiges Typargument ein Verweistyp sein muss, z. b. eine Zeichenfolge, ein Array oder ein Delegat oder ein Objekt, das aus einer Klasse erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5efb8-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="5efb8-144">Das `Structure`-Schlüsselwort Schränkt einen generischen Typparameter ein, sodass jedes an ihn übergebenen Typargument ein Werttyp sein muss, z. b. eine Struktur, eine Enumeration oder ein grundlegender Datentyp.</span><span class="sxs-lookup"><span data-stu-id="5efb8-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="5efb8-145">Sie können nicht sowohl `Class` als auch `Structure` in denselben `constraintlist`einschließen.</span><span class="sxs-lookup"><span data-stu-id="5efb8-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>

  <span data-ttu-id="5efb8-146">Der angegebene Typ muss jede Anforderung erfüllen, die Sie in `constraintlist`einschließen.</span><span class="sxs-lookup"><span data-stu-id="5efb8-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>

  <span data-ttu-id="5efb8-147">Einschränkungen für die einzelnen Typparameter sind unabhängig von Einschränkungen für andere Typparameter.</span><span class="sxs-lookup"><span data-stu-id="5efb8-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>

## <a name="behavior"></a><span data-ttu-id="5efb8-148">Verhalten</span><span class="sxs-lookup"><span data-stu-id="5efb8-148">Behavior</span></span>

- <span data-ttu-id="5efb8-149">**Ersetzung der Kompilierzeit.**</span><span class="sxs-lookup"><span data-stu-id="5efb8-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="5efb8-150">Wenn Sie einen konstruierten Typ aus einem generischen Programmier Element erstellen, geben Sie einen definierten Typ für jeden Typparameter an.</span><span class="sxs-lookup"><span data-stu-id="5efb8-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="5efb8-151">Der Visual Basic Compiler ersetzt den angegebenen Typ für jedes Vorkommen von `typename` innerhalb des generischen Elements.</span><span class="sxs-lookup"><span data-stu-id="5efb8-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>

- <span data-ttu-id="5efb8-152">**Fehlende Einschränkungen.**</span><span class="sxs-lookup"><span data-stu-id="5efb8-152">**Absence of Constraints.**</span></span> <span data-ttu-id="5efb8-153">Wenn Sie keine Einschränkungen für einen Typparameter angeben, ist der Code auf die Vorgänge und Member beschränkt, die vom [Objekt Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md) für diesen Typparameter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="5efb8-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="5efb8-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5efb8-154">Example</span></span>

<span data-ttu-id="5efb8-155">Das folgende Beispiel zeigt eine Gerüst Definition einer generischen Wörterbuch Klasse, einschließlich einer Skeleton-Funktion, um dem Wörterbuch einen neuen Eintrag hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5efb8-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a><span data-ttu-id="5efb8-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5efb8-156">Example</span></span>

<span data-ttu-id="5efb8-157">Da `dictionary` generisch ist, kann der Code, der ihn verwendet, eine Vielzahl von Objekten daraus erstellen, die jeweils die gleiche Funktionalität aufweisen, aber auf einem anderen Datentyp agieren.</span><span class="sxs-lookup"><span data-stu-id="5efb8-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="5efb8-158">Das folgende Beispiel zeigt eine Codezeile, die ein `dictionary` Objekt mit `String` Einträgen und `Integer` Schlüsseln erstellt.</span><span class="sxs-lookup"><span data-stu-id="5efb8-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a><span data-ttu-id="5efb8-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5efb8-159">Example</span></span>

<span data-ttu-id="5efb8-160">Das folgende Beispiel zeigt die entsprechende Skelett Definition, die im vorherigen Beispiel generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5efb8-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="5efb8-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5efb8-161">See also</span></span>

- [<span data-ttu-id="5efb8-162">Of</span><span class="sxs-lookup"><span data-stu-id="5efb8-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)
- [<span data-ttu-id="5efb8-163">New-Operator</span><span class="sxs-lookup"><span data-stu-id="5efb8-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="5efb8-164">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5efb8-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="5efb8-165">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="5efb8-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="5efb8-166">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5efb8-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="5efb8-167">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5efb8-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="5efb8-168">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5efb8-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="5efb8-169">Gewusst wie: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="5efb8-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="5efb8-170">Kovarianz und Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="5efb8-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="5efb8-171">In</span><span class="sxs-lookup"><span data-stu-id="5efb8-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="5efb8-172">Out</span><span class="sxs-lookup"><span data-stu-id="5efb8-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
