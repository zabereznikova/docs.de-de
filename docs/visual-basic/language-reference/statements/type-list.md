---
title: Typenliste (Visual Basic)
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
ms.openlocfilehash: d071e59d94e51ca55167983d0ee3098bd5c7dd8f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843629"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="c54a3-102">Typenliste (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c54a3-102">Type List (Visual Basic)</span></span>
<span data-ttu-id="c54a3-103">Gibt an, die *Typparameter* für eine *generische* Programmierelement.</span><span class="sxs-lookup"><span data-stu-id="c54a3-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="c54a3-104">Mehrere Parameter werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="c54a3-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="c54a3-105">Es folgt die Syntax für einen Typ-Parameter.</span><span class="sxs-lookup"><span data-stu-id="c54a3-105">Following is the syntax for one type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c54a3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c54a3-106">Syntax</span></span>  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="c54a3-107">Teile</span><span class="sxs-lookup"><span data-stu-id="c54a3-107">Parts</span></span>  
  
|<span data-ttu-id="c54a3-108">Begriff</span><span class="sxs-lookup"><span data-stu-id="c54a3-108">Term</span></span>|<span data-ttu-id="c54a3-109">Definition</span><span class="sxs-lookup"><span data-stu-id="c54a3-109">Definition</span></span>|  
|---|---|  
|`genericmodifier`|<span data-ttu-id="c54a3-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c54a3-110">Optional.</span></span> <span data-ttu-id="c54a3-111">Kann nur in generischen Schnittstellen und Delegaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c54a3-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="c54a3-112">Sie können einen Typ als Kovariante deklarieren, mit der [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) -Schlüsselwort oder kontravariant mithilfe der [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c54a3-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="c54a3-113">Siehe [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="c54a3-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|  
|`typename`|<span data-ttu-id="c54a3-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c54a3-114">Required.</span></span> <span data-ttu-id="c54a3-115">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="c54a3-115">Name of the type parameter.</span></span> <span data-ttu-id="c54a3-116">Dies ist ein Platzhalter, durch das entsprechende Typargument vom definierten Typ ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="c54a3-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|  
|`constraintlist`|<span data-ttu-id="c54a3-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c54a3-117">Optional.</span></span> <span data-ttu-id="c54a3-118">Liste der Anforderungen, die den Datentyp, der für angegeben werden können, einschränken `typename`.</span><span class="sxs-lookup"><span data-stu-id="c54a3-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="c54a3-119">Wenn Sie mehrere Einschränkungen verfügen, schließen Sie sie in geschweifte Klammern (`{ }`), und trennen Sie diese durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="c54a3-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="c54a3-120">Führen Sie die Einschränkungsliste mit dem [als](../../../visual-basic/language-reference/statements/as-clause.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c54a3-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="c54a3-121">Verwenden Sie `As` nur einmal am Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="c54a3-121">You use `As` only once, at the beginning of the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c54a3-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c54a3-122">Remarks</span></span>  
 <span data-ttu-id="c54a3-123">Jedes generische Programmierelement muss mindestens einen Typparameter ausführen.</span><span class="sxs-lookup"><span data-stu-id="c54a3-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="c54a3-124">Ein Typparameter ist ein Platzhalter für einen bestimmten Typ (ein *konstruierte Element*), dass Clientcode gibt an, wenn sie eine Instanz des generischen Typs erstellt.</span><span class="sxs-lookup"><span data-stu-id="c54a3-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="c54a3-125">Definieren Sie eine generische Klasse kann, Struktur, Schnittstelle, Prozedur oder delegieren.</span><span class="sxs-lookup"><span data-stu-id="c54a3-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>  
  
 <span data-ttu-id="c54a3-126">Weitere Informationen dazu, wann Sie einen generischen Typ definieren, finden Sie unter [generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="c54a3-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="c54a3-127">Weitere Informationen zu Typparameternamen, finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="c54a3-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c54a3-128">Regeln</span><span class="sxs-lookup"><span data-stu-id="c54a3-128">Rules</span></span>  
  
-   <span data-ttu-id="c54a3-129">**Klammern.**</span><span class="sxs-lookup"><span data-stu-id="c54a3-129">**Parentheses.**</span></span> <span data-ttu-id="c54a3-130">Wenn Sie eine Liste der Parameter angeben, Sie es in Klammern einschließen müssen und führen Sie die Liste mit den [von](../../../visual-basic/language-reference/statements/of-clause.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c54a3-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="c54a3-131">Verwenden Sie `Of` nur einmal am Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="c54a3-131">You use `Of` only once, at the beginning of the list.</span></span>  
  
-   <span data-ttu-id="c54a3-132">**Einschränkungen.**</span><span class="sxs-lookup"><span data-stu-id="c54a3-132">**Constraints.**</span></span> <span data-ttu-id="c54a3-133">Eine Liste der *Einschränkungen* für einen Parameter die folgenden Elemente in beliebiger Kombination enthalten kann:</span><span class="sxs-lookup"><span data-stu-id="c54a3-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>  
  
    -   <span data-ttu-id="c54a3-134">Eine beliebige Anzahl von Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="c54a3-134">Any number of interfaces.</span></span> <span data-ttu-id="c54a3-135">Der angegebene Typ muss jeder Schnittstelle in der Liste implementieren.</span><span class="sxs-lookup"><span data-stu-id="c54a3-135">The supplied type must implement every interface in this list.</span></span>  
  
    -   <span data-ttu-id="c54a3-136">Höchstens eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="c54a3-136">At most one class.</span></span> <span data-ttu-id="c54a3-137">Der angegebene Typ muss von dieser Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="c54a3-137">The supplied type must inherit from that class.</span></span>  
  
    -   <span data-ttu-id="c54a3-138">Das `New`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c54a3-138">The `New` keyword.</span></span> <span data-ttu-id="c54a3-139">Der angegebene Typ muss einen parameterlosen Konstruktor verfügbar machen, den der generische Typ zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c54a3-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="c54a3-140">Dies ist hilfreich, wenn Sie einen Typparameter durch eine oder mehrere Schnittstellen einschränken.</span><span class="sxs-lookup"><span data-stu-id="c54a3-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="c54a3-141">Ein Typ, der Schnittstellen implementiert ist nicht unbedingt einen Konstruktor verfügbar machen, und abhängig von die Zugriffsebene eines Konstruktors, der Code in den generischen Typ möglicherweise nicht darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c54a3-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>  
  
    -   <span data-ttu-id="c54a3-142">Entweder die `Class` Schlüsselwort oder `Structure` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c54a3-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="c54a3-143">Die `Class` -Schlüsselwort schränkt einen generischen Typparameter erforderlich ist, dass jedes Typargument übergeben, einen Verweistyp handelt, z. B. eine Zeichenfolge, Array oder Delegaten werden oder ein Objekt aus einer Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="c54a3-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="c54a3-144">Die `Structure` Schlüsselwort schränkt einen generischen Parameter anfordern, dass alle an sie übergebene Typargument ein Werttyp, ist beispielsweise eine Struktur, Enumeration oder elementarer Datentyp.</span><span class="sxs-lookup"><span data-stu-id="c54a3-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="c54a3-145">Dürfen nicht zusammen `Class` und `Structure` in der gleichen `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="c54a3-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>  
  
     <span data-ttu-id="c54a3-146">Der angegebene Typ muss jeder Anforderung, die Sie in einschließen genügen `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="c54a3-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>  
  
     <span data-ttu-id="c54a3-147">Einschränkungen für jeden Typparameter sind unabhängig von Einschränkungen für andere Type-Parameter.</span><span class="sxs-lookup"><span data-stu-id="c54a3-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="c54a3-148">Verhalten</span><span class="sxs-lookup"><span data-stu-id="c54a3-148">Behavior</span></span>  
  
-   <span data-ttu-id="c54a3-149">**Während der Kompilierung Ersetzung.**</span><span class="sxs-lookup"><span data-stu-id="c54a3-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="c54a3-150">Wenn Sie einen konstruierten Typ aus einer generischen Programmierelements erstellen, geben Sie keinen definierten Typ für jeden Typparameter an.</span><span class="sxs-lookup"><span data-stu-id="c54a3-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="c54a3-151">Visual Basic-Compiler ersetzt diesen angegebenen Typ für jedes Vorkommen des `typename` innerhalb des generischen Elements.</span><span class="sxs-lookup"><span data-stu-id="c54a3-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>  
  
-   <span data-ttu-id="c54a3-152">**Die Abwesenheit von Einschränkungen.**</span><span class="sxs-lookup"><span data-stu-id="c54a3-152">**Absence of Constraints.**</span></span> <span data-ttu-id="c54a3-153">Wenn Sie keine Einschränkungen für einen Typparameter angeben, ist Ihr Code die Operationen und Member, die von unterstützt werden auf die [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) für den Typparameter.</span><span class="sxs-lookup"><span data-stu-id="c54a3-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c54a3-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c54a3-154">Example</span></span>  
 <span data-ttu-id="c54a3-155">Im folgenden Beispiel wird die rumpfdefinition einer generischen Wörterbuch-Klasse, einschließlich eine Skelette-Funktion um einen neuen Eintrag zum Wörterbuch hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c54a3-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>  
  
 [!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="c54a3-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c54a3-156">Example</span></span>  
 <span data-ttu-id="c54a3-157">Da `dictionary` ist generisch ist, der Code, der verwendet wird kann eine Vielzahl von Objekten aus erstellen, jeweils die gleiche Funktionalität müssen jedoch, die auf einen anderen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="c54a3-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="c54a3-158">Das folgende Beispiel zeigt eine einzige Zeile Code, der erstellt eine `dictionary` Objekt mit `String` Einträge und `Integer` Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="c54a3-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>  
  
 [!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="c54a3-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c54a3-159">Example</span></span>  
 <span data-ttu-id="c54a3-160">Das folgende Beispiel zeigt die entsprechende rumpfdefinition, die im vorherigen Beispiel generiert.</span><span class="sxs-lookup"><span data-stu-id="c54a3-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="c54a3-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c54a3-161">See also</span></span>

- [<span data-ttu-id="c54a3-162">Of</span><span class="sxs-lookup"><span data-stu-id="c54a3-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)
- [<span data-ttu-id="c54a3-163">New-Operator</span><span class="sxs-lookup"><span data-stu-id="c54a3-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="c54a3-164">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c54a3-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="c54a3-165">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c54a3-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="c54a3-166">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c54a3-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="c54a3-167">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c54a3-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="c54a3-168">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c54a3-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="c54a3-169">Vorgehensweise: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="c54a3-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="c54a3-170">Kovarianz und Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="c54a3-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="c54a3-171">In</span><span class="sxs-lookup"><span data-stu-id="c54a3-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="c54a3-172">Out</span><span class="sxs-lookup"><span data-stu-id="c54a3-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
