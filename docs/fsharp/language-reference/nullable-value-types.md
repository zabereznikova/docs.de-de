---
title: Auf NULL festlegbare Werttypen
description: 'Erfahren Sie, wie Sie Werte zulässt-Werttypen verwenden können, eine Möglichkeit, einen Werttyp darzustellen, der auch NULL sein kann, in F #.'
ms.date: 11/19/2020
ms.openlocfilehash: da0cd85bd651db81ba98c02a9db31d92dc52a8c6
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740429"
---
# <a name="nullable-value-types"></a><span data-ttu-id="cc7c9-103">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="cc7c9-103">Nullable value types</span></span>

<span data-ttu-id="cc7c9-104">Ein auf NULL festleg _barer Werttyp_ `Nullable<'T>` stellt einen beliebigen Strukturtyp dar, der auch sein könnte [struct](structures.md) `null`</span><span class="sxs-lookup"><span data-stu-id="cc7c9-104">A _nullable value type_ `Nullable<'T>` represents any [struct](structures.md) type that could also be `null`.</span></span> <span data-ttu-id="cc7c9-105">Dies ist hilfreich, wenn Sie mit Bibliotheken und Komponenten interagieren, die diese Arten von Typen, wie z. b. ganze Zahlen, mit einem `null` Wert aus Effizienzgründen darstellen können.</span><span class="sxs-lookup"><span data-stu-id="cc7c9-105">This is helpful when interacting with libraries and components that may choose to represent these kinds of types, like integers, with a `null` value for efficiency reasons.</span></span> <span data-ttu-id="cc7c9-106">Der zugrunde liegende Typ, der dieses Konstrukt unterstützt, ist <xref:System.Nullable%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="cc7c9-106">The underlying type that backs this construct is <xref:System.Nullable%601?displayProperty=nameWithType>.</span></span>

## <a name="syntax"></a><span data-ttu-id="cc7c9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc7c9-107">Syntax</span></span>

```fsharp
Nullable<'T>
Nullable value
```

## <a name="declare-and-assign-with-values"></a><span data-ttu-id="cc7c9-108">Deklarieren und mit Werten zuweisen</span><span class="sxs-lookup"><span data-stu-id="cc7c9-108">Declare and assign with values</span></span>

<span data-ttu-id="cc7c9-109">Das Deklarieren eines auf NULL festleg baren Werttyps ist wie das Deklarieren eines beliebigen Wrapper ähnlichen Typs in F #:</span><span class="sxs-lookup"><span data-stu-id="cc7c9-109">Declaring a nullable value type is just like declaring any wrapper-like type in F#:</span></span>

```fsharp
open System

let x = 12
let nullableX = Nullable<int> x
```

<span data-ttu-id="cc7c9-110">Sie können auch den generischen Typparameter entfernen und den Typrückschluss zulassen, um ihn aufzulösen:</span><span class="sxs-lookup"><span data-stu-id="cc7c9-110">You can also elide the generic type parameter and allow type inference to resolve it:</span></span>

```fsharp
open System

let x = 12
let nullableX = Nullable x
```

<span data-ttu-id="cc7c9-111">Wenn Sie einem Werttyp, der NULL-Werte zulässt, zuweisen möchten, müssen Sie auch explizit sein.</span><span class="sxs-lookup"><span data-stu-id="cc7c9-111">To assign to a nullable value type, you'll need to also be explicit.</span></span> <span data-ttu-id="cc7c9-112">Es gibt keine implizite Konvertierung für F #-definierte Werttypen, die NULL-Werte zulassen:</span><span class="sxs-lookup"><span data-stu-id="cc7c9-112">There is no implicit conversion for F#-defined nullable value types:</span></span>

```fsharp
open System

let mutable x = Nullable 12
x <- Nullable 13
```

## <a name="assign-null"></a><span data-ttu-id="cc7c9-113">NULL zuweisen</span><span class="sxs-lookup"><span data-stu-id="cc7c9-113">Assign null</span></span>

<span data-ttu-id="cc7c9-114">Sie können `null` einem Werttyp, der NULL-Werte zulässt, nicht direkt zuweisen</span><span class="sxs-lookup"><span data-stu-id="cc7c9-114">You cannot directly assign `null` to a nullable value type.</span></span> <span data-ttu-id="cc7c9-115">Verwenden Sie `Nullable()` stattdessen:</span><span class="sxs-lookup"><span data-stu-id="cc7c9-115">Use `Nullable()` instead:</span></span>

```fsharp
let mutable a = Nullable 42
a <- Nullable()
```

<span data-ttu-id="cc7c9-116">Der Grund hierfür ist, dass `Nullable<'T>` nicht über `null` einen geeigneten Wert verfügt.</span><span class="sxs-lookup"><span data-stu-id="cc7c9-116">This is because `Nullable<'T>` does not have `null` as a proper value.</span></span>

## <a name="pass-and-assign-to-members"></a><span data-ttu-id="cc7c9-117">Übergeben und zuweisen an Member</span><span class="sxs-lookup"><span data-stu-id="cc7c9-117">Pass and assign to members</span></span>

<span data-ttu-id="cc7c9-118">Ein wichtiger Unterschied zwischen der Arbeit mit Membern und F #-Werten besteht darin, dass Werte zulässt-Werttypen implizit abgeleitet werden können, wenn Sie mit Membern arbeiten.</span><span class="sxs-lookup"><span data-stu-id="cc7c9-118">A key difference between working with members and F# values is that nullable value types can be implicitly inferred when you're working with members.</span></span> <span data-ttu-id="cc7c9-119">Beachten Sie die folgende Methode, die einen Werte zulässt-Werttyp als Eingabe annimmt:</span><span class="sxs-lookup"><span data-stu-id="cc7c9-119">Consider the folling method that takes a nullable value type as input:</span></span>

```fsharp
type C() =
    member _.M(x: Nullable<int>) = x.HasValue
    member val NVT = Nullable 12 with get, set

let c = C()
c.M(12)
c.NVT <- 12
```

<span data-ttu-id="cc7c9-120">Im vorherigen Beispiel können Sie `12` an die-Methode übergeben `M` .</span><span class="sxs-lookup"><span data-stu-id="cc7c9-120">In the previous example, you can pass `12` to the method `M`.</span></span> <span data-ttu-id="cc7c9-121">Sie können auch `12` der Auto-Eigenschaft zuweisen `NVT` .</span><span class="sxs-lookup"><span data-stu-id="cc7c9-121">You can also assign `12` to the auto property `NVT`.</span></span> <span data-ttu-id="cc7c9-122">Der F #-Compiler konvertiert einen oder dieselbe Zuweisung implizit, wenn der Zieltyp mit der Eingabe übereinstimmt, wenn die Eingabe als nulllabel-Werttyp erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cc7c9-122">The F# compiler will implicitly convert a call or assignment like this when the target type matches the input, if the input can be constructed as a nullabel value type.</span></span>

## <a name="examine-a-nullable-value-type-instance"></a><span data-ttu-id="cc7c9-123">Überprüfen einer Instanz, die NULL-Werte zulässt</span><span class="sxs-lookup"><span data-stu-id="cc7c9-123">Examine a nullable value type instance</span></span>

<span data-ttu-id="cc7c9-124">Anders als bei [Optionen](options.md), bei denen es sich um ein generalisiertes Konstrukt zur Darstellung eines möglichen Werts handelt, werden Werte zulässt-Werttypen nicht mit Musterabgleich verwendet</span><span class="sxs-lookup"><span data-stu-id="cc7c9-124">Unlike [Options](options.md), which are a generalized construct for representing a possible value, nullable value types are not used with pattern matching.</span></span> <span data-ttu-id="cc7c9-125">Stattdessen müssen Sie einen [`if`](conditional-expressions-if-then-else.md) Ausdruck verwenden und die-Eigenschaft überprüfen `HasValue` .</span><span class="sxs-lookup"><span data-stu-id="cc7c9-125">Instead, you need to use an [`if`](conditional-expressions-if-then-else.md) expression and check the `HasValue` property.</span></span>

<span data-ttu-id="cc7c9-126">Um den zugrunde liegenden Wert zu erhalten, verwenden Sie die- `Value` Eigenschaft nach einer `HasValue` Überprüfung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cc7c9-126">To get the underlying value, use the `Value` property after a `HasValue` check, like so:</span></span>

```fsharp
open System

let a = Nullable 42

if a.HasValue then
    printfn $"{a} is {a.Value}"
else
    printfn $"{a} has no value."
```

## <a name="nullable-operators"></a><span data-ttu-id="cc7c9-127">NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="cc7c9-127">Nullable operators</span></span>

<span data-ttu-id="cc7c9-128">Vorgänge für Werttypen, die NULL-Werte zulassen, wie z. b. Arithmetik oder Vergleiche, können die Verwendung von [NULL-Werten](symbol-and-operator-reference/nullable-operators.md)zulassen</span><span class="sxs-lookup"><span data-stu-id="cc7c9-128">Operations on nullable value types, such as arithmetic or comparison, can require the use of [nullable operators](symbol-and-operator-reference/nullable-operators.md).</span></span>

<span data-ttu-id="cc7c9-129">Mithilfe von Konvertierungs Operatoren aus dem-Namespace können Sie von einem Werte zulässt-Werttyp in einen anderen konvertieren `FSharp.Linq` :</span><span class="sxs-lookup"><span data-stu-id="cc7c9-129">You can convert from one nullable value type to another using conversion operators from the `FSharp.Linq` namespace:</span></span>

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt
```

<span data-ttu-id="cc7c9-130">Sie können auch einen geeigneten Operator, der keine NULL-Werte zulässt, verwenden, um einen primitiven Typ zu konvertieren, der eine Ausnahme auslöst, wenn er über keinen Wert verfügt:</span><span class="sxs-lookup"><span data-stu-id="cc7c9-130">You can also use an appropriate non-nullable operator to convert to a primitive type, risking an exception if it has no value:</span></span>

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

printfn $"value is %f{float nullableFloat}"
```

<span data-ttu-id="cc7c9-131">Sie können auch die Operatoren, die NULL-Werte zulassen, zum Überprüfen von `HasValue` und verwenden `Value` :</span><span class="sxs-lookup"><span data-stu-id="cc7c9-131">You can also use nullable operators as a short-hand for checking `HasValue` and `Value`:</span></span>

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

let isBigger = nullableFloat ?> 1.0
let isBiggerLongForm = nullableFloat.HasValue && nullableFloat.Value > 1.0
```

<span data-ttu-id="cc7c9-132">Der `?>` Vergleich überprüft, ob die linke Seite NULL-Werte zulässt und nur erfolgreich ist, wenn Sie über einen Wert verfügt.</span><span class="sxs-lookup"><span data-stu-id="cc7c9-132">The `?>` comparison checks if the left-hand side is nullable and only succeeds if it has a value.</span></span> <span data-ttu-id="cc7c9-133">Dies entspricht der folgenden Zeile.</span><span class="sxs-lookup"><span data-stu-id="cc7c9-133">It is equivalent to the line that follows it.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc7c9-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc7c9-134">See also</span></span>

- [<span data-ttu-id="cc7c9-135">Strukturen</span><span class="sxs-lookup"><span data-stu-id="cc7c9-135">Structures</span></span>](structures.md)
- [<span data-ttu-id="cc7c9-136">F #-Optionen</span><span class="sxs-lookup"><span data-stu-id="cc7c9-136">F# Options</span></span>](options.md)
