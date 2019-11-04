---
title: Unit-Typ
description: Erfahren Sie, F# wie der Typ "Unit" häufig verwendet wird, um den Speicherort zu speichern, an dem ein Wert für die Sprachsyntax erforderlich ist, wenn kein Wert erforderlich oder erwünscht ist.
ms.date: 05/16/2016
ms.openlocfilehash: a5960fb05af50486a78345d10a5ad913e65729e3
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424034"
---
# <a name="unit-type"></a><span data-ttu-id="232b0-103">Unit-Typ</span><span class="sxs-lookup"><span data-stu-id="232b0-103">Unit Type</span></span>

<span data-ttu-id="232b0-104">Der `unit` Typ ist ein Typ, der das Fehlen eines bestimmten Werts angibt. der `unit` Typ hat nur einen einzelnen Wert, der als Platzhalter fungiert, wenn kein anderer Wert vorhanden oder benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="232b0-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="232b0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="232b0-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="232b0-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="232b0-106">Remarks</span></span>

<span data-ttu-id="232b0-107">Jeder F# Ausdruck muss zu einem-Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="232b0-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="232b0-108">Für Ausdrücke, die keinen Wert generieren, der von Interesse ist, wird der Wert des Typs `unit` verwendet.</span><span class="sxs-lookup"><span data-stu-id="232b0-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="232b0-109">Der `unit` C# -Typ ähnelt dem `void`-Typ in Sprachen wie C++und.</span><span class="sxs-lookup"><span data-stu-id="232b0-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="232b0-110">Der `unit` Typ hat einen einzelnen Wert, und dieser Wert wird durch das Token `()`angegeben.</span><span class="sxs-lookup"><span data-stu-id="232b0-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="232b0-111">Der Wert des `unit` Typs wird häufig bei F# der Programmierung verwendet, um den Ort zu speichern, an dem ein Wert für die Sprachsyntax erforderlich ist, aber wenn kein Wert erforderlich oder erwünscht ist.</span><span class="sxs-lookup"><span data-stu-id="232b0-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="232b0-112">Ein Beispiel könnte der Rückgabewert einer `printf`-Funktion sein.</span><span class="sxs-lookup"><span data-stu-id="232b0-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="232b0-113">Da die wichtigen Aktionen des `printf` Vorgangs in der Funktion auftreten, muss die Funktion keinen tatsächlichen Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="232b0-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="232b0-114">Daher ist der Rückgabewert vom Typ `unit`.</span><span class="sxs-lookup"><span data-stu-id="232b0-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="232b0-115">Einige Konstrukte erwarten einen `unit` Wert.</span><span class="sxs-lookup"><span data-stu-id="232b0-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="232b0-116">Beispielsweise wird erwartet, dass eine `do` Bindung oder Code auf der obersten Ebene eines Moduls zu einem `unit` Wert ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="232b0-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="232b0-117">Der Compiler meldet eine Warnung, wenn eine `do` Bindung oder Code auf der obersten Ebene eines Moduls ein anderes Ergebnis als den `unit` Wert erzeugt, der nicht verwendet wird, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="232b0-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="232b0-118">Diese Warnung ist ein Merkmal der funktionalen Programmierung. Sie wird in anderen .NET-Programmiersprachen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="232b0-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="232b0-119">In einem rein funktionalen Programm, in dem Funktionen keine Nebeneffekte haben, ist der abschließende Rückgabewert das einzige Ergebnis eines Funktions Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="232b0-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="232b0-120">Wenn das Ergebnis ignoriert wird, ist es daher ein möglicher Programmierfehler.</span><span class="sxs-lookup"><span data-stu-id="232b0-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="232b0-121">Obwohl F# es sich nicht um eine rein funktionale Programmiersprache handelt, empfiehlt es sich, nach Möglichkeit den funktionalen Programmierstil zu befolgen.</span><span class="sxs-lookup"><span data-stu-id="232b0-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="232b0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="232b0-122">See also</span></span>

- [<span data-ttu-id="232b0-123">Christentum</span><span class="sxs-lookup"><span data-stu-id="232b0-123">Primitive</span></span>](basic-types.md)
- [<span data-ttu-id="232b0-124">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="232b0-124">F# Language Reference</span></span>](index.md)
