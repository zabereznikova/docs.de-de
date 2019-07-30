---
title: 'Schleifen: for...to-Ausdruck'
description: Siehe How F# for... to-Ausdruck wird zum Durchlaufen einer Schleife über einen Wertebereich einer Schleifen Variablen verwendet.
ms.date: 05/16/2016
ms.openlocfilehash: 910c04aa4ea6b2c637dcad147347c1c317b5e0c0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626629"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="747a5-103">Schleifen: for...to-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="747a5-103">Loops: for...to Expression</span></span>

<span data-ttu-id="747a5-104">Der `for...to` Ausdruck wird zum Durchlaufen einer Schleife über einen Wertebereich einer Schleifen Variablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="747a5-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="747a5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="747a5-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="747a5-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="747a5-106">Remarks</span></span>

<span data-ttu-id="747a5-107">Der Typ des Bezeichners wird vom Typ der Ausdrücke zum *starten* und *Beenden* abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="747a5-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="747a5-108">Typen für diese Ausdrücke müssen 32-Bit-Ganzzahlen sein.</span><span class="sxs-lookup"><span data-stu-id="747a5-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="747a5-109">Obwohl es sich technisch gesehen `for...to` um einen Ausdruck handelt, ähnelt dies einer herkömmlichen Anweisung in einer imperativen Programmiersprache.</span><span class="sxs-lookup"><span data-stu-id="747a5-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="747a5-110">Der Rückgabetyp für den *Text Ausdruck* muss `unit`lauten.</span><span class="sxs-lookup"><span data-stu-id="747a5-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="747a5-111">In den folgenden Beispielen werden verschiedene Verwendungen `for...to` des-Ausdrucks veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="747a5-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="747a5-112">Der obige Code gibt Folgendes aus.</span><span class="sxs-lookup"><span data-stu-id="747a5-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="747a5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="747a5-113">See also</span></span>

- [<span data-ttu-id="747a5-114">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="747a5-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="747a5-115">Loops `for...in`Begriff</span><span class="sxs-lookup"><span data-stu-id="747a5-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="747a5-116">Loops `while...do`Begriff</span><span class="sxs-lookup"><span data-stu-id="747a5-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
