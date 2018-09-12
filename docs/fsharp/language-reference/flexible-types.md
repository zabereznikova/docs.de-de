---
title: Flexible Typen (F#)
description: Erfahren Sie, wie Sie mit F#-Anmerkung flexibler Typen, die angibt, dass ein Parameter, Variablen oder Wert ein Typs mit einem angegebenen Typ kompatibel ist.
ms.date: 05/16/2016
ms.openlocfilehash: b6c97c3cc19f15b2c8db74b2c55660a16b2858f7
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44698467"
---
# <a name="flexible-types"></a>Flexible Typen

Ein *Anmerkung flexibler Typen* gibt an, dass ein Parameter, Variablen oder Wert ein Typs, der mit einem angegebenen Typ kompatibel ist, in denen die Kompatibilität anhand der Position in einer objektorientierten Hierarchie von Klassen oder Schnittstellen bestimmt. Flexible Typen eignen sich besonders dann, wenn die automatische Konvertierung in Typen, die in der Hierarchie höher nicht erfolgt, aber weiterhin die Funktionen zum Arbeiten mit beliebigen Typs in der Hierarchie oder jeder Typ, der eine Schnittstelle implementiert aktivieren möchten.

## <a name="syntax"></a>Syntax

```fsharp
#type
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax *Typ* stellt einen Basistyp oder eine Schnittstelle dar.

Ein flexibler Typ entspricht ein generischer Typ mit einer Einschränkung, die die zulässigen Typen auf Typen beschränkt, die mit dem Typ Basis oder Schnittstelle kompatibel sind. Das heißt, entsprechen die folgenden zwei Codezeilen.

```fsharp
#SomeType

'T when 'T :> SomeType
```

Flexible Typen sind in verschiedenen Arten von Situationen nützlich. Bei einer Funktion höherer Ordnung (eine Funktion, die eine Funktion als Argument akzeptiert), ist es beispielsweise häufig nützlich, um die Funktion einen flexiblen Typ zurückgeben. Im folgenden Beispiel ist die Verwendung eines flexiblen Typs mit einer Sequenzargument in `iterate2` ermöglicht die Funktion höheren Ordnung Arbeit mit Funktionen, die Sequenzen, Arrays, Listen und beliebige andere aufzählbare Typen zu generieren.

Erwägen Sie die folgenden zwei Funktionen, die eine der gibt eine Sequenz, der andere einen flexiblen Typ zurückgibt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

Betrachten Sie als ein weiteres Beispiel: die [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) Library-Funktion:

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

Sie können eine der folgenden aufzählbaren Sequenzen dieser Funktion übergeben:

- Eine Liste mit Listen
- Eine Liste von arrays
- Ein Array von Listen
- Ein Array von Sequenzen
- Eine beliebige andere Kombination der aufzählbaren Sequenzen

Der folgende code verwendet `Seq.concat` die Szenarien veranschaulicht werden, die Sie mithilfe flexible Typen unterstützen können.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

Die Ausgabe lautet wie folgt.

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

In f# sind wie in anderen objektorientierten Sprachen Kontexte, die in denen abgeleiteten Typen oder Typen, die Schnittstellen implementieren automatisch in einem Basistyp oder der Schnittstellentyp konvertiert werden. Diesen automatischen Konvertierungen erfolgen in direkten Argumente, jedoch nicht, wenn der Typ in eine untergeordnete Position, als Teil einer komplexeren Typ wie einen Rückgabetyp eines Funktionstyps oder als ein Argument vom Typ ist. Daher ist die flexiblen Typ Notation vor allem nützlich, wenn der Typ, die, dem Sie sie anwenden können, sind, Teil eines komplexen Typs ist.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Generika](generics/index.md)
