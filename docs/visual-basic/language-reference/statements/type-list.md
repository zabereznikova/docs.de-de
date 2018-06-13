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
ms.openlocfilehash: 5fbb07154fce27feb257b431c1726446b42fbfe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605289"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="91199-102">Typenliste (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91199-102">Type List (Visual Basic)</span></span>
<span data-ttu-id="91199-103">Gibt an, die *Typparameter* für eine *generische* Programmierelement.</span><span class="sxs-lookup"><span data-stu-id="91199-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="91199-104">Mehrere Parameter werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="91199-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="91199-105">Nachfolgend ist die Syntax für einen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="91199-105">Following is the syntax for one type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91199-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="91199-106">Syntax</span></span>  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="91199-107">Teile</span><span class="sxs-lookup"><span data-stu-id="91199-107">Parts</span></span>  
  
|<span data-ttu-id="91199-108">Begriff</span><span class="sxs-lookup"><span data-stu-id="91199-108">Term</span></span>|<span data-ttu-id="91199-109">Definition</span><span class="sxs-lookup"><span data-stu-id="91199-109">Definition</span></span>|  
|---|---|  
|`genericmodifier`|<span data-ttu-id="91199-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="91199-110">Optional.</span></span> <span data-ttu-id="91199-111">Kann nur in generischen Schnittstellen und Delegaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91199-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="91199-112">Sie können einen Typ kovariant deklarieren, indem die [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) Schlüsselwort oder kontravariant mithilfe der [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="91199-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="91199-113">Siehe [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="91199-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|  
|`typename`|<span data-ttu-id="91199-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="91199-114">Required.</span></span> <span data-ttu-id="91199-115">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="91199-115">Name of the type parameter.</span></span> <span data-ttu-id="91199-116">Dies ist ein Platzhalter, durch einen definierten, durch das entsprechende Typargument bereitgestellten Typ ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="91199-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|  
|`constraintlist`|<span data-ttu-id="91199-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="91199-117">Optional.</span></span> <span data-ttu-id="91199-118">Liste der Anforderungen, die den Datentyp zu beschränken, die für die angegeben werden können `typename`.</span><span class="sxs-lookup"><span data-stu-id="91199-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="91199-119">Wenn Sie mehrere Einschränkungen verfügen, schließen Sie sie in geschweifte Klammern (`{ }`) und trennen Sie diese durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="91199-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="91199-120">Führen Sie die Einschränkungsliste mit dem [als](../../../visual-basic/language-reference/statements/as-clause.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="91199-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="91199-121">Verwenden Sie `As` nur einmal am Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="91199-121">You use `As` only once, at the beginning of the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91199-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91199-122">Remarks</span></span>  
 <span data-ttu-id="91199-123">Jedes generische Programmierelement muss mindestens ein Typparameter akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="91199-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="91199-124">Ein Typparameter ist ein Platzhalter für einen bestimmten Typ (ein *konstruierte Element*), dass Clientcode gibt an, wenn er eine Instanz des generischen Typs erstellt.</span><span class="sxs-lookup"><span data-stu-id="91199-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="91199-125">Sie können definieren Sie eine generische Klasse, Struktur, Schnittstelle, Prozedur, klicken oder delegieren.</span><span class="sxs-lookup"><span data-stu-id="91199-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>  
  
 <span data-ttu-id="91199-126">Weitere Informationen dazu, wann einen generischen Typ definieren, finden Sie unter [generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="91199-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="91199-127">Weitere Informationen zu Typparameternamen, finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="91199-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="91199-128">Regeln</span><span class="sxs-lookup"><span data-stu-id="91199-128">Rules</span></span>  
  
-   <span data-ttu-id="91199-129">**Klammern.**</span><span class="sxs-lookup"><span data-stu-id="91199-129">**Parentheses.**</span></span> <span data-ttu-id="91199-130">Wenn Sie eine Typparameterliste angeben, Sie es in Klammern einschließen müssen und führen Sie die Liste mit den [von](../../../visual-basic/language-reference/statements/of-clause.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="91199-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="91199-131">Verwenden Sie `Of` nur einmal am Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="91199-131">You use `Of` only once, at the beginning of the list.</span></span>  
  
-   <span data-ttu-id="91199-132">**Einschränkungen.**</span><span class="sxs-lookup"><span data-stu-id="91199-132">**Constraints.**</span></span> <span data-ttu-id="91199-133">Eine Liste der *Einschränkungen* für einen Parameter die folgenden Elemente in beliebiger Kombination enthalten:</span><span class="sxs-lookup"><span data-stu-id="91199-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>  
  
    -   <span data-ttu-id="91199-134">Eine beliebige Anzahl von Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="91199-134">Any number of interfaces.</span></span> <span data-ttu-id="91199-135">Der angegebene Typ muss in dieser Liste jede Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="91199-135">The supplied type must implement every interface in this list.</span></span>  
  
    -   <span data-ttu-id="91199-136">Höchstens einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="91199-136">At most one class.</span></span> <span data-ttu-id="91199-137">Der angegebene Typ muss von dieser Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="91199-137">The supplied type must inherit from that class.</span></span>  
  
    -   <span data-ttu-id="91199-138">Das `New`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="91199-138">The `New` keyword.</span></span> <span data-ttu-id="91199-139">Der angegebene Typ muss einen parameterlosen Konstruktor verfügbar machen, den der generische Typ zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="91199-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="91199-140">Dies ist hilfreich, wenn einen Typparameter durch eine oder mehrere Schnittstellen zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="91199-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="91199-141">Ein Typ, der Schnittstellen implementiert macht nicht unbedingt einen Konstruktor, und je nach den Zugriff für einen Konstruktor, der Code in den generischen Typ möglicherweise nicht darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="91199-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>  
  
    -   <span data-ttu-id="91199-142">Entweder die `Class` Schlüsselwort oder der `Structure` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="91199-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="91199-143">Die `Class` -Schlüsselwort schränkt einen generischen Typparameter erforderlich ist, dass jedes übergebene Typargument ein Verweistyp, z. B. eine Zeichenfolge, Array oder Delegaten, oder ein Objekt aus einer Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="91199-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="91199-144">Die `Structure` -Schlüsselwort schränkt einen generischen Typparameter erforderlich ist, dass alle an sie übergebene Typargument ein Werttyp ist, werden z. B. eine Struktur, Enumeration oder ein elementarer Datentyp.</span><span class="sxs-lookup"><span data-stu-id="91199-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="91199-145">Darf keine enthalten beide `Class` und `Structure` in der gleichen `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="91199-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>  
  
     <span data-ttu-id="91199-146">Der angegebene Typ muss jede Anforderung, die Sie in einschließen erfüllen `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="91199-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>  
  
     <span data-ttu-id="91199-147">Einschränkungen für jeden Typparameter sind unabhängig von Einschränkungen für andere Type-Parameter.</span><span class="sxs-lookup"><span data-stu-id="91199-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="91199-148">Verhalten</span><span class="sxs-lookup"><span data-stu-id="91199-148">Behavior</span></span>  
  
-   <span data-ttu-id="91199-149">**Zeitpunkt der Kompilierung Ersetzung.**</span><span class="sxs-lookup"><span data-stu-id="91199-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="91199-150">Wenn Sie einen konstruierten Typ aus einem generischen Programmierelements erstellen, geben Sie einen definierten Typ für jeden Typparameter.</span><span class="sxs-lookup"><span data-stu-id="91199-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="91199-151">Visual Basic-Compiler ersetzt für jedes Vorkommen eines angegebenen Typs `typename` innerhalb des generischen Elements.</span><span class="sxs-lookup"><span data-stu-id="91199-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>  
  
-   <span data-ttu-id="91199-152">**Falls keine Einschränkungen vorliegen.**</span><span class="sxs-lookup"><span data-stu-id="91199-152">**Absence of Constraints.**</span></span> <span data-ttu-id="91199-153">Wenn Sie keine Einschränkungen für einen Typparameter angeben, wird Code beschränkt auf die Operationen und Member, die von unterstützt die [Object-Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md) für den Typparameter.</span><span class="sxs-lookup"><span data-stu-id="91199-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91199-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91199-154">Example</span></span>  
 <span data-ttu-id="91199-155">Im folgenden Beispiel wird die rumpfdefinition einer generischen Wörterbuch-Klasse, z. B. eine Skelette-Funktion um einen neuen Eintrag zum Wörterbuch hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="91199-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="91199-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91199-156">Example</span></span>  
 <span data-ttu-id="91199-157">Da `dictionary` ist generisch ist, der Code, die verwendet werden kann eine Vielzahl von Objekten daraus erstellen, jeweils die gleiche Funktionalität ist jedoch auf einen anderen Datentyp fungiert.</span><span class="sxs-lookup"><span data-stu-id="91199-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="91199-158">Das folgende Beispiel zeigt eine Codezeile erstellt eine `dictionary` -Objekt mit `String` Einträge und `Integer` Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="91199-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="91199-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91199-159">Example</span></span>  
 <span data-ttu-id="91199-160">Das folgende Beispiel zeigt die entsprechende rumpfdefinition, die im vorherigen Beispiel generiert.</span><span class="sxs-lookup"><span data-stu-id="91199-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="91199-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91199-161">See Also</span></span>  
 [<span data-ttu-id="91199-162">Of</span><span class="sxs-lookup"><span data-stu-id="91199-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
 [<span data-ttu-id="91199-163">New-Operator</span><span class="sxs-lookup"><span data-stu-id="91199-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="91199-164">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="91199-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="91199-165">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="91199-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="91199-166">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="91199-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="91199-167">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="91199-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="91199-168">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="91199-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="91199-169">Gewusst wie: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="91199-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="91199-170">Kovarianz und Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="91199-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="91199-171">In</span><span class="sxs-lookup"><span data-stu-id="91199-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [<span data-ttu-id="91199-172">Out</span><span class="sxs-lookup"><span data-stu-id="91199-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
