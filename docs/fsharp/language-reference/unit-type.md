---
title: Unit-Typ (F#)
description: "Erfahren Sie, wie der f#-Typ \"Einheit\" häufig verwendet wird, um den Ort zu speichern, in dem ein Wert von der Sprachsyntax erforderlich ist, wenn kein Wert erforderlich oder gewünscht ist."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: eabbb6d7-80f3-4fa5-80b4-0f48982466a7
ms.openlocfilehash: 60ac08c0e3f8380a8f9dec7a083ede93c68bb0e8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="unit-type"></a><span data-ttu-id="c5e71-104">Unit-Typ</span><span class="sxs-lookup"><span data-stu-id="c5e71-104">Unit Type</span></span>

<span data-ttu-id="c5e71-105">Die `unit` Typ ist ein Typ, der das Fehlen eines bestimmten Werts; gibt an, die `unit` Typ verfügt über einen einzelnen Wert, der als Platzhalter fungiert, wenn kein anderer Wert vorhanden ist oder benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c5e71-105">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>


## <a name="syntax"></a><span data-ttu-id="c5e71-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5e71-106">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="c5e71-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5e71-107">Remarks</span></span>
<span data-ttu-id="c5e71-108">Jeder f#-Ausdruck muss zu einem Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="c5e71-108">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="c5e71-109">Für Ausdrücke, die keinen Wert generieren, die von Interesse sind, den Wert des Typs `unit` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c5e71-109">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="c5e71-110">Die `unit` Typ ähnelt dem `void` Typ in Sprachen wie c# und C++.</span><span class="sxs-lookup"><span data-stu-id="c5e71-110">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="c5e71-111">Die `unit` Typ verfügt über einen einzelnen Wert und diesen Wert angegeben wird, von dem Token `()`.</span><span class="sxs-lookup"><span data-stu-id="c5e71-111">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="c5e71-112">Der Wert, der die `unit` Typ werden häufig in F#-Programmierung die Stelle halten, während ein Wert von der Sprachsyntax erforderlich ist, jedoch kein Wert erforderlich oder gewünscht ist.</span><span class="sxs-lookup"><span data-stu-id="c5e71-112">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="c5e71-113">Ein Beispiel handelt es sich möglicherweise um den Rückgabewert einer `printf` Funktion.</span><span class="sxs-lookup"><span data-stu-id="c5e71-113">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="c5e71-114">Da die wichtigen Aktionen von der `printf` Vorgang auftreten, in der Funktion die Funktion muss es sich nicht in einen tatsächlichen Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c5e71-114">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="c5e71-115">Aus diesem Grund ist der Rückgabewert vom Typ `unit`.</span><span class="sxs-lookup"><span data-stu-id="c5e71-115">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="c5e71-116">Einige Konstrukte erwarten einen `unit` Wert.</span><span class="sxs-lookup"><span data-stu-id="c5e71-116">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="c5e71-117">Z. B. eine `do` Bindung oder den Code auf der obersten Ebene eines Moduls muss ergeben eine `unit` Wert.</span><span class="sxs-lookup"><span data-stu-id="c5e71-117">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="c5e71-118">Meldet der Compiler eine Warnung, wenn eine `do` Bindung oder den Code auf der obersten Ebene eines Moduls erzeugt ein Ergebnis außer der `unit` -Wert, der nicht verwendet wird, wie im folgenden Beispiel gezeigt,.</span><span class="sxs-lookup"><span data-stu-id="c5e71-118">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="c5e71-119">Diese Warnung ist ein Merkmal der funktionalen Programmierung. Es wird nicht in anderen .NET-Programmiersprachen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5e71-119">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="c5e71-120">In einem reinen funktionalen-Programm in die Funktionen keine keine Nebeneffekte aufweisen, ist der letzte Rückgabewert das einzige Ergebnis eines Funktionsaufrufs.</span><span class="sxs-lookup"><span data-stu-id="c5e71-120">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="c5e71-121">Wenn das Ergebnis ignoriert wird, ist es daher möglicherweise ein Programmierfehler.</span><span class="sxs-lookup"><span data-stu-id="c5e71-121">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="c5e71-122">F# ist, zwar keiner reinen funktionalen Programmiersprache Ihrer Wahl ist es empfiehlt sich, führen die funktionalen Programmierstils, wann immer möglich.</span><span class="sxs-lookup"><span data-stu-id="c5e71-122">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5e71-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5e71-123">See Also</span></span>
[<span data-ttu-id="c5e71-124">Primitive</span><span class="sxs-lookup"><span data-stu-id="c5e71-124">Primitive</span></span>](primitive-types.md)

[<span data-ttu-id="c5e71-125">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="c5e71-125">F# Language Reference</span></span>](index.md)
