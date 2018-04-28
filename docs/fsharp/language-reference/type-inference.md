---
title: Typrückschluss (F#)
description: Erfahren Sie, wie der f#-Compiler die Typen von Werten, Variablen, Parameter und Rückgabewerte ableitet.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: b5f7861c0a638baebfe72c9b4cf7dca119339ae3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="type-inference"></a><span data-ttu-id="409c1-103">Typableitung</span><span class="sxs-lookup"><span data-stu-id="409c1-103">Type Inference</span></span>

<span data-ttu-id="409c1-104">In diesem Thema wird beschrieben, wie der f#-Compiler die Typen von Werten, Variablen, Parameter und Rückgabewerte ableitet.</span><span class="sxs-lookup"><span data-stu-id="409c1-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="409c1-105">Im Allgemeinen den Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="409c1-105">Type Inference in General</span></span>
<span data-ttu-id="409c1-106">Das Konzept der Typrückschluss ist, dass Sie keine geben die Typen von f#-Konstrukte, außer wenn der Compiler eindeutig den Typ ableiten kann.</span><span class="sxs-lookup"><span data-stu-id="409c1-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="409c1-107">Weglassen von expliziten Typinformationen bedeutet nicht, dass f# eine dynamisch typisierte Sprache ist, dass Werte in f# schwach typisiert.</span><span class="sxs-lookup"><span data-stu-id="409c1-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="409c1-108">F# ist eine statisch typisierte Sprache, d. h. leitet der Compiler einen genauen Typ für jedes Konstrukts während der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="409c1-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="409c1-109">Wenn es keine ausreichenden Informationen für den Compiler sind an, die Typen von jedes Konstrukts hergeleitet werden, müssen Sie zusätzliche Typinformationen durch Hinzufügen von Anmerkungen zum expliziten Typ an einer beliebigen Stelle im Code in der Regel angeben.</span><span class="sxs-lookup"><span data-stu-id="409c1-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>


## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="409c1-110">Inferenz von Parameter- und Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="409c1-110">Inference of Parameter and Return Types</span></span>
<span data-ttu-id="409c1-111">In einer Parameterliste müssen Sie nicht den Typ jedes Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="409c1-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="409c1-112">Noch f# eine statisch typisierte Sprache ist und daher jeder Wert und einen Ausdruck verfügt über einen bestimmten Typ zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="409c1-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="409c1-113">Für diese Typen, die Sie nicht explizit angeben, leitet der Compiler den Typ auf Grundlage des Kontexts.</span><span class="sxs-lookup"><span data-stu-id="409c1-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="409c1-114">Wenn der Typ nicht anderweitig angegeben ist, wird er generisch sein abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="409c1-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="409c1-115">Wenn der Code einen Wert inkonsistent verwendet wird, ergibt sich keine einzelne abgeleitet so Typ, der alle Vorkommen eines Werts entspricht der Compiler einen Fehler meldet.</span><span class="sxs-lookup"><span data-stu-id="409c1-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="409c1-116">Der Rückgabetyp einer Funktion wird durch den Typ des letzten Ausdrucks in der Funktion bestimmt.</span><span class="sxs-lookup"><span data-stu-id="409c1-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="409c1-117">Beispielsweise in den folgenden Code, der Parametertypen `a` und `b` und der Rückgabetyp abgeleitet, werden `int` da das Literal `100` ist vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="409c1-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="409c1-118">Sie können den Typrückschluss beeinflussen, indem Sie die Literale ändern.</span><span class="sxs-lookup"><span data-stu-id="409c1-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="409c1-119">Wenn Sie stellen die `100` eine `uint32` durch das Suffix Anfügen `u`, die Typen von `a`, `b`, und der Rückgabewert abgeleitet werden `uint32`.</span><span class="sxs-lookup"><span data-stu-id="409c1-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="409c1-120">Sie können auch beeinflussen, Typrückschluss mithilfe anderer Konstrukte, die die Einschränkungen für den Typ, z. B. Funktionen und Methoden, die für die Arbeit mit nur einem bestimmten Typ implizieren.</span><span class="sxs-lookup"><span data-stu-id="409c1-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="409c1-121">Darüber hinaus können Sie explizite typanmerkungen Funktion oder Methode Parametern oder Variablen in Ausdrücken, anwenden wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="409c1-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="409c1-122">Fehler führen, wenn Konflikte zwischen verschiedenen Einschränkungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="409c1-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="409c1-123">Sie können den Rückgabewert einer Funktion auch explizit angeben, indem er einer typanmerkung Startwerte der Parameter.</span><span class="sxs-lookup"><span data-stu-id="409c1-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="409c1-124">Ein häufiges Szenario, in dem eine typanmerkung hilfreich, wenn ein Parameter ist, ist, wenn der Parameter ein Objekt ist, und Sie ein Element verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="409c1-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]
    
## <a name="automatic-generalization"></a><span data-ttu-id="409c1-125">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="409c1-125">Automatic Generalization</span></span>
<span data-ttu-id="409c1-126">Wenn Sie der Funktionscode nicht den Typ eines Parameters abhängig ist, betrachtet der Compiler Parameters generisch sein.</span><span class="sxs-lookup"><span data-stu-id="409c1-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="409c1-127">Hierbei spricht *automatische Verallgemeinerung*, und es kann eine leistungsstarke Hilfe beim Schreiben von generischem Code ohne die Komplexität erhöhen.</span><span class="sxs-lookup"><span data-stu-id="409c1-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="409c1-128">Zum Beispiel kombiniert die folgende Funktion zwei Parameter eines beliebigen Typs in ein Tupel.</span><span class="sxs-lookup"><span data-stu-id="409c1-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="409c1-129">Der Typ wird abgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="409c1-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="409c1-130">Zusätzliche Informationen</span><span class="sxs-lookup"><span data-stu-id="409c1-130">Additional Information</span></span>
<span data-ttu-id="409c1-131">Typrückschluss wird in der f#-Sprachspezifikation ausführlicher beschrieben.</span><span class="sxs-lookup"><span data-stu-id="409c1-131">Type inference is described in more detail in the F# Language Specification.</span></span>


## <a name="see-also"></a><span data-ttu-id="409c1-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="409c1-132">See Also</span></span>
[<span data-ttu-id="409c1-133">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="409c1-133">Automatic Generalization</span></span>](generics/automatic-generalization.md)
