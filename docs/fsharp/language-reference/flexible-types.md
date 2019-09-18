---
title: Flexible Typen
description: Erfahren Sie, wie F# Sie eine flexible Typanmerkung verwenden, die angibt, dass ein Parameter, eine Variable oder ein Wert einen Typ aufweist, der mit einem angegebenen Typ kompatibel ist.
ms.date: 05/16/2016
ms.openlocfilehash: bf05f78f163d1f9c73c667df60925b66a5315627
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083062"
---
# <a name="flexible-types"></a>Flexible Typen

Eine *flexible Typanmerkung* gibt an, dass ein Parameter, eine Variable oder ein Wert einen Typ aufweist, der mit einem angegebenen Typ kompatibel ist, wobei die Kompatibilität durch die Position in einer objektorientierten Hierarchie von Klassen oder Schnittstellen bestimmt wird. Flexible Typen sind besonders nützlich, wenn die automatische Konvertierung in Typen, die in der Typhierarchie höher sind, nicht stattfindet, Sie aber weiterhin die Funktion für die Arbeit mit einem beliebigen Typ in der Hierarchie oder einem beliebigen Typ aktivieren möchten, der eine Schnittstelle implementiert.

## <a name="syntax"></a>Syntax

```fsharp
#type
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax stellt *Type* einen Basistyp oder eine Schnittstelle dar.

Ein flexibler Typ entspricht einem generischen Typ, der über eine Einschränkung verfügt, die die zulässigen Typen auf Typen beschränkt, die mit dem Basis-oder Schnittstellentyp kompatibel sind. Das heißt, die folgenden zwei Codezeilen sind äquivalent.

```fsharp
#SomeType

'T when 'T :> SomeType
```

Flexible Typen sind in verschiedenen Arten von Situationen nützlich. Wenn Sie z. b. über eine Funktion höherer Ordnung verfügen (eine Funktion, die eine Funktion als Argument annimmt), ist es oft hilfreich, dass die Funktion einen flexiblen Typ zurückgibt. Im folgenden Beispiel ermöglicht die Verwendung eines flexiblen Typs mit einem Sequence-Argument in `iterate2` der Funktion höherer Ordnung die Verwendung von Funktionen, die Sequenzen, Arrays, Listen und alle anderen Aufzähl Bare-Typen generieren.

Beachten Sie die folgenden zwei Funktionen, von denen eine eine Sequenz zurückgibt, die andere einen flexiblen Typ zurückgibt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

Betrachten Sie als weiteres Beispiel die Bibliotheksfunktion " [setq. Concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) ":

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

Sie können jede der folgenden Aufzähl Bare-Sequenzen an diese Funktion übergeben:

- Eine Liste mit Listen
- Eine Liste von Arrays
- Ein Array von Listen
- Ein Array von Sequenzen
- Eine beliebige andere Kombination von Aufzähl Bare-Sequenzen

Der folgende Code verwendet `Seq.concat` , um die Szenarien zu veranschaulichen, die Sie mithilfe von flexiblen Typen unterstützen können.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

Die Ausgabe lautet wie folgt.

```console
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

In F# sind wie in anderen objektorientierten Sprachen Kontexte, die in denen abgeleiteten Typen oder Typen, die Schnittstellen implementieren automatisch in einem Basistyp oder der Schnittstellentyp konvertiert werden. Diese automatischen Konvertierungen erfolgen in direkten Argumenten, jedoch nicht, wenn sich der Typ in einer untergeordneten Position befindet, als Teil eines komplexeren Typs, z. b. eines Rückgabe Typs eines Funktions Typs, oder als Typargument. Daher ist die flexible typnotation vor allem dann nützlich, wenn der Typ, auf den Sie Sie anwenden, Teil eines komplexeren Typs ist.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Generika](./generics/index.md)
