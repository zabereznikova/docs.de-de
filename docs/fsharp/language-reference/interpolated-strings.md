---
title: Interpolierte Zeichenfolgen
description: 'Erfahren Sie mehr über interpoliert Zeichen folgen, eine spezielle Form von Zeichen folgen, die es Ihnen ermöglicht, F #-Ausdrücke direkt in Sie einzubetten.'
ms.date: 11/12/2020
ms.openlocfilehash: a49d4e743306fd9bdabb1e019ec4e6c77e0e1f5a
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688624"
---
# <a name="interpolated-strings"></a>Interpolierte Zeichenfolgen

Interpoliert Zeichen folgen [sind Zeichen](strings.md) folgen, die es Ihnen ermöglichen, F #-Ausdrücke in Sie einzubetten. Sie sind in einer Vielzahl von Szenarien hilfreich, in denen sich der Wert einer Zeichenfolge basierend auf dem Ergebnis eines Werts oder Ausdrucks ändern kann.

## <a name="syntax"></a>Syntax

```fsharp
$"string-text {expr}"
$"string-text %format-specifier{expr}"
$"""string-text {"embedded string literal"}"""
```

## <a name="remarks"></a>Hinweise

Interinterpolierte Zeichen folgen ermöglichen das Schreiben von Code in "Holes" innerhalb eines Zeichenfolgenliterals. Im Folgenden finden Sie ein einfaches Beispiel:

```fsharp
let name = "Phillip"
let age = 30
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

Der Inhalt zwischen den einzelnen `{}` Klammern kann ein beliebiger F #-Ausdruck sein.

Wenn Sie ein Klammer Paar mit Escapezeichen versehen möchten `{}` , schreiben Sie zwei von Ihnen wie folgt:

```fsharp
let str = $"A pair of braces: {{}}"
// "A pair of braces: {}"
```

## <a name="typed-interpolated-strings"></a>Typisierte interpoliert Zeichen folgen

Interinterpolierte Zeichen folgen können auch F #-Format Bearbeiter aufweisen, um den Typ Safey zu erzwingen.

```fsharp
let name = "Phillip"
let age = 30

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

Im vorherigen Beispiel übergibt der Code versehentlich den `age` Wert, wobei den Wert `name` hat und umgekehrt. Da die interinterpolierten Zeichen folgen Formatspezifizierer verwenden, ist dies ein Kompilierungsfehler anstelle eines geringfügigen Lauf Zeit Fehlers.

Alle Formatspezifizierer, die in der [Klartext-Formatierung](plaintext-formatting.md) abgedeckt werden, sind innerhalb einer interpoliert Zeichenfolge gültig.

## <a name="verbatim-interpolated-strings"></a>Wörtliche interinterpolierte Zeichen folgen

F # unterstützt wörtliche interpoliert Zeichen folgen mit dreifachen Anführungszeichen, sodass Sie Zeichen folgen Literale einbetten können.

```fsharp
let age = 30

printfn $"""Name: {"Phillip"}, Age: %d{age}"""
```

## <a name="aligning-expressions-in-interpolated-strings"></a>Ausrichten von Ausdrücken in interpoliert-Zeichen folgen

Sie können Ausdrücke in interinterpolierten Zeichen folgen mit linksbündig ausrichten oder mit `|` der Angabe, wie viele Leerzeichen übereinstimmen. Mit der folgenden interinterierten Zeichenfolge werden die linken und rechten Ausdrücke Links und rechts um 7 Leerzeichen ausgerichtet.

```fsharp
printfn $"""|{"Left",-7}|{"Right",7}|"""
// |Left   |  Right|
```

## <a name="interpolated-strings-and-formattablestring-formatting"></a>Interpoliert Zeichen folgen und `FormattableString` Formatierung

Sie können auch die Formatierung anwenden, die den Regeln für folgt <xref:System.FormattableString> :

```fsharp
let speedOfLight = 299792.458
printfn $"The speed of light is {speedOfLight:N3} km/s."
// "The speed of light is 299,792.458 km/s."
```

Außerdem kann eine interinterpolierte Zeichenfolge <xref:System.FormattableString> über eine Typanmerkung auch als typeCheck-Wert angegeben werden:

```fsharp
let frmtStr = $"The speed of light is {speedOfLight:N3} km/s." : FormattableString
// Type: FormattableString
// The speed of light is 299,792.458 km/s.
```

Beachten Sie, dass sich die Typanmerkung auf dem interinterierten Zeichen folgen Ausdruck selbst befinden muss. F # konvertiert eine interinterpolierte Zeichenfolge nicht implizit in eine <xref:System.FormattableString> .

## <a name="see-also"></a>Siehe auch

* [Zeichenfolgen](strings.md)
