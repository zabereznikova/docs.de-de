---
title: Vererbung (F#)
description: Informationen Sie zum f# vererbungsbeziehungen mit dem Schlüsselwort "inherit" angeben.
ms.date: 05/16/2016
ms.openlocfilehash: 3d0c0785fc595315a8283979b99d0ec4fc5cbc0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564770"
---
# <a name="inheritance"></a>Vererbung

Die Vererbung wird verwendet, um die Beziehung "ist-a" zu modellieren oder Untertypen, bei der objektorientierten Programmierung.


## <a name="specifying-inheritance-relationships"></a>Vererbungsbeziehungen angeben
Geben Sie vererbungsbeziehungen mithilfe der `inherit` Schlüsselwort in einer Klassendeklaration. Im folgenden Beispiel wird die grundlegende syntaktische Form angezeigt.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

Eine Klasse kann höchstens eine direkte Basisklasse haben. Wenn Sie eine Basisklasse keinen mithilfe angeben der `inherit` -Schlüsselwort, die Klasse erbt implizit von `System.Object`.


## <a name="inherited-members"></a>Geerbte Member
Wenn eine Klasse von einer anderen Klasse erbt, sind die Methoden und Member der Basisklasse für Benutzer der abgeleiteten Klasse verfügbar, als wären sie direkte Member der abgeleiteten Klasse.

Alle let-Bindungen und Konstruktorparameter auf eine Klasse privat sind und daher können nicht von abgeleiteten Klassen zugegriffen werden kann.

Das Schlüsselwort `base` steht in abgeleiteten Klassen und bezieht sich auf die Instanz der Basisklasse. Es wird wie der Selbstbezeichner verwendet.


## <a name="virtual-methods-and-overrides"></a>Virtuelle Methoden und Außerkraftsetzungen anpassen
Virtuelle Methoden (und Eigenschaften) funktioniert etwas anders in F#-im Vergleich zu anderen. Um einen neuen virtuellen Member zu deklarieren, verwenden Sie die `abstract` Schlüsselwort. Dies geschieht unabhängig davon, ob Sie eine standardmäßige Implementierung dieser Methode bereitstellen. Eine vollständige Definition einer virtuellen Methode in einer Basisklasse folgt daher diesem Muster:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

Und in einer abgeleiteten Klasse eine Überschreibung der virtuellen Methode folgt diesem Muster:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

Wenn Sie die standardmäßige Implementierung in der Basisklasse weglassen, wird die Basisklasse eine abstrakte Klasse.

Das folgende Codebeispiel veranschaulicht die Deklaration einer neuen virtuellen Methode `function1` in einer Basisklasse und wie Sie es in einer abgeleiteten Klasse überschreiben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]
    
## <a name="constructors-and-inheritance"></a>Konstruktoren und Vererbung
Der Konstruktor für die Basisklasse muss in der abgeleiteten Klasse aufgerufen werden. Die Argumente für den Konstruktor der Basisklasse angezeigt, in der Argumentliste der `inherit` Klausel. Die Werte, die verwendet werden, müssen aus Argumente, die dem abgeleiteten Klassenkonstruktor ermittelt werden.

Der folgende Code zeigt eine Basisklasse und eine abgeleitete Klasse, wenn die abgeleitete Klasse den Basisklassenkonstruktor in der erben-Klausel aufruft:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

Im Fall von mehreren Konstruktoren kann der folgende Code verwendet werden. Die erste Zeile der abgeleiteten Klassenkonstruktoren wird der `inherit` -Klausel und die Felder werden als explizite Felder, die mit deklariert werden die `val` Schlüsselwort. Weitere Informationen finden Sie unter [explizite Felder: das `val` Schlüsselwort](members/explicit-fields-the-val-keyword.md).

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a>Alternativen zur Vererbung
In Fällen, in denen eine kleinere Änderung eines Typs erforderlich ist, sollten Sie in Erwägung ziehen, ein Objektausdrücke als Alternative zur Vererbung zu verwenden. Das folgende Beispiel veranschaulicht die Verwendung eines Ausdrucks Objekt als Alternative zum Erstellen eines neuen abgeleiteten Typs:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

Weitere Informationen zu Objektausdrücke, finden Sie unter [Objektausdrücke](object-expressions.md).

Wenn Sie Objekthierarchien erstellen, erwägen Sie, die eine Unterscheidungs-Union anstelle der Vererbung. Unterscheidungs-Unions können auch verschiedene Modellverhalten unterschiedlichen Objekten, die einen gemeinsamen allgemeinen Typ aufweisen. Eine einzelne Unterscheidungs-Union kann häufig nicht erforderlich für eine Reihe von abgeleiteten Klassen aus, die geringfügige Unterschiede voneinander sind. Informationen zu Unterscheidungs-Unions finden Sie unter [Unterscheidungs-Unions](discriminated-unions.md).


## <a name="see-also"></a>Siehe auch
[Objektausdrücke](object-expressions.md)

[F#-Sprachreferenz](index.md)
