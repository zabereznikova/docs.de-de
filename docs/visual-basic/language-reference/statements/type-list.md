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
ms.openlocfilehash: 7e22ad6e32ec13f081391e1d47a80df8b1e65063
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84412987"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="b4a5a-102">Typenliste (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4a5a-102">Type List (Visual Basic)</span></span>

<span data-ttu-id="b4a5a-103">Gibt die *Typparameter* für ein *generisches* Programmier Element an.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="b4a5a-104">Mehrere Parameter werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="b4a5a-105">Im folgenden finden Sie die Syntax für einen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-105">Following is the syntax for one type parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4a5a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4a5a-106">Syntax</span></span>

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a><span data-ttu-id="b4a5a-107">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="b4a5a-107">Parts</span></span>

|<span data-ttu-id="b4a5a-108">Begriff</span><span class="sxs-lookup"><span data-stu-id="b4a5a-108">Term</span></span>|<span data-ttu-id="b4a5a-109">Definition</span><span class="sxs-lookup"><span data-stu-id="b4a5a-109">Definition</span></span>|
|---|---|
|`genericmodifier`|<span data-ttu-id="b4a5a-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-110">Optional.</span></span> <span data-ttu-id="b4a5a-111">Kann nur in generischen Schnittstellen und Delegaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="b4a5a-112">Sie können einen typkovariant deklarieren, indem Sie das Schlüsselwort [out](../modifiers/out-generic-modifier.md) oder Kontra Variant mit dem [in](../modifiers/in-generic-modifier.md) -Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-112">You can declare a type covariant by using the [Out](../modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="b4a5a-113">Siehe [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="b4a5a-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|
|`typename`|<span data-ttu-id="b4a5a-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-114">Required.</span></span> <span data-ttu-id="b4a5a-115">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-115">Name of the type parameter.</span></span> <span data-ttu-id="b4a5a-116">Dies ist ein Platzhalter, der durch einen definierten Typ ersetzt werden soll, der durch das entsprechende Typargument bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|
|`constraintlist`|<span data-ttu-id="b4a5a-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-117">Optional.</span></span> <span data-ttu-id="b4a5a-118">Liste der Anforderungen, die den Datentyp einschränken, der für bereitgestellt werden kann `typename` .</span><span class="sxs-lookup"><span data-stu-id="b4a5a-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="b4a5a-119">Wenn Sie mehrere Einschränkungen haben, schließen Sie Sie in geschweiften Klammern ( `{ }` ) ein, und trennen Sie Sie durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="b4a5a-120">Sie müssen die Einschränkungs Liste mit dem [As](as-clause.md) -Schlüsselwort einführen.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-120">You must introduce the constraint list with the [As](as-clause.md) keyword.</span></span> <span data-ttu-id="b4a5a-121">Sie verwenden `As` nur einmal am Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-121">You use `As` only once, at the beginning of the list.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b4a5a-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b4a5a-122">Remarks</span></span>

<span data-ttu-id="b4a5a-123">Jedes generische Programmier Element muss mindestens einen Typparameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="b4a5a-124">Ein Typparameter ist ein Platzhalter für einen bestimmten Typ (ein *konstruiertes Element*), das vom Client Code beim Erstellen einer Instanz des generischen Typs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="b4a5a-125">Sie können eine generische Klasse, Struktur, Schnittstelle, Prozedur oder einen Delegaten definieren.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>

<span data-ttu-id="b4a5a-126">Weitere Informationen zum Definieren eines generischen Typs finden Sie unter [generische Typen in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="b4a5a-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="b4a5a-127">Weitere Informationen zu Typparameter Namen finden Sie unter [deklarierte Element Namen](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="b4a5a-127">For more information on type parameter names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="rules"></a><span data-ttu-id="b4a5a-128">Regeln</span><span class="sxs-lookup"><span data-stu-id="b4a5a-128">Rules</span></span>

- <span data-ttu-id="b4a5a-129">**Klammern.**</span><span class="sxs-lookup"><span data-stu-id="b4a5a-129">**Parentheses.**</span></span> <span data-ttu-id="b4a5a-130">Wenn Sie eine Typparameter Liste angeben, müssen Sie Sie in Klammern einschließen, und Sie müssen die Liste mit dem [of](of-clause.md) -Schlüsselwort einführen.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](of-clause.md) keyword.</span></span> <span data-ttu-id="b4a5a-131">Sie verwenden `Of` nur einmal am Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-131">You use `Of` only once, at the beginning of the list.</span></span>

- <span data-ttu-id="b4a5a-132">**Auflagen.**</span><span class="sxs-lookup"><span data-stu-id="b4a5a-132">**Constraints.**</span></span> <span data-ttu-id="b4a5a-133">Eine Liste der *Einschränkungen* für einen Typparameter kann die folgenden Elemente in beliebiger Kombination enthalten:</span><span class="sxs-lookup"><span data-stu-id="b4a5a-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>

  - <span data-ttu-id="b4a5a-134">Eine beliebige Anzahl von Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-134">Any number of interfaces.</span></span> <span data-ttu-id="b4a5a-135">Der angegebene Typ muss jede Schnittstelle in dieser Liste implementieren.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-135">The supplied type must implement every interface in this list.</span></span>

  - <span data-ttu-id="b4a5a-136">Höchstens eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-136">At most one class.</span></span> <span data-ttu-id="b4a5a-137">Der angegebene Typ muss von dieser Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-137">The supplied type must inherit from that class.</span></span>

  - <span data-ttu-id="b4a5a-138">Das `New`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-138">The `New` keyword.</span></span> <span data-ttu-id="b4a5a-139">Der angegebene Typ muss einen Parameter losen Konstruktor verfügbar machen, auf den der generische Typ zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="b4a5a-140">Dies ist hilfreich, wenn Sie einen Typparameter durch eine oder mehrere Schnittstellen einschränken.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="b4a5a-141">Ein Typ, der Schnittstellen implementiert, macht nicht notwendigerweise einen Konstruktor verfügbar, und abhängig von der Zugriffsebene eines Konstruktors kann der Code innerhalb des generischen Typs möglicherweise nicht darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>

  - <span data-ttu-id="b4a5a-142">Entweder das- `Class` Schlüsselwort oder das- `Structure` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="b4a5a-143">Das- `Class` Schlüsselwort Schränkt einen generischen Typparameter ein, um zu verlangen, dass jedes an es übergebenen Typargument ein Verweistyp ist, z. b. eine Zeichenfolge, ein Array oder ein Delegat oder ein Objekt, das aus einer</span><span class="sxs-lookup"><span data-stu-id="b4a5a-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="b4a5a-144">Das- `Structure` Schlüsselwort Schränkt einen generischen Typparameter ein, sodass jedes an ihn übergebenen Typargument ein Werttyp sein muss, z. b. eine Struktur, eine Enumeration oder ein grundlegender Datentyp.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="b4a5a-145">Sie können nicht `Class` `Structure` gleichzeitig und in denselben einschließen `constraintlist` .</span><span class="sxs-lookup"><span data-stu-id="b4a5a-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>

  <span data-ttu-id="b4a5a-146">Der angegebene Typ muss jede Anforderung erfüllen, die Sie in einschließen `constraintlist` .</span><span class="sxs-lookup"><span data-stu-id="b4a5a-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>

  <span data-ttu-id="b4a5a-147">Einschränkungen für die einzelnen Typparameter sind unabhängig von Einschränkungen für andere Typparameter.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>

## <a name="behavior"></a><span data-ttu-id="b4a5a-148">Verhalten</span><span class="sxs-lookup"><span data-stu-id="b4a5a-148">Behavior</span></span>

- <span data-ttu-id="b4a5a-149">**Ersetzung der Kompilierzeit.**</span><span class="sxs-lookup"><span data-stu-id="b4a5a-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="b4a5a-150">Wenn Sie einen konstruierten Typ aus einem generischen Programmier Element erstellen, geben Sie einen definierten Typ für jeden Typparameter an.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="b4a5a-151">Der Visual Basic Compiler ersetzt den angegebenen Typ für jedes Vorkommen von `typename` innerhalb des generischen Elements.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>

- <span data-ttu-id="b4a5a-152">**Fehlende Einschränkungen.**</span><span class="sxs-lookup"><span data-stu-id="b4a5a-152">**Absence of Constraints.**</span></span> <span data-ttu-id="b4a5a-153">Wenn Sie keine Einschränkungen für einen Typparameter angeben, ist der Code auf die Vorgänge und Member beschränkt, die vom [Objekt Datentyp](../data-types/object-data-type.md) für diesen Typparameter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../data-types/object-data-type.md) for that type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="b4a5a-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4a5a-154">Example</span></span>

<span data-ttu-id="b4a5a-155">Das folgende Beispiel zeigt eine Gerüst Definition einer generischen Wörterbuch Klasse, einschließlich einer Skeleton-Funktion, um dem Wörterbuch einen neuen Eintrag hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a><span data-ttu-id="b4a5a-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4a5a-156">Example</span></span>

<span data-ttu-id="b4a5a-157">Da `dictionary` generisch ist, kann der Code, der ihn verwendet, eine Vielzahl von Objekten daraus erstellen, die jeweils die gleiche Funktionalität aufweisen, aber auf einem anderen Datentyp agieren.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="b4a5a-158">Das folgende Beispiel zeigt eine Codezeile, die ein `dictionary` -Objekt mit `String` Einträgen und `Integer` Schlüsseln erstellt.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a><span data-ttu-id="b4a5a-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4a5a-159">Example</span></span>

<span data-ttu-id="b4a5a-160">Das folgende Beispiel zeigt die entsprechende Skelett Definition, die im vorherigen Beispiel generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b4a5a-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="b4a5a-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4a5a-161">See also</span></span>

- [<span data-ttu-id="b4a5a-162">Natürlich</span><span class="sxs-lookup"><span data-stu-id="b4a5a-162">Of</span></span>](of-clause.md)
- [<span data-ttu-id="b4a5a-163">New-Operator</span><span class="sxs-lookup"><span data-stu-id="b4a5a-163">New Operator</span></span>](../operators/new-operator.md)
- [<span data-ttu-id="b4a5a-164">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b4a5a-164">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="b4a5a-165">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="b4a5a-165">Object Data Type</span></span>](../data-types/object-data-type.md)
- [<span data-ttu-id="b4a5a-166">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b4a5a-166">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="b4a5a-167">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="b4a5a-167">Structure Statement</span></span>](structure-statement.md)
- [<span data-ttu-id="b4a5a-168">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b4a5a-168">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="b4a5a-169">Vorgehensweise: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="b4a5a-169">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="b4a5a-170">Kovarianz und Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="b4a5a-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="b4a5a-171">Geben Sie in</span><span class="sxs-lookup"><span data-stu-id="b4a5a-171">In</span></span>](../modifiers/in-generic-modifier.md)
- [<span data-ttu-id="b4a5a-172">Vorgenommen</span><span class="sxs-lookup"><span data-stu-id="b4a5a-172">Out</span></span>](../modifiers/out-generic-modifier.md)
