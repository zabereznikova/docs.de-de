---
title: Lokale Funktionen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 06/14/2017
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: 7b6b46a33430a4a58c78245a0ab3bed1e0fbcd9c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455373"
---
# <a name="local-functions-c-programming-guide"></a><span data-ttu-id="4445d-102">Lokale Funktionen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4445d-102">Local functions (C# Programming Guide)</span></span>

<span data-ttu-id="4445d-103">Ab C#-7.0 unterstützt C# *lokale Funktionen*.</span><span class="sxs-lookup"><span data-stu-id="4445d-103">Starting with C# 7.0, C# supports *local functions*.</span></span> <span data-ttu-id="4445d-104">Lokale Funktionen sind private Methoden eines Typs, die in einem anderen Member geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="4445d-104">Local functions are private methods of a type that are nested in another member.</span></span> <span data-ttu-id="4445d-105">Sie können nur aus ihrem enthaltenden Member aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4445d-105">They can only be called from their containing member.</span></span> <span data-ttu-id="4445d-106">Lokale Funktionen können deklariert und aufgerufen werden aus:</span><span class="sxs-lookup"><span data-stu-id="4445d-106">Local functions can be declared in and called from:</span></span>

- <span data-ttu-id="4445d-107">Methoden, insbesondere Iteratormethoden und Async-Methoden</span><span class="sxs-lookup"><span data-stu-id="4445d-107">Methods, especially iterator methods and async methods</span></span>
- <span data-ttu-id="4445d-108">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="4445d-108">Constructors</span></span>
- <span data-ttu-id="4445d-109">Eigenschaftenaccessoren</span><span class="sxs-lookup"><span data-stu-id="4445d-109">Property accessors</span></span>
- <span data-ttu-id="4445d-110">Ereignisaccessoren</span><span class="sxs-lookup"><span data-stu-id="4445d-110">Event accessors</span></span>
- <span data-ttu-id="4445d-111">Anonymen Methoden</span><span class="sxs-lookup"><span data-stu-id="4445d-111">Anonymous methods</span></span>
- <span data-ttu-id="4445d-112">Lambdaausdrücke</span><span class="sxs-lookup"><span data-stu-id="4445d-112">Lambda expressions</span></span>
- <span data-ttu-id="4445d-113">Finalizer</span><span class="sxs-lookup"><span data-stu-id="4445d-113">Finalizers</span></span>
- <span data-ttu-id="4445d-114">Anderen lokalen Funktionen</span><span class="sxs-lookup"><span data-stu-id="4445d-114">Other local functions</span></span>

<span data-ttu-id="4445d-115">Lokale Funktionen können jedoch nicht in einem Ausdruckskörpermember deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="4445d-115">However, local functions can't be declared inside an expression-bodied member.</span></span>

> [!NOTE]
> <span data-ttu-id="4445d-116">In einigen Fällen können Sie einen Lambdaausdruck zum Implementieren von Funktionen verwenden, die auch von einer lokalen Funktion unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="4445d-116">In some cases, you can use a lambda expression to implement functionality also supported by a local function.</span></span> <span data-ttu-id="4445d-117">Einen Vergleich finden Sie unter [Lokale Funktionen im Vergleich zu Lambdaausdrücken](../../local-functions-vs-lambdas.md).</span><span class="sxs-lookup"><span data-stu-id="4445d-117">For a comparison, see [Local functions compared to Lambda expressions](../../local-functions-vs-lambdas.md).</span></span>

<span data-ttu-id="4445d-118">Lokale Funktionen machen den Zweck Ihres Codes deutlich.</span><span class="sxs-lookup"><span data-stu-id="4445d-118">Local functions make the intent of your code clear.</span></span> <span data-ttu-id="4445d-119">Beim Lesen des Codes wird deutlich, dass die Methode nur von der enthaltenden Methode aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4445d-119">Anyone reading your code can see that the method is not callable except by the containing method.</span></span> <span data-ttu-id="4445d-120">Bei Teamprojekten wird auch verhindert, dass ein anderer Entwickler die Methode versehentlich direkt an anderer Stelle in der Klasse oder Struktur aufruft.</span><span class="sxs-lookup"><span data-stu-id="4445d-120">For team projects, they also make it impossible for another developer to mistakenly call the method directly from elsewhere in the class or struct.</span></span>
 
## <a name="local-function-syntax"></a><span data-ttu-id="4445d-121">Syntax einer lokalen Funktion</span><span class="sxs-lookup"><span data-stu-id="4445d-121">Local function syntax</span></span>

<span data-ttu-id="4445d-122">Eine lokale Funktion wird definiert als eine geschachtelte Methode in einem enthaltenden Member.</span><span class="sxs-lookup"><span data-stu-id="4445d-122">A local function is defined as a nested method inside a containing member.</span></span> <span data-ttu-id="4445d-123">Ihre Definition besitzt die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="4445d-123">Its definition has the following syntax:</span></span>

```csharp
<modifiers: async | unsafe> <return-type> <method-name> <parameter-list>
```

<span data-ttu-id="4445d-124">Lokale Funktionen können die Modifizierer [async](../../language-reference/keywords/async.md) und [unsafe](../../language-reference/keywords/unsafe.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4445d-124">Local functions can use the [async](../../language-reference/keywords/async.md) and [unsafe](../../language-reference/keywords/unsafe.md) modifiers.</span></span> 

<span data-ttu-id="4445d-125">Beachten Sie, dass alle im enthaltenden Member definierten lokalen Variablen, einschließlich der Methodenparameter, in der lokalen Funktion zugänglich sind.</span><span class="sxs-lookup"><span data-stu-id="4445d-125">Note that all local variables that are defined in the containing member, including its method parameters, are accessible in the local function.</span></span> 

<span data-ttu-id="4445d-126">Im Gegensatz zu einer Methodendefinition kann die Definition einer lokalen Funktion keines der folgenden Elemente enthalten:</span><span class="sxs-lookup"><span data-stu-id="4445d-126">Unlike a method definition, a local function definition cannot include the following elements:</span></span>

- <span data-ttu-id="4445d-127">Den Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="4445d-127">The member access modifier.</span></span> <span data-ttu-id="4445d-128">Da alle lokale Funktionen privat sind, generiert das Verwenden eines Zugriffsmodifizierers wie etwa das Schlüsselwort `private` den Compilerfehler CS0106 „Der Modifizierer ‚private‘ ist für dieses Element nicht gültig“.</span><span class="sxs-lookup"><span data-stu-id="4445d-128">Because all local functions are private, including an access modifier, such as the `private` keyword, generates compiler error CS0106, "The modifier 'private' is not valid for this item."</span></span>
 
- <span data-ttu-id="4445d-129">Das Schlüsselwort [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="4445d-129">The [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="4445d-130">Die Verwendung des Schlüsselworts `static` generiert den Compilerfehler CS0106 „Der Modifizierer ‚static‘ ist für dieses Element nicht gültig“.</span><span class="sxs-lookup"><span data-stu-id="4445d-130">Including the `static` keyword generates compiler error CS0106, "The modifier 'static' is not valid for this item."</span></span>

<span data-ttu-id="4445d-131">Darüber hinaus können keine Attribute auf lokale Funktionen oder ihre Parameter und Typparameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="4445d-131">In addition, attributes can't be applied to the local function or to its parameters and type parameters.</span></span> 
 
<span data-ttu-id="4445d-132">Das folgende Beispiel definiert eine lokale Funktion mit dem Namen `AppendPathSeparator`, die für eine Methode mit dem Namen `GetText` privat ist:</span><span class="sxs-lookup"><span data-stu-id="4445d-132">The following example defines a local function named `AppendPathSeparator` that is private to a method named `GetText`:</span></span>
   
[!code-csharp[LocalFunctionExample](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  
   
## <a name="local-functions-and-exceptions"></a><span data-ttu-id="4445d-133">Lokale Funktionen und Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="4445d-133">Local functions and exceptions</span></span>

<span data-ttu-id="4445d-134">Eine nützliche Funktion von lokalen Funktionen ist die Tatsache, dass sie Ausnahmen sofort verfügbar machen können.</span><span class="sxs-lookup"><span data-stu-id="4445d-134">One of the useful features of local functions is that they can allow exceptions to surface immediately.</span></span> <span data-ttu-id="4445d-135">Bei Methodeniteratoren werden Ausnahmen erst eingeblendet, wenn die zurückgegebene Sequenz aufgelistet wird, und nicht, wenn der Iterator abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4445d-135">For method iterators, exceptions are surfaced only when the returned sequence is enumerated, and not when the iterator is retrieved.</span></span> <span data-ttu-id="4445d-136">Bei async-Methoden werden Ausnahmen festgestellt, wenn die zurückgegebene Aufgabe erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="4445d-136">For async methods, any exceptions thrown in an async method are observed when the returned task is awaited.</span></span> 

<span data-ttu-id="4445d-137">Das folgende Beispiel definiert eine `OddSequence`-Methode, die ungerade Zahlen in einem angegebenen Bereich aufzählt.</span><span class="sxs-lookup"><span data-stu-id="4445d-137">The following example defines an `OddSequence` method that enumerates odd numbers between a specified range.</span></span> <span data-ttu-id="4445d-138">Da eine Zahl größer als 100 an die `OddSequence`-Enumeratormethode übergeben wird, wird <xref:System.ArgumentOutOfRangeException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="4445d-138">Because it passes a number greater than 100 to the `OddSequence` enumerator method, the method throws an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="4445d-139">Die Ausgabe des Beispiels zeigt, dass die Ausnahme erst beim Durchlaufen der Zahlen und nicht beim Abrufen des Enumerators eingeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="4445d-139">As the output from the example shows, the exception surfaces only when you iterate the numbers, and not when you retrieve the enumerator.</span></span>

[!code-csharp[LocalFunctionIterator1](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)] 

<span data-ttu-id="4445d-140">Stattdessen können Sie während der Validierung und vor Abrufen des Iterators wie im folgenden Beispiel dargestellt eine Ausnahme auslösen, indem der Iterator aus einer lokalen Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4445d-140">Instead, you can throw an exception when performing validation and before retrieving the iterator by returning the iterator from a local function, as the following example shows.</span></span>

[!code-csharp[LocalFunctionIterator2](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

<span data-ttu-id="4445d-141">Lokale Funktionen können auf ähnliche Weise verwendet werden, um Ausnahmen außerhalb des asynchronen Vorgangs zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="4445d-141">Local functions can be used in a similar way to handle exceptions outside of the asynchronous operation.</span></span> <span data-ttu-id="4445d-142">Normalerweise erfordern Ausnahmen in einer async-Methode die Überprüfung der inneren Ausnahmen von <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="4445d-142">Ordinarily, exceptions thrown in async method require that you examine the inner exceptions of an <xref:System.AggregateException>.</span></span> <span data-ttu-id="4445d-143">Lokale Funktionen ermöglichen einen schnellen Abbruch Ihres Codes. Ihre Ausnahme kann sowohl synchron ausgelöst als auch beobachtet werden.</span><span class="sxs-lookup"><span data-stu-id="4445d-143">Local functions allow your code to fail fast and allow your exception to be both thrown and observed synchronously.</span></span>

<span data-ttu-id="4445d-144">Im folgenden Beispiel wird eine asynchrone Methode mit dem Namen `GetMultipleAsync` verwendet, um für eine bestimmte Anzahl von Sekunden anzuhalten und ein zufälliges Vielfaches dieser Sekundenanzahl zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="4445d-144">The following example uses an asynchronous method named `GetMultipleAsync` to pause for a specified number of seconds and return a value that is a random multiple of that number of seconds.</span></span> <span data-ttu-id="4445d-145">Die maximale Verzögerung beträgt 5 Sekunden. <xref:System.ArgumentOutOfRangeException> wird ausgegeben, wenn der Wert größer als 5 ist.</span><span class="sxs-lookup"><span data-stu-id="4445d-145">The maximum delay is 5 seconds; an <xref:System.ArgumentOutOfRangeException> results if the value is greater than 5.</span></span> <span data-ttu-id="4445d-146">Im folgenden Beispiel wird verdeutlicht, dass die Ausnahme, die bei der Übergabe eines Werts größer als 6 an die Methode `GetMultipleAsync` ausgelöst wird, von <xref:System.AggregateException> umschlossen wird, sobald die Methode `GetMultipleAsync` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4445d-146">As the following example shows, the exception that is thrown when a value of 6 is passed to the `GetMultipleAsync` method is wrapped in an <xref:System.AggregateException> after the `GetMultipleAsync` method begins execution.</span></span>

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)] 

<span data-ttu-id="4445d-147">Wie beim Methodeniterator kann der Code aus diesem Beispiel umgestaltet werden, um die Validierung vor Aufruf der asynchronen Methode durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="4445d-147">As we did with the method iterator, we can refactor the code from this example to perform the validation before calling the asynchronous method.</span></span> <span data-ttu-id="4445d-148">Die Ausgabe des folgenden Beispiels zeigt, dass <xref:System.ArgumentOutOfRangeException> nicht von einer <xref:System.AggregateException> umschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="4445d-148">As the output from the following example shows, the <xref:System.ArgumentOutOfRangeException> is not wrapped in a <xref:System.AggregateException>.</span></span>

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)] 

## <a name="see-also"></a><span data-ttu-id="4445d-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4445d-149">See also</span></span>

- [<span data-ttu-id="4445d-150">Methoden</span><span class="sxs-lookup"><span data-stu-id="4445d-150">Methods</span></span>](methods.md)
