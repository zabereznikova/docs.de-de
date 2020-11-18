---
title: Interpolierte Zeichenfolgen
description: 'Erfahren Sie mehr über interpoliert Zeichen folgen, eine spezielle Form von Zeichen folgen, die es Ihnen ermöglicht, F #-Ausdrücke direkt in Sie einzubetten.'
ms.date: 11/12/2020
ms.openlocfilehash: 8c552b44cea7d6c51ec333b6bdd4d407c6f10da7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829686"
---
# <a name="interpolated-strings"></a><span data-ttu-id="e5a75-103">Interpolierte Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="e5a75-103">Interpolated strings</span></span>

<span data-ttu-id="e5a75-104">Interpoliert Zeichen folgen [sind Zeichen](strings.md) folgen, die es Ihnen ermöglichen, F #-Ausdrücke in Sie einzubetten.</span><span class="sxs-lookup"><span data-stu-id="e5a75-104">Interpolated strings are [strings](strings.md) that allow you to embed F# expressions into them.</span></span> <span data-ttu-id="e5a75-105">Sie sind in einer Vielzahl von Szenarien hilfreich, in denen sich der Wert einer Zeichenfolge basierend auf dem Ergebnis eines Werts oder Ausdrucks ändern kann.</span><span class="sxs-lookup"><span data-stu-id="e5a75-105">They are helpful in a wide range of scenarios where the value of a string may change based on the result of a value or expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="e5a75-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5a75-106">Syntax</span></span>

```fsharp
$"string-text {expr}"
$"string-text %format-specifier{expr}"
$"""string-text {"embedded string literal"}"""
```

## <a name="remarks"></a><span data-ttu-id="e5a75-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5a75-107">Remarks</span></span>

<span data-ttu-id="e5a75-108">Interinterpolierte Zeichen folgen ermöglichen das Schreiben von Code in "Holes" innerhalb eines Zeichenfolgenliterals.</span><span class="sxs-lookup"><span data-stu-id="e5a75-108">Interpolated strings let you write code in "holes" inside of a string literal.</span></span> <span data-ttu-id="e5a75-109">Im Folgenden finden Sie ein einfaches Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e5a75-109">Here's a basic example:</span></span>

```fsharp
let name = "Phillip"
let age = 30
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

<span data-ttu-id="e5a75-110">Der Inhalt zwischen den einzelnen `{}` Klammern kann ein beliebiger F #-Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="e5a75-110">The contents in between each `{}` brace pair can be any F# expression.</span></span>

<span data-ttu-id="e5a75-111">Wenn Sie ein Klammer Paar mit Escapezeichen versehen möchten `{}` , schreiben Sie zwei von Ihnen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e5a75-111">To escape a `{}` brace pair, write two of them like so:</span></span>

```fsharp
let str = $"A pair of braces: {{}}"
// "A pair of braces: {}"
```

## <a name="typed-interpolated-strings"></a><span data-ttu-id="e5a75-112">Typisierte interpoliert Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="e5a75-112">Typed interpolated strings</span></span>

<span data-ttu-id="e5a75-113">Interinterpolierte Zeichen folgen können auch F #-Format Bearbeiter aufweisen, um Typsicherheit zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e5a75-113">Interpolated strings can also have F# format specifiers to enforce type safety.</span></span>

```fsharp
let name = "Phillip"
let age = 30

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

<span data-ttu-id="e5a75-114">Im vorherigen Beispiel übergibt der Code versehentlich den `age` Wert, wobei den Wert `name` hat und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="e5a75-114">In the previous example, the code mistakenly passes the `age` value where `name` should be, and vice/versa.</span></span> <span data-ttu-id="e5a75-115">Da die interinterpolierten Zeichen folgen Formatspezifizierer verwenden, ist dies ein Kompilierungsfehler anstelle eines geringfügigen Lauf Zeit Fehlers.</span><span class="sxs-lookup"><span data-stu-id="e5a75-115">Because the interpolated strings use format specifiers, this is a compile error instead of a subtle runtime bug.</span></span>

<span data-ttu-id="e5a75-116">Alle Formatspezifizierer, die in der [Klartext-Formatierung](plaintext-formatting.md) abgedeckt werden, sind innerhalb einer interpoliert Zeichenfolge gültig.</span><span class="sxs-lookup"><span data-stu-id="e5a75-116">All format specifiers covered in [plaintext formatting](plaintext-formatting.md) are valid inside of an interpolated string.</span></span>

## <a name="verbatim-interpolated-strings"></a><span data-ttu-id="e5a75-117">Wörtliche interinterpolierte Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="e5a75-117">Verbatim interpolated strings</span></span>

<span data-ttu-id="e5a75-118">F # unterstützt wörtliche interpoliert Zeichen folgen mit dreifachen Anführungszeichen, sodass Sie Zeichen folgen Literale einbetten können.</span><span class="sxs-lookup"><span data-stu-id="e5a75-118">F# supports verbatim interpolated strings with triple quotes so that you can embed string literals.</span></span>

```fsharp
let age = 30

printfn $"""Name: {"Phillip"}, Age: %d{age}"""
```

## <a name="aligning-expressions-in-interpolated-strings"></a><span data-ttu-id="e5a75-119">Ausrichten von Ausdrücken in interpoliert-Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="e5a75-119">Aligning expressions in interpolated strings</span></span>

<span data-ttu-id="e5a75-120">Sie können Ausdrücke in interinterpolierten Zeichen folgen mit linksbündig ausrichten oder mit `|` der Angabe, wie viele Leerzeichen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e5a75-120">You can left-align or right-align expressions inside interpolated strings with `|` and a specification of how many spaces.</span></span> <span data-ttu-id="e5a75-121">Mit der folgenden interinterierten Zeichenfolge werden die linken und rechten Ausdrücke Links und rechts um sieben Leerzeichen ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="e5a75-121">The following interpolated string aligns the left and right expressions to the left and right, respectively, by seven spaces.</span></span>

```fsharp
printfn $"""|{"Left",-7}|{"Right",7}|"""
// |Left   |  Right|
```

## <a name="interpolated-strings-and-formattablestring-formatting"></a><span data-ttu-id="e5a75-122">Interpoliert Zeichen folgen und `FormattableString` Formatierung</span><span class="sxs-lookup"><span data-stu-id="e5a75-122">Interpolated strings and `FormattableString` formatting</span></span>

<span data-ttu-id="e5a75-123">Sie können auch die Formatierung anwenden, die den Regeln für folgt <xref:System.FormattableString> :</span><span class="sxs-lookup"><span data-stu-id="e5a75-123">You can also apply formatting that adheres to the rules for <xref:System.FormattableString>:</span></span>

```fsharp
let speedOfLight = 299792.458
printfn $"The speed of light is {speedOfLight:N3} km/s."
// "The speed of light is 299,792.458 km/s."
```

<span data-ttu-id="e5a75-124">Außerdem kann eine interinterpolierte Zeichenfolge auch als <xref:System.FormattableString> über eine Typanmerkung als überprüfte Typ markiert werden:</span><span class="sxs-lookup"><span data-stu-id="e5a75-124">Additionally, an interpolated string can also be type checked as a <xref:System.FormattableString> via a type annotation:</span></span>

```fsharp
let frmtStr = $"The speed of light is {speedOfLight:N3} km/s." : FormattableString
// Type: FormattableString
// The speed of light is 299,792.458 km/s.
```

<span data-ttu-id="e5a75-125">Beachten Sie, dass sich die Typanmerkung auf dem interinterierten Zeichen folgen Ausdruck selbst befinden muss.</span><span class="sxs-lookup"><span data-stu-id="e5a75-125">Note that the type annotation must be on the interpolated string expression itself.</span></span> <span data-ttu-id="e5a75-126">F # konvertiert eine interinterpolierte Zeichenfolge nicht implizit in eine <xref:System.FormattableString> .</span><span class="sxs-lookup"><span data-stu-id="e5a75-126">F# does not implicitly convert an interpolated string into a <xref:System.FormattableString>.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5a75-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5a75-127">See also</span></span>

* [<span data-ttu-id="e5a75-128">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="e5a75-128">Strings</span></span>](strings.md)
