---
title: Vererbung
description: "Erfahren Sie, wie Sie F #-Vererbungs Beziehungen mithilfe des Schlüssel Worts ' erben ' angeben."
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223848"
---
# <a name="inheritance"></a>Vererbung

Vererbung wird verwendet, um die "is-a"-Beziehung oder die unter Typisierung in der objektorientierten Programmierung zu modellieren.

## <a name="specifying-inheritance-relationships"></a>Angeben von Vererbungs Beziehungen

Sie geben Vererbungs Beziehungen mithilfe des- `inherit` Schlüssel Worts in einer Klassen Deklaration an. Das grundlegende syntaktische Formular wird im folgenden Beispiel gezeigt.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

Eine Klasse kann höchstens über eine direkte Basisklasse verfügen. Wenn Sie mit dem-Schlüsselwort keine Basisklasse angeben `inherit` , erbt die-Klasse implizit von `System.Object` .

## <a name="inherited-members"></a>Geerbte Elemente

Wenn eine Klasse von einer anderen Klasse erbt, sind die Methoden und Member der Basisklasse für Benutzer der abgeleiteten Klasse so verfügbar, als wären Sie direkte Member der abgeleiteten Klasse.

Alle let-Bindungen und Konstruktorparameter sind in einer Klasse privat und können daher nicht von abgeleiteten Klassen aus aufgerufen werden.

Das Schlüsselwort `base` ist in abgeleiteten Klassen verfügbar und verweist auf die Instanz der Basisklasse. Es wird wie der selbst Bezeichner verwendet.

## <a name="virtual-methods-and-overrides"></a>Virtuelle Methoden und über schreibungen

Virtuelle Methoden (und Eigenschaften) funktionieren in F # in Bezug auf andere .NET-Sprachen etwas anders. Um einen neuen virtuellen Member zu deklarieren, verwenden Sie das- `abstract` Schlüsselwort. Dies geschieht unabhängig davon, ob Sie eine Standard Implementierung für diese Methode bereitstellen. Daher folgt eine komplette Definition einer virtuellen Methode in einer Basisklasse diesem Muster:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

Und in einer abgeleiteten Klasse folgt eine außer Kraft setzung dieser virtuellen Methode diesem Muster:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

Wenn Sie die Standard Implementierung in der Basisklasse weglassen, wird die Basisklasse zu einer abstrakten Klasse.

Im folgenden Codebeispiel wird die Deklaration einer neuen virtuellen Methode `function1` in einer Basisklasse und die Überschreibung in einer abgeleiteten Klasse veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>Konstruktoren und Vererbung

Der Konstruktor für die Basisklasse muss in der abgeleiteten Klasse aufgerufen werden. Die Argumente für den Basisklassenkonstruktor werden in der Argumentliste in der- `inherit` Klausel angezeigt. Die verwendeten Werte müssen von den Argumenten bestimmt werden, die für den Konstruktor der abgeleiteten Klasse bereitgestellt werden.

Der folgende Code zeigt eine Basisklasse und eine abgeleitete Klasse, in der die abgeleitete Klasse den Basisklassenkonstruktor in der Vererbungs Klausel aufruft:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

Bei mehreren Konstruktoren kann der folgende Code verwendet werden. Die erste Zeile der abgeleiteten Klassenkonstruktoren ist die `inherit` -Klausel, und die Felder werden als explizite Felder angezeigt, die mit dem- `val` Schlüsselwort deklariert werden. Weitere Informationen finden Sie unter [Explizite Felder: das- `val` Schlüsselwort](./members/explicit-fields-the-val-keyword.md).

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

In Fällen, in denen eine geringfügige Änderung eines Typs erforderlich ist, sollten Sie die Verwendung eines Objekt Ausdrucks als Alternative zu Vererbung in Erwägung gezogen. Das folgende Beispiel veranschaulicht die Verwendung eines Objekt Ausdrucks als Alternative zum Erstellen eines neuen abgeleiteten Typs:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

Weitere Informationen zu Objekt Ausdrücken finden Sie unter [Object Expressions](object-expressions.md).

Wenn Sie Objekt Hierarchien erstellen, sollten Sie die Verwendung einer Unterscheidungs-Union anstelle der Vererbung in Erwägung gezogen. Unterscheidungs-Unions können auch ein unterschiedliches Verhalten verschiedener Objekte modellieren, die einen gemeinsamen allgemeinen Typ haben. Eine einzelne Unterscheidungs-Union kann häufig den Bedarf an einer Reihe abgeleiteter Klassen ausschließen, die neben Abweichungen darstellen. Informationen zu Unterscheidungs-Unions finden Sie unter Unterscheidungs- [Unions](discriminated-unions.md).

## <a name="see-also"></a>Weitere Informationen

- [Objektausdrücke](object-expressions.md)
- [F#-Sprachreferenz](index.md)
