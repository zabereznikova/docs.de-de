---
title: Unit-Typ (F#)
description: Erfahren Sie, wie der F#-Typ "Unit" häufig verwendet wird, um die Stelle zu speichern, in dem ein Wert durch die Syntax der erforderlich ist, wenn kein Wert erforderlich oder gewünscht ist.
ms.date: 05/16/2016
ms.openlocfilehash: c3dfa5f63c25a1e8abc0f75b905c129b311479af
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "44204655"
---
# <a name="unit-type"></a><span data-ttu-id="4ab7c-103">Unit-Typ</span><span class="sxs-lookup"><span data-stu-id="4ab7c-103">Unit Type</span></span>

<span data-ttu-id="4ab7c-104">Die `unit` Typ ist ein Typ, der das Fehlen eines bestimmten Werts; gibt an, die `unit` Typ verfügt über nur einen einzelnen Wert, der als Platzhalter fungiert, wenn kein anderer Wert vorhanden oder erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="4ab7c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ab7c-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="4ab7c-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4ab7c-106">Remarks</span></span>

<span data-ttu-id="4ab7c-107">Alle F#-Ausdruck muss zu einem Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="4ab7c-108">Für Ausdrücke, die keinen Wert generieren, die von Interesse sind, wird der Wert des Typs `unit` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="4ab7c-109">Die `unit` Typ ähnelt der `void` Typ in Sprachen wie c# und C++.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="4ab7c-110">Die `unit` Typ verfügt über einen einzelnen Wert und diesen Wert angegeben wird, durch das Token `()`.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="4ab7c-111">Der Wert des der `unit` wird häufig in F#-Programmierung, um die Stelle zu speichern, ein Wert von der Sprachsyntax erforderlich ist, aber wenn kein Wert erforderlich oder gewünscht wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="4ab7c-112">Ein Beispiel handelt es sich möglicherweise um den Rückgabewert einer `printf` Funktion.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="4ab7c-113">Da die wichtigen Aktionen von der `printf` Vorgang auftreten, in der Funktion, die Funktion muss nicht unbedingt einen tatsächlichen Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="4ab7c-114">Aus diesem Grund der Rückgabewert ist vom Typ `unit`.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="4ab7c-115">Einige Konstrukte erwarten eine `unit` Wert.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="4ab7c-116">Z. B. eine `do` -Bindung oder Code auf der obersten Ebene eines Moduls wird erwartet, ergibt eine `unit` Wert.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="4ab7c-117">Der Compiler meldet eine Warnung bei eine `do` Bindung oder den Code auf der obersten Ebene eines Moduls, erzeugt ein Ergebnis außer der `unit` -Wert, der nicht verwendet wird, wie im folgenden Beispiel gezeigt,.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="4ab7c-118">Diese Warnung ist ein Merkmal der funktionalen Programmierung. Es wird nicht in anderen .NET-Programmiersprachen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="4ab7c-119">In einem rein funktionaler-Programm in der Funktionen aller möglichen Nebeneffekte, keine ist der letzte zurückgegebene Wert das einzige Ergebnis eines Funktionsaufrufs.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="4ab7c-120">Wenn das Ergebnis ignoriert wird, ist es daher möglicherweise ein Programmierfehler.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="4ab7c-121">F# ist, zwar keine rein funktionale Programmiersprache ist es sich bewährt, führen die funktionalen Programmierstils, wann immer möglich.</span><span class="sxs-lookup"><span data-stu-id="4ab7c-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ab7c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ab7c-122">See also</span></span>

- [<span data-ttu-id="4ab7c-123">Primitive</span><span class="sxs-lookup"><span data-stu-id="4ab7c-123">Primitive</span></span>](primitive-types.md)
- [<span data-ttu-id="4ab7c-124">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="4ab7c-124">F# Language Reference</span></span>](index.md)
