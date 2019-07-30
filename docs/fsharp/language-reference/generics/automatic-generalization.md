---
title: Automatische Verallgemeinerung
description: Erfahren Sie, wie F# automatisch die Argumente und Funktionstypen verallgemeinert, damit sie mit mehreren Typen nach Möglichkeit funktionieren.
ms.date: 05/16/2016
ms.openlocfilehash: 501749a190d9770cbcd9848e3d528cba32fe6762
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630628"
---
# <a name="automatic-generalization"></a><span data-ttu-id="aeed9-103">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="aeed9-103">Automatic Generalization</span></span>

<span data-ttu-id="aeed9-104">F#verwendet den Typrückschluss, um die Typen von Funktionen und Ausdrücken auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="aeed9-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="aeed9-105">In diesem Thema wird beschrieben, wie F# automatisch die Argumente und Funktionstypen verallgemeinert, damit sie mit mehreren Arten funktionieren, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="aeed9-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>

## <a name="automatic-generalization"></a><span data-ttu-id="aeed9-106">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="aeed9-106">Automatic Generalization</span></span>

<span data-ttu-id="aeed9-107">Wenn F# der Compiler einen Typrückschluss für eine Funktion ausführt, bestimmt er, ob ein bestimmter Parameter generisch sein kann.</span><span class="sxs-lookup"><span data-stu-id="aeed9-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="aeed9-108">Der Compiler überprüft jeden Parameter und bestimmt, ob die Funktion eine Abhängigkeit vom jeweiligen Typ dieses Parameters aufweist.</span><span class="sxs-lookup"><span data-stu-id="aeed9-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="aeed9-109">Wenn dies nicht der Fall ist, wird der Typ als generisch abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="aeed9-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="aeed9-110">Im folgenden Codebeispiel wird eine Funktion veranschaulicht, die der Compiler als generisch herleitet.</span><span class="sxs-lookup"><span data-stu-id="aeed9-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="aeed9-111">Der Typ wird als abgeleitet `'a -> 'a -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="aeed9-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="aeed9-112">Der-Typ gibt an, dass es sich hierbei um eine Funktion handelt, die zwei Argumente desselben unbekannten Typs annimmt und einen Wert desselben Typs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="aeed9-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="aeed9-113">Einer der Gründe dafür, dass die vorherige Funktion generisch sein kann, ist, dass der größer`>`-als-Operator () selbst generisch ist.</span><span class="sxs-lookup"><span data-stu-id="aeed9-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="aeed9-114">Der größer-als-Operator hat die `'a -> 'a -> bool`Signatur.</span><span class="sxs-lookup"><span data-stu-id="aeed9-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="aeed9-115">Nicht alle Operatoren sind generisch, und wenn der Code in einer Funktion einen Parametertyp mit einer nicht generischen Funktion oder einem nicht generischen Operator verwendet, kann dieser Parametertyp nicht generalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="aeed9-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="aeed9-116">Da `max` generisch ist, kann es mit Typen `int`wie, `float`usw. verwendet werden, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="aeed9-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="aeed9-117">Allerdings müssen die beiden Argumente denselben Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="aeed9-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="aeed9-118">Die Signatur ist `'a -> 'a -> 'a`, nicht `'a -> 'b -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="aeed9-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="aeed9-119">Daher erzeugt der folgende Code einen Fehler, da die Typen nicht identisch sind.</span><span class="sxs-lookup"><span data-stu-id="aeed9-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="aeed9-120">Die `max` -Funktion funktioniert auch mit jedem Typ, der den größer-als-Operator unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aeed9-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="aeed9-121">Daher können Sie Sie auch für eine Zeichenfolge verwenden, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="aeed9-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a><span data-ttu-id="aeed9-122">Wert Einschränkung</span><span class="sxs-lookup"><span data-stu-id="aeed9-122">Value Restriction</span></span>

<span data-ttu-id="aeed9-123">Der Compiler führt die automatische Generalisierung nur für vollständige Funktionsdefinitionen mit expliziten Argumenten und für einfache unveränderliche Werte durch.</span><span class="sxs-lookup"><span data-stu-id="aeed9-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="aeed9-124">Dies bedeutet, dass der Compiler einen Fehler ausgibt, wenn Sie versuchen, Code zu kompilieren, der nicht ausreichend auf einen bestimmten Typ beschränkt ist, aber auch nicht verallgemeinerbar ist.</span><span class="sxs-lookup"><span data-stu-id="aeed9-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="aeed9-125">Die Fehlermeldung für dieses Problem bezieht sich auf diese Einschränkung bei der automatischen Generalisierung von Werten als *Wert Einschränkung*.</span><span class="sxs-lookup"><span data-stu-id="aeed9-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="aeed9-126">In der Regel tritt der Wert Einschränkungs Fehler auf, wenn ein Konstrukt generisch sein soll, der Compiler jedoch nicht über ausreichende Informationen verfügt, um ihn zu generalisieren, oder wenn Sie versehentlich ausreichende Typinformationen in einem nicht generischen Konstrukt weglassen.</span><span class="sxs-lookup"><span data-stu-id="aeed9-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="aeed9-127">Die Lösung für den Wert Einschränkungs Fehler besteht darin, ausführlichere Informationen bereitzustellen, um das Typrückschluss Problem mit einer der folgenden Methoden vollständig einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="aeed9-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>

- <span data-ttu-id="aeed9-128">Beschränken Sie einen Typ auf einen nicht generischen Typ, indem Sie einem Wert oder Parameter eine explizite Typanmerkung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aeed9-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="aeed9-129">Wenn das Problem ein nicht generisch erbares Konstrukt zum Definieren einer generischen Funktion verwendet, wie z. b. eine Funktions Komposition oder nicht vollständig angewendete currried-Funktionsargumente, versuchen Sie, die Funktion als normale Funktionsdefinition umzuschreiben.</span><span class="sxs-lookup"><span data-stu-id="aeed9-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="aeed9-130">Wenn das Problem ein Ausdruck ist, der zu komplex ist, um verallgemeinert zu werden, nehmen Sie ihn durch Hinzufügen eines zusätzlichen, nicht verwendeten Parameters in eine Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="aeed9-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="aeed9-131">Fügen Sie explizite generische Typparameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="aeed9-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="aeed9-132">Diese Option wird nur selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="aeed9-132">This option is rarely used.</span></span>

- <span data-ttu-id="aeed9-133">Die folgenden Codebeispiele veranschaulichen die einzelnen Szenarien.</span><span class="sxs-lookup"><span data-stu-id="aeed9-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="aeed9-134">Fall 1: Der Ausdruck ist zu komplex.</span><span class="sxs-lookup"><span data-stu-id="aeed9-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="aeed9-135">In diesem Beispiel ist die Liste `counter` vorgesehen `int option ref`, aber Sie ist nicht als einfacher unveränderlicher Wert definiert.</span><span class="sxs-lookup"><span data-stu-id="aeed9-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="aeed9-136">Fall 2: Verwenden eines nicht verallgemeinerbaren Konstrukts zum Definieren einer generischen Funktion.</span><span class="sxs-lookup"><span data-stu-id="aeed9-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="aeed9-137">In diesem Beispiel ist das Konstrukt nicht verallgemeinerbar, da es eine partielle Anwendung von Funktions Argumenten umfasst.</span><span class="sxs-lookup"><span data-stu-id="aeed9-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="aeed9-138">Fall 3: Hinzufügen eines zusätzlichen, nicht verwendeten Parameters.</span><span class="sxs-lookup"><span data-stu-id="aeed9-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="aeed9-139">Da dieser Ausdruck für die Generalisierung nicht einfach genug ist, gibt der Compiler den Wert Einschränkungs Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="aeed9-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="aeed9-140">Fall 4: Typparameter werden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="aeed9-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="aeed9-141">Im letzten Fall wird der Wert zu einer Typfunktion, die verwendet werden kann, um Werte von vielen verschiedenen Typen zu erstellen, z. b. wie folgt:</span><span class="sxs-lookup"><span data-stu-id="aeed9-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="aeed9-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aeed9-142">See also</span></span>

- [<span data-ttu-id="aeed9-143">Typableitung</span><span class="sxs-lookup"><span data-stu-id="aeed9-143">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="aeed9-144">Generika</span><span class="sxs-lookup"><span data-stu-id="aeed9-144">Generics</span></span>](index.md)
- [<span data-ttu-id="aeed9-145">Statisch aufgelöste Typparameter</span><span class="sxs-lookup"><span data-stu-id="aeed9-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)
- [<span data-ttu-id="aeed9-146">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="aeed9-146">Constraints</span></span>](constraints.md)
