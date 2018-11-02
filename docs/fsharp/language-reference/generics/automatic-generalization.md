---
title: Automatische Verallgemeinerung (F#)
description: Erfahren Sie, wie F# automatisch die Argumente und Funktionstypen verallgemeinert, damit sie mit mehreren Typen nach Möglichkeit funktionieren.
ms.date: 05/16/2016
ms.openlocfilehash: 84de9cbb2b9fcf2488393f7dbdfc3b610cdcffb0
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43855776"
---
# <a name="automatic-generalization"></a><span data-ttu-id="ae3fd-103">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="ae3fd-103">Automatic Generalization</span></span>

<span data-ttu-id="ae3fd-104">F#-verwendet den Typrückschluss, um die Arten von Funktionen und Ausdrücke zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="ae3fd-105">In diesem Thema wird beschrieben, wie F# automatisch die Argumente und Funktionstypen verallgemeinert, damit sie mit mehreren Arten funktionieren, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>

## <a name="automatic-generalization"></a><span data-ttu-id="ae3fd-106">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="ae3fd-106">Automatic Generalization</span></span>

<span data-ttu-id="ae3fd-107">Der F#-Compiler, bestimmt wenn er den Typrückschluss auf eine Funktion ausführt, ob es sich bei ein bestimmten Parameter generisch sein kann.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="ae3fd-108">Der Compiler untersucht jeden Parameter und bestimmt, ob die Funktion eine Abhängigkeit vom angegebenen Typ dieses Parameters hat.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="ae3fd-109">Wenn dies nicht der Fall ist, wird der Typ abgeleitet, generisch sein.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="ae3fd-110">Im folgenden Codebeispiel wird veranschaulicht, eine Funktion, die der Compiler leitet ab, um generisch sein.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="ae3fd-111">Der Typ wird abgeleitet sein `'a -> 'a -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="ae3fd-112">Der Typ gibt an, dass dies eine Funktion, die akzeptiert zwei Argumente des gleichen unbekannten Typs und gibt einen Wert desselben Typs zurück.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="ae3fd-113">Einer der Gründe, die die vorherige Funktion sein, können generisch ist, das größer-als-Operator (`>`) selbst generisch ist.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="ae3fd-114">Größer-als Operator die Signatur hat `'a -> 'a -> bool`.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="ae3fd-115">Nicht alle Operatoren sind generisch, und wenn der Code in einer Funktion einen Parametertyp zusammen mit einer nicht generischen Funktion oder Operator verwendet, kann dieser Parametertyp kann nicht generalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="ae3fd-116">Da `max` ist generisch ist, sie können mit Typen verwendet werden wie z. B. `int`, `float`und so weiter, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="ae3fd-117">Allerdings müssen die beiden Argumente vom gleichen Typ sein.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="ae3fd-118">Die Signatur ist `'a -> 'a -> 'a`, nicht `'a -> 'b -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="ae3fd-119">Aus diesem Grund generiert der folgende Code einen Fehler, da die Datentypen nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="ae3fd-120">Die `max` Funktion funktioniert auch mit jeder Typ, der größer unterstützt-als-Operator.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="ae3fd-121">Aus diesem Grund könnte auch auf eine Zeichenfolge, Verwendung wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a><span data-ttu-id="ae3fd-122">Wertebeschränkung</span><span class="sxs-lookup"><span data-stu-id="ae3fd-122">Value Restriction</span></span>

<span data-ttu-id="ae3fd-123">Der Compiler führt die automatische Verallgemeinerung nur für vollständige Funktionsdefinitionen, die expliziten Argumente haben, und klicken Sie auf einfache unveränderlichen Werten.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="ae3fd-124">Dies bedeutet, dass der Compiler einen Fehler ausgibt, wenn Sie versuchen, Code zu kompilieren, die nicht ausreichend sollen einen bestimmten Typ beschränkt ist, jedoch ist auch nicht generalisierbar.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="ae3fd-125">Die Fehlermeldung für dieses Problem bezieht sich auf die diese Einschränkung für die automatische Verallgemeinerung für Werte als die *wertebeschränkung*.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="ae3fd-126">In der Regel tritt auf, der Wert Einschränkung Fehler, wenn Sie möchten ein Konstrukt generisch sein, aber der Compiler hat nicht genügend Informationen, um sie zu generalisieren oder unbeabsichtigt genügend Typinformationen in einer nicht generischen Konstrukts ohne Angabe.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="ae3fd-127">Die Lösung auf den Wert Einschränkung Fehler besteht darin, geben Sie explizitere Informationen, um das Problem Type Inference ausführlicher in einem der folgenden Methoden zu beschränken:</span><span class="sxs-lookup"><span data-stu-id="ae3fd-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>

- <span data-ttu-id="ae3fd-128">Einen Typ nicht generischen ist durch das Hinzufügen einer expliziten Typ-Anmerkung auf einen Wert oder einen Parameter zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="ae3fd-129">Wenn das Problem ein Konstrukt verallgemeinerbaren definieren Sie eine generische Funktion, wie z. B. eine funktionskomposition verwendet oder nicht vollständig Curry Funktionsargumente angewendet, versuchen Sie, Schreiben Sie die Funktion wie eine normale Funktionsdefinition.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="ae3fd-130">Wenn das Problem ein Ausdruck ist, der ist zu komplex für den generalisiert werden, stellen es in eine Funktion, durch das Hinzufügen eines zusätzlichen, nicht verwendeten Parameters.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="ae3fd-131">Fügen Sie explizite generische Typparameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="ae3fd-132">Diese Option wird nur selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-132">This option is rarely used.</span></span>

- <span data-ttu-id="ae3fd-133">Die folgenden Codebeispiele veranschaulichen jedes dieser Szenarien.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="ae3fd-134">Fall 1: Zu komplex ist ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="ae3fd-135">In diesem Beispiel wird die Liste `counter` dient `int option ref`, aber es ist nicht definiert, wie ein einfacher, unveränderliche Wert.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="ae3fd-136">Fall 2: Verwenden ein verallgemeinerbaren-Konstrukt, um eine generische Funktion zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="ae3fd-137">In diesem Beispiel ist das Konstrukt verallgemeinerbaren, da hierbei partielle Anwendung von Funktionsargumenten.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="ae3fd-138">Fall 3: Hinzufügen eines zusätzlichen, nicht verwendeten Parameters.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="ae3fd-139">Da dieses Ausdrucks nicht vorhanden sind, die für die Generalisierung einfach genug ist, gibt der Compiler den Wert Einschränkung Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="ae3fd-140">Fall 4: Hinzufügen von Typparametern.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="ae3fd-141">Im letzten Fall wird der Wert einer Typfunktion, die verwendet werden kann, um die Werte verschiedener Typen, z. B. wie folgt erstellen:</span><span class="sxs-lookup"><span data-stu-id="ae3fd-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="ae3fd-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae3fd-142">See also</span></span>

- [<span data-ttu-id="ae3fd-143">Typableitung</span><span class="sxs-lookup"><span data-stu-id="ae3fd-143">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="ae3fd-144">Generika</span><span class="sxs-lookup"><span data-stu-id="ae3fd-144">Generics</span></span>](index.md)
- [<span data-ttu-id="ae3fd-145">Statisch aufgelöste Typparameter</span><span class="sxs-lookup"><span data-stu-id="ae3fd-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)
- [<span data-ttu-id="ae3fd-146">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ae3fd-146">Constraints</span></span>](constraints.md)
