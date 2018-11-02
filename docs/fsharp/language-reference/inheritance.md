---
title: Vererbung (F#)
description: Erfahren Sie, wie Sie F#-vererbungsbeziehungen mithilfe des Schlüsselworts "inherit" angeben.
ms.date: 05/16/2016
ms.openlocfilehash: e4d79244fb9bada5db0c5c4c7179d4bfe6e21f3d
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43864468"
---
# <a name="inheritance"></a>Vererbung

Vererbung wird verwendet, um die Beziehung "ist-ein" zu modellieren oder von Untertypen in der objektorientierten Programmierung.

## <a name="specifying-inheritance-relationships"></a>Angeben von Vererbungsbeziehungen

Geben Sie vererbungsbeziehungen mithilfe der `inherit` Schlüsselwort in einer Klassendeklaration. Im folgenden Beispiel wird die grundlegende syntaktische Form angezeigt.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

Eine Klasse kann höchstens eine direkte Basisklasse verfügen. Wenn Sie keine Basisklasse mithilfe von angeben der `inherit` Schlüsselworts die Klasse erbt implizit von `System.Object`.

## <a name="inherited-members"></a>Vererbte Member

Wenn eine Klasse von einer anderen Klasse erbt, sind die Methoden und Member der Basisklasse für Benutzer der abgeleiteten Klasse verfügbar, als wären sie direkte Member der abgeleiteten Klasse.

Eine let-Bindungen und Konstruktorparameter auf eine Klasse privat sind und aus diesem Grund können nicht von abgeleiteten Klassen zugegriffen werden kann.

Das Schlüsselwort `base` steht in abgeleiteten Klassen aus, und verweist auf die Instanz der Basisklasse. Es wird wie der Selbstbezeichner verwendet.

## <a name="virtual-methods-and-overrides"></a>Virtuelle Methoden und Außerkraftsetzungen

Virtuelle Methoden (und Eigenschaften) funktionieren etwas anders als in F#-im Vergleich zu anderen. Um ein neuer virtueller Member zu deklarieren, verwenden Sie die `abstract` Schlüsselwort. Dies geschieht unabhängig davon, ob Sie eine Standardimplementierung für diese Methode bereitstellen. Eine vollständige Definition der eine virtuelle Methode in einer Basisklasse folgt daher diesem Muster:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

Und in einer abgeleiteten Klasse eine Überschreibung der virtuellen Methode folgt diesem Muster:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

Wenn Sie die standardmäßige Implementierung in der Basisklasse auslassen, wird die Basisklasse eine abstrakte Klasse.

Das folgende Codebeispiel veranschaulicht die Deklaration einer neuen virtuellen Methode `function1` in einer Basisklasse und wie es in einer abgeleiteten Klasse überschrieben wird.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>Konstruktoren und Vererbung

Der Konstruktor der Basisklasse muss in der abgeleiteten Klasse aufgerufen werden. Die Argumente für den Konstruktor der Basisklasse angezeigt, in der Argumentliste in die `inherit` Klausel. Die Werte, die verwendet werden, müssen aus Argumente, die dem abgeleiteten Klassenkonstruktor ermittelt werden.

Der folgende Code zeigt eine Basisklasse und einer abgeleiteten Klasse, in denen die abgeleitete Klasse den Basisklassenkonstruktor in der Klausel erben aufruft:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

Im Fall von mehreren Konstruktoren kann der folgende Code verwendet werden. Die erste Zeile der abgeleiteten Klassenkonstruktoren ist die `inherit` -Klausel und die Felder angezeigt als explizite Felder, die mit deklariert werden die `val` Schlüsselwort. Weitere Informationen finden Sie unter [explizite Felder: das `val` Schlüsselwort](members/explicit-fields-the-val-keyword.md).

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

In Fällen, in denen eine geringfügige Änderung eines Typs erforderlich ist, sollten Sie in Erwägung ziehen, einen Object-Ausdruck als Alternative zur Vererbung zu verwenden. Das folgende Beispiel veranschaulicht die Verwendung von Objektausdruck als Alternative zum Erstellen eines neuen abgeleiteten Typs:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

Weitere Informationen zu Object-Ausdrücke, finden Sie unter [Objektausdrücke](object-expressions.md).

Wenn Sie Objekthierarchien erstellen, erwägen Sie, die eine Unterscheidungs-Union anstelle von Vererbung. Unterscheidungs-Unions können auch verschiedene Modellverhalten unterschiedlicher Objekte, die einen gemeinsamen allgemeinen Typ gemeinsam nutzen. Eine einzelne Unterscheidungs-Union kann häufig nicht erforderlich für eine Reihe von abgeleiteten Klassen, die geringfügige Unterschiede voneinander sind. Weitere Informationen zu Unterscheidungs-Unions, finden Sie unter [Unterscheidungs-Unions](discriminated-unions.md).

## <a name="see-also"></a>Siehe auch

- [Objektausdrücke](object-expressions.md)
- [F#-Sprachreferenz](index.md)
