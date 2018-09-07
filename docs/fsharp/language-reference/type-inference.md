---
title: Typrückschluss (F#)
description: Erfahren Sie, wie der F#-Compiler die Typen von Werten, Variablen, Parameter und Rückgabewerte herleitet.
ms.date: 05/16/2016
ms.openlocfilehash: fd826ac48fb9a70aa6f4ff746599c11b7e21a02e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865695"
---
# <a name="type-inference"></a><span data-ttu-id="82751-103">Typableitung</span><span class="sxs-lookup"><span data-stu-id="82751-103">Type Inference</span></span>

<span data-ttu-id="82751-104">In diesem Thema wird beschrieben, wie der F#-Compiler die Typen von Werten, Variablen, Parameter und Rückgabewerte herleitet.</span><span class="sxs-lookup"><span data-stu-id="82751-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="82751-105">Im Allgemeinen den Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="82751-105">Type Inference in General</span></span>

<span data-ttu-id="82751-106">Das Konzept der Typrückschluss ist, dass Sie keine geben die Art der f#-Konstrukte, außer wenn der Compiler allerdings den Typ hergeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="82751-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="82751-107">Explizite Typinformationen auslassen bedeutet nicht, dass f# einer dynamisch typisierten Sprache ist oder des typisierten, dass die Werte in f# sind.</span><span class="sxs-lookup"><span data-stu-id="82751-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="82751-108">F# ist eine statisch typisierte Sprache, was bedeutet, dass der Compiler einen genauen Typ für jedes Konstrukt während der Kompilierung ableitet.</span><span class="sxs-lookup"><span data-stu-id="82751-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="82751-109">Wenn nicht genügend Informationen, damit der Compiler die Typen von jedes Konstrukts Herleiten vorhanden ist, müssen Sie zusätzliche Typinformationen in der Regel angeben, indem Sie explizite Typen an einer beliebigen Stelle im Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="82751-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>

## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="82751-110">Inferenz von Parameter- und Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="82751-110">Inference of Parameter and Return Types</span></span>

<span data-ttu-id="82751-111">In einer Parameterliste müssen Sie nicht den Typ jedes Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="82751-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="82751-112">Und noch f# ist eine statisch typisierte Sprache, und jeder Wert und der Ausdruck hat daher einen eindeutigen Typ zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="82751-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="82751-113">Für diese Typen, die Sie nicht explizit angeben, leitet der Compiler den Typ auf Grundlage des Kontexts.</span><span class="sxs-lookup"><span data-stu-id="82751-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="82751-114">Wenn der Typ nicht nichts anderes angegeben ist, wird es abgeleitet generisch sein.</span><span class="sxs-lookup"><span data-stu-id="82751-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="82751-115">Wenn der Code einen Wert nicht einheitlich verwendet, dass kein einzelner abgeleitet so Typ, der alle Vorkommen eines Werts, entspricht der Compiler einen Fehler meldet.</span><span class="sxs-lookup"><span data-stu-id="82751-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="82751-116">Der Rückgabetyp einer Funktion wird durch den Typ des letzten Ausdrucks in der Funktion bestimmt.</span><span class="sxs-lookup"><span data-stu-id="82751-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="82751-117">Beispielsweise in den folgenden Code, die Parametertypen `a` und `b` und der Rückgabetyp abgeleitet, werden `int` da das Literal `100` ist vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="82751-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="82751-118">Sie können den Typrückschluss beeinflussen, ändern Sie die Literale.</span><span class="sxs-lookup"><span data-stu-id="82751-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="82751-119">Wenn Sie ändern die `100` eine `uint32` durch Anfügen des Suffixes `u`, die Typen von `a`, `b`, und der zurückgegebene Wert abgeleitet werden `uint32`.</span><span class="sxs-lookup"><span data-stu-id="82751-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="82751-120">Sie können auch beeinflussen den Typrückschluss mit anderen Konstrukten, die die Einschränkungen für den Typ, z. B. Funktionen und Methoden, die Arbeit mit nur einem bestimmten Typ implizieren.</span><span class="sxs-lookup"><span data-stu-id="82751-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="82751-121">Außerdem können Sie explizite Typen Funktion oder Methode Parameter oder Variablen in Ausdrücken, gelten wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="82751-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="82751-122">Fehler führen, wenn Konflikte zwischen verschiedenen Einschränkungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="82751-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="82751-123">Sie können auch explizit den Rückgabewert einer Funktion angeben, durch die Bereitstellung einer typanmerkung schließlich die Parameter.</span><span class="sxs-lookup"><span data-stu-id="82751-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="82751-124">Ein häufiges Szenario, in denen eine typanmerkung für einen Parameter eignet, ist der Parameter ist ein Objekt, und Sie ein Element verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82751-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a><span data-ttu-id="82751-125">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="82751-125">Automatic Generalization</span></span>

<span data-ttu-id="82751-126">Ist der Funktionscode nicht abhängig von dem Typ eines Parameters, betrachtet der Compiler den Parameter, um generisch sein.</span><span class="sxs-lookup"><span data-stu-id="82751-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="82751-127">Dies wird als bezeichnet *automatische Verallgemeinerung*, und es kann sein, eine leistungsstarke Hilfe beim Schreiben von generischem Code ohne die Komplexität erhöhen.</span><span class="sxs-lookup"><span data-stu-id="82751-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="82751-128">Die folgende Funktion kombiniert beispielsweise zwei Parameter eines beliebigen Typs in ein Tupel.</span><span class="sxs-lookup"><span data-stu-id="82751-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="82751-129">Der Typ wird abgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="82751-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="82751-130">Zusätzliche Informationen</span><span class="sxs-lookup"><span data-stu-id="82751-130">Additional Information</span></span>

<span data-ttu-id="82751-131">Typrückschluss wird in der F#-Sprachspezifikation ausführlicher beschrieben.</span><span class="sxs-lookup"><span data-stu-id="82751-131">Type inference is described in more detail in the F# Language Specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="82751-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82751-132">See also</span></span>

- [<span data-ttu-id="82751-133">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="82751-133">Automatic Generalization</span></span>](generics/automatic-generalization.md)
