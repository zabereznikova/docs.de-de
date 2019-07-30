---
title: Typableitung
description: Erfahren Sie, F# wie der Compiler die Typen von Werten, Variablen, Parametern und Rückgabe Werten leitet.
ms.date: 05/16/2016
ms.openlocfilehash: 4b18c1a67a8b7ddadb4fb334ea4736e9fd29feb0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630181"
---
# <a name="type-inference"></a><span data-ttu-id="ba27b-103">Typableitung</span><span class="sxs-lookup"><span data-stu-id="ba27b-103">Type Inference</span></span>

<span data-ttu-id="ba27b-104">In diesem Thema wird beschrieben F# , wie der Compiler die Typen von Werten, Variablen, Parametern und Rückgabe Werten leitet.</span><span class="sxs-lookup"><span data-stu-id="ba27b-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="ba27b-105">Typrückschluss im allgemeinen</span><span class="sxs-lookup"><span data-stu-id="ba27b-105">Type Inference in General</span></span>

<span data-ttu-id="ba27b-106">Das Konzept der Typrückschluss ist, dass Sie keine geben die Art der F#-Konstrukte, außer wenn der Compiler allerdings den Typ hergeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ba27b-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="ba27b-107">Explizite Typinformationen auslassen bedeutet nicht, dass F# einer dynamisch typisierten Sprache ist oder des typisierten, dass die Werte in F# sind.</span><span class="sxs-lookup"><span data-stu-id="ba27b-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="ba27b-108">F#ist eine statisch typisierte Sprache. Dies bedeutet, dass der Compiler während der Kompilierung einen exakten Typ für jedes Konstrukt herleitet.</span><span class="sxs-lookup"><span data-stu-id="ba27b-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="ba27b-109">Wenn nicht genügend Informationen vorhanden sind, damit der Compiler die Typen der einzelnen Konstrukte ableiten kann, müssen zusätzliche Typinformationen bereitgestellt werden, in der Regel durch das Hinzufügen von expliziten Typanmerkungen an einer beliebigen Stelle im Code.</span><span class="sxs-lookup"><span data-stu-id="ba27b-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>

## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="ba27b-110">Ableiten von Parameter-und Rückgabe Typen</span><span class="sxs-lookup"><span data-stu-id="ba27b-110">Inference of Parameter and Return Types</span></span>

<span data-ttu-id="ba27b-111">In einer Parameterliste müssen Sie nicht den Typ jedes Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="ba27b-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="ba27b-112">Und noch F# ist eine statisch typisierte Sprache, und jeder Wert und der Ausdruck hat daher einen eindeutigen Typ zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="ba27b-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="ba27b-113">Für die Typen, die Sie nicht explizit angeben, leitet der Compiler den Typ auf Grundlage des Kontexts ab.</span><span class="sxs-lookup"><span data-stu-id="ba27b-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="ba27b-114">Wenn der Typ nicht anderweitig angegeben ist, wird er als generisch abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="ba27b-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="ba27b-115">Wenn der Code einen Wert inkonsistent verwendet, gibt der Compiler einen Fehler aus, wenn es keinen einzelnen, abgelegten Typ gibt, der alle Verwendungen eines Werts erfüllt.</span><span class="sxs-lookup"><span data-stu-id="ba27b-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="ba27b-116">Der Rückgabetyp einer Funktion wird durch den Typ des letzten Ausdrucks in der Funktion bestimmt.</span><span class="sxs-lookup"><span data-stu-id="ba27b-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="ba27b-117">Im folgenden Code werden z. b. die Parametertypen `a` und `b` und der Rückgabetyp als abgeleitet `int` , weil der Literaltyp `100` `int`ist.</span><span class="sxs-lookup"><span data-stu-id="ba27b-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="ba27b-118">Sie können den Typrückschluss beeinflussen, indem Sie die Literale ändern.</span><span class="sxs-lookup"><span data-stu-id="ba27b-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="ba27b-119">`100` Wenn Sie das `uint32` -Suffix `u`durch Anhängen des Suffixes durch Anhängen, werden `a`die `b`Typen von `uint32`, und der Rückgabewert als abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="ba27b-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="ba27b-120">Sie können den Typrückschluss auch beeinflussen, indem Sie andere Konstrukte verwenden, die Einschränkungen für den Typ implizieren, wie z. b. Funktionen und Methoden, die nur mit einem bestimmten Typ funktionieren.</span><span class="sxs-lookup"><span data-stu-id="ba27b-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="ba27b-121">Außerdem können Sie explizite Typanmerkungen auf Funktions-oder Methoden Parameter oder auf Variablen in Ausdrücken anwenden, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba27b-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="ba27b-122">Fehler treten auf, wenn Konflikte zwischen verschiedenen Einschränkungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="ba27b-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="ba27b-123">Sie können den Rückgabewert einer Funktion auch explizit angeben, indem Sie eine Typanmerkung nach allen Parametern bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba27b-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="ba27b-124">Ein gängiger Fall, bei dem eine Typanmerkung für einen Parameter nützlich ist, ist, wenn der Parameter ein Objekttyp ist und Sie einen Member verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ba27b-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a><span data-ttu-id="ba27b-125">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="ba27b-125">Automatic Generalization</span></span>

<span data-ttu-id="ba27b-126">Wenn der Funktionscode nicht vom Typ eines Parameters abhängt, betrachtet der Compiler den Parameter als generisch.</span><span class="sxs-lookup"><span data-stu-id="ba27b-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="ba27b-127">Dies wird als *Automatische Generalisierung*bezeichnet und kann eine leistungsstarke Hilfe beim Schreiben von generischem Code sein, ohne die Komplexität zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="ba27b-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="ba27b-128">Die folgende Funktion kombiniert z. b. zwei Parameter eines beliebigen Typs in einem Tupel.</span><span class="sxs-lookup"><span data-stu-id="ba27b-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="ba27b-129">Der Typ wird als</span><span class="sxs-lookup"><span data-stu-id="ba27b-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="ba27b-130">Zusätzliche Informationen</span><span class="sxs-lookup"><span data-stu-id="ba27b-130">Additional Information</span></span>

<span data-ttu-id="ba27b-131">Der Typrückschluss wird in der F# -Sprachspezifikation ausführlicher beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba27b-131">Type inference is described in more detail in the F# Language Specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba27b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba27b-132">See also</span></span>

- [<span data-ttu-id="ba27b-133">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="ba27b-133">Automatic Generalization</span></span>](./generics/automatic-generalization.md)
