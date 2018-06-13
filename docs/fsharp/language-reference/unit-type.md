---
title: Unit-Typ (F#)
description: Erfahren Sie, wie der f#-Typ "Einheit" häufig verwendet wird, um den Ort zu speichern, in dem ein Wert von der Sprachsyntax erforderlich ist, wenn kein Wert erforderlich oder gewünscht ist.
ms.date: 05/16/2016
ms.openlocfilehash: fdd6b62f9d5c6d73407d5326c7d1f66d55780682
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564419"
---
# <a name="unit-type"></a><span data-ttu-id="c4887-103">Unit-Typ</span><span class="sxs-lookup"><span data-stu-id="c4887-103">Unit Type</span></span>

<span data-ttu-id="c4887-104">Die `unit` Typ ist ein Typ, der das Fehlen eines bestimmten Werts; gibt an, die `unit` Typ verfügt über einen einzelnen Wert, der als Platzhalter fungiert, wenn kein anderer Wert vorhanden ist oder benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c4887-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>


## <a name="syntax"></a><span data-ttu-id="c4887-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4887-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="c4887-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4887-106">Remarks</span></span>
<span data-ttu-id="c4887-107">Jeder f#-Ausdruck muss zu einem Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="c4887-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="c4887-108">Für Ausdrücke, die keinen Wert generieren, die von Interesse sind, den Wert des Typs `unit` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c4887-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="c4887-109">Die `unit` Typ ähnelt dem `void` Typ in Sprachen wie c# und C++.</span><span class="sxs-lookup"><span data-stu-id="c4887-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="c4887-110">Die `unit` Typ verfügt über einen einzelnen Wert und diesen Wert angegeben wird, von dem Token `()`.</span><span class="sxs-lookup"><span data-stu-id="c4887-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="c4887-111">Der Wert, der die `unit` Typ werden häufig in F#-Programmierung die Stelle halten, während ein Wert von der Sprachsyntax erforderlich ist, jedoch kein Wert erforderlich oder gewünscht ist.</span><span class="sxs-lookup"><span data-stu-id="c4887-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="c4887-112">Ein Beispiel handelt es sich möglicherweise um den Rückgabewert einer `printf` Funktion.</span><span class="sxs-lookup"><span data-stu-id="c4887-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="c4887-113">Da die wichtigen Aktionen von der `printf` Vorgang auftreten, in der Funktion die Funktion muss es sich nicht in einen tatsächlichen Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c4887-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="c4887-114">Aus diesem Grund ist der Rückgabewert vom Typ `unit`.</span><span class="sxs-lookup"><span data-stu-id="c4887-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="c4887-115">Einige Konstrukte erwarten einen `unit` Wert.</span><span class="sxs-lookup"><span data-stu-id="c4887-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="c4887-116">Z. B. eine `do` Bindung oder den Code auf der obersten Ebene eines Moduls muss ergeben eine `unit` Wert.</span><span class="sxs-lookup"><span data-stu-id="c4887-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="c4887-117">Meldet der Compiler eine Warnung, wenn eine `do` Bindung oder den Code auf der obersten Ebene eines Moduls erzeugt ein Ergebnis außer der `unit` -Wert, der nicht verwendet wird, wie im folgenden Beispiel gezeigt,.</span><span class="sxs-lookup"><span data-stu-id="c4887-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="c4887-118">Diese Warnung ist ein Merkmal der funktionalen Programmierung. Es wird nicht in anderen .NET-Programmiersprachen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c4887-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="c4887-119">In einem reinen funktionalen-Programm in die Funktionen keine keine Nebeneffekte aufweisen, ist der letzte Rückgabewert das einzige Ergebnis eines Funktionsaufrufs.</span><span class="sxs-lookup"><span data-stu-id="c4887-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="c4887-120">Wenn das Ergebnis ignoriert wird, ist es daher möglicherweise ein Programmierfehler.</span><span class="sxs-lookup"><span data-stu-id="c4887-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="c4887-121">F# ist, zwar keiner reinen funktionalen Programmiersprache Ihrer Wahl ist es empfiehlt sich, führen die funktionalen Programmierstils, wann immer möglich.</span><span class="sxs-lookup"><span data-stu-id="c4887-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4887-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4887-122">See Also</span></span>
[<span data-ttu-id="c4887-123">Primitive</span><span class="sxs-lookup"><span data-stu-id="c4887-123">Primitive</span></span>](primitive-types.md)

[<span data-ttu-id="c4887-124">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="c4887-124">F# Language Reference</span></span>](index.md)
