---
title: Automatische Verallgemeinerung (F#)
description: "Erfahren Sie, wie f# automatisch die Argumente und Funktionstypen verallgemeinert, damit sie mit verschiedenen möglichst zusammenarbeiten."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 14a3554c-3fad-4eba-a93d-8ba07d1245b4
ms.openlocfilehash: d60831084cef76ce29f64322362b4920520f71d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="automatic-generalization"></a><span data-ttu-id="ac209-104">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="ac209-104">Automatic Generalization</span></span>

<span data-ttu-id="ac209-105">F# verwendet Typrückschluss die Arten von Funktionen und Ausdrücke auswerten.</span><span class="sxs-lookup"><span data-stu-id="ac209-105">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="ac209-106">In diesem Thema wird beschrieben, wie f# automatisch die Argumente und Funktionstypen verallgemeinert, damit sie mit verschiedenen zusammenarbeiten, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="ac209-106">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>


## <a name="automatic-generalization"></a><span data-ttu-id="ac209-107">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="ac209-107">Automatic Generalization</span></span>
<span data-ttu-id="ac209-108">F#-Compiler, bestimmt Wenn sie den Typrückschluss für eine Funktion ausführt, ob es sich bei angegebenem Parameter generisch sein kann.</span><span class="sxs-lookup"><span data-stu-id="ac209-108">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="ac209-109">Der Compiler überprüft jeden Parameter und bestimmt, ob die Funktion eine Abhängigkeit für den spezifischen Typ der Parameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="ac209-109">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="ac209-110">Wenn dies nicht der Fall ist, wird der Typ abgeleitet, generisch sein.</span><span class="sxs-lookup"><span data-stu-id="ac209-110">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="ac209-111">Das folgende Codebeispiel veranschaulicht eine Funktion, die der Compiler leitet um generisch sein.</span><span class="sxs-lookup"><span data-stu-id="ac209-111">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="ac209-112">Der Typ wird davon ausgegangen werden `'a -> 'a -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="ac209-112">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="ac209-113">Der Typ gibt an, dass dies eine Funktion akzeptiert zwei Argumente vom gleichen unbekannten Typ und gibt einen Wert desselben Typs zurück.</span><span class="sxs-lookup"><span data-stu-id="ac209-113">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="ac209-114">Einer der Gründe, die der previous-Funktion kann generisch ist, das größer-als-Operator (`>`) generisch.</span><span class="sxs-lookup"><span data-stu-id="ac209-114">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="ac209-115">Größer-als Operator hat eine Signatur `'a -> 'a -> bool`.</span><span class="sxs-lookup"><span data-stu-id="ac209-115">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="ac209-116">Nicht alle Operatoren sind generisch, und wenn der Code in einer Funktion einen Parametertyp zusammen mit einer nicht generischen Funktion or -Operator verwendet, kann nicht, Parametertyp verallgemeinert werden.</span><span class="sxs-lookup"><span data-stu-id="ac209-116">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="ac209-117">Da `max` ist generisch, er kann verwendet werden mit Typen wie z. B. `int`, `float`usw., wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac209-117">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="ac209-118">Allerdings müssen der zwei Argumente vom gleichen Typ sein.</span><span class="sxs-lookup"><span data-stu-id="ac209-118">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="ac209-119">Die Signatur ist `'a -> 'a -> 'a`, nicht `'a -> 'b -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="ac209-119">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="ac209-120">Aus diesem Grund generiert der folgende Code einen Fehler, da die Datentypen nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ac209-120">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="ac209-121">Die `max` Funktion funktioniert auch mit jedem Typ, der größer unterstützt-als-Operator.</span><span class="sxs-lookup"><span data-stu-id="ac209-121">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="ac209-122">Aus diesem Grund auch können er auf eine Zeichenfolge ist, Sie wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac209-122">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]
    
## <a name="value-restriction"></a><span data-ttu-id="ac209-123">Wertebeschränkung</span><span class="sxs-lookup"><span data-stu-id="ac209-123">Value Restriction</span></span>
<span data-ttu-id="ac209-124">Der Compiler führt automatische Verallgemeinerung nur für vollständige Funktionsdefinitionen, die expliziten Argumente verfügen, und klicken Sie auf einfache unveränderliche Werte.</span><span class="sxs-lookup"><span data-stu-id="ac209-124">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="ac209-125">Dies bedeutet, dass der Compiler einen Fehler ausgibt, wenn Sie versuchen, den Code zu kompilieren, die nicht ausreichend für einen bestimmten Typ eingeschränkt ist, jedoch ist auch nicht generalisierbar.</span><span class="sxs-lookup"><span data-stu-id="ac209-125">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="ac209-126">Die Fehlermeldung für dieses Problem bezieht sich auf diese Einschränkung auf automatische Verallgemeinerung für Werte als die *Wert Einschränkung*.</span><span class="sxs-lookup"><span data-stu-id="ac209-126">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="ac209-127">In der Regel tritt auf, der Wert Einschränkung Fehler, wenn ein Konstrukt generisch sein sollen, aber der Compiler hat nicht genügend Informationen, um ihn zu verallgemeinern oder wenn Sie unbeabsichtigt genügend Typinformationen in einem nicht generischen Konstrukt auslassen.</span><span class="sxs-lookup"><span data-stu-id="ac209-127">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="ac209-128">Die Lösung mit dem Wert Einschränkung Fehler besteht darin, expliziter Anmeldeinformationen um Problem mithilfe eines Rückschlusses "Typ" in einem der folgenden Methoden ausführlicher zu beschränken:</span><span class="sxs-lookup"><span data-stu-id="ac209-128">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>


- <span data-ttu-id="ac209-129">Beschränken eines Typs für nicht generische werden durch einen Wert oder einen Parameter eine expliziten typanmerkung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ac209-129">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="ac209-130">Wenn das Problem ein Konstrukt verallgemeinerbaren definieren Sie eine generische Funktion, z. B. eine funktionskomposition verwenden oder nicht vollständig mit Currying Funktionsargumente angewendet wurde ist, versucht die Funktion wie die Definition einer gewöhnlichen Funktion schreiben.</span><span class="sxs-lookup"><span data-stu-id="ac209-130">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="ac209-131">Wenn das Problem ein Ausdruck ist, der ist zu komplex werden generalisiert, stellen es in eine Funktion durch einen zusätzlichen, nicht verwendeten Parameter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ac209-131">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="ac209-132">Fügen Sie explizite generische Typparameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac209-132">Add explicit generic type parameters.</span></span> <span data-ttu-id="ac209-133">Diese Option wird selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac209-133">This option is rarely used.</span></span>

- <span data-ttu-id="ac209-134">Die folgenden Codebeispiele veranschaulichen jedes dieser Szenarien.</span><span class="sxs-lookup"><span data-stu-id="ac209-134">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="ac209-135">Fall 1: Zu komplexer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ac209-135">Case 1: Too complex an expression.</span></span> <span data-ttu-id="ac209-136">In diesem Beispiel wird die Liste `counter` erhebt auf `int option ref`, aber es ist nicht als einfache unveränderliche Wert definiert.</span><span class="sxs-lookup"><span data-stu-id="ac209-136">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="ac209-137">Fall 2: Verwenden eines Konstrukts verallgemeinerbaren eine generische Funktion definieren.</span><span class="sxs-lookup"><span data-stu-id="ac209-137">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="ac209-138">In diesem Beispiel wird das Konstrukt verallgemeinerbaren, da hierbei partielle Anwendung von Funktionsargumenten.</span><span class="sxs-lookup"><span data-stu-id="ac209-138">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="ac209-139">Fall 3: Hinzufügen eines zusätzlichen, nicht verwendeten Parameters.</span><span class="sxs-lookup"><span data-stu-id="ac209-139">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="ac209-140">Da dieser Ausdruck nicht einfach genug für Verallgemeinerung ist, gibt der Compiler den Wert Einschränkung Fehler an.</span><span class="sxs-lookup"><span data-stu-id="ac209-140">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="ac209-141">Fall 4: Hinzufügen von Typparametern.</span><span class="sxs-lookup"><span data-stu-id="ac209-141">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="ac209-142">Im letzten Fall wird der Wert einer Typfunktion, die verwendet werden können, um Werte verschiedener Typen, z. B. wie folgt erstellen:</span><span class="sxs-lookup"><span data-stu-id="ac209-142">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="ac209-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac209-143">See Also</span></span>
[<span data-ttu-id="ac209-144">Typableitung</span><span class="sxs-lookup"><span data-stu-id="ac209-144">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="ac209-145">Generika</span><span class="sxs-lookup"><span data-stu-id="ac209-145">Generics</span></span>](index.md)

[<span data-ttu-id="ac209-146">Statisch aufgelöste Typparameter</span><span class="sxs-lookup"><span data-stu-id="ac209-146">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)

[<span data-ttu-id="ac209-147">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ac209-147">Constraints</span></span>](constraints.md)

