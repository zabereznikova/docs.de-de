---
title: Vererbung
description: Erfahren Sie, wie Sie die Vererbungsbeziehungen von F- und Vererbungsbeziehungen mithilfe des Schlüsselworts "erben" angeben.
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401130"
---
# <a name="inheritance"></a>Vererbung

Vererbung wird verwendet, um die "is-a"-Beziehung oder Untertypisierung in der objektorientierten Programmierung zu modellieren.

## <a name="specifying-inheritance-relationships"></a>Angeben von Vererbungsbeziehungen

Sie geben Vererbungsbeziehungen an, indem Sie das `inherit` Schlüsselwort in einer Klassendeklaration verwenden. Die grundlegende syntaktische Form wird im folgenden Beispiel gezeigt.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

Eine Klasse kann höchstens eine direkte Basisklasse haben. Wenn Sie keine Basisklasse mithilfe `inherit` des Schlüsselworts angeben, erbt die Klasse implizit von `System.Object`.

## <a name="inherited-members"></a>Geerbte Elemente

Wenn eine Klasse von einer anderen Klasse erbt, stehen die Methoden und Member der Basisklasse Benutzern der abgeleiteten Klasse zur Verfügung, als wären sie direkte Member der abgeleiteten Klasse.

Alle let-Bindungen und Konstruktorparameter sind für eine Klasse privat und können daher nicht von abgeleiteten Klassen aufgerufen werden.

Das `base` Schlüsselwort ist in abgeleiteten Klassen verfügbar und bezieht sich auf die Basisklasseninstanz. Es wird wie die Selbstbezeichnerverwendet.

## <a name="virtual-methods-and-overrides"></a>Virtuelle Methoden und Überschreibungen

Virtuelle Methoden (und Eigenschaften) funktionieren in F-Code etwas anders als in anderen .NET-Sprachen. Um ein neues virtuelles Mitglied `abstract` zu deklarieren, verwenden Sie das Schlüsselwort. Sie tun dies unabhängig davon, ob Sie eine Standardimplementierung für diese Methode bereitstellen. Daher folgt eine vollständige Definition einer virtuellen Methode in einer Basisklasse diesem Muster:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

Und in einer abgeleiteten Klasse folgt eine Außerkraftsetzung dieser virtuellen Methode diesem Muster:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

Wenn Sie die Standardimplementierung in der Basisklasse weglassen, wird die Basisklasse zu einer abstrakten Klasse.

Das folgende Codebeispiel veranschaulicht die Deklaration einer neuen virtuellen Methode `function1` in einer Basisklasse und wie sie in einer abgeleiteten Klasse überschrieben werden kann.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>Konstruktoren und Vererbung

Der Konstruktor für die Basisklasse muss in der abgeleiteten Klasse aufgerufen werden. Die Argumente für den Basisklassenkonstruktor werden `inherit` in der Argumentliste in der Klausel angezeigt. Die verwendeten Werte müssen aus den Argumenten bestimmt werden, die dem abgeleiteten Klassenkonstruktor bereitgestellt werden.

Der folgende Code zeigt eine Basisklasse und eine abgeleitete Klasse, bei der die abgeleitete Klasse den Basisklassenkonstruktor in der erben-Klausel aufruft:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

Bei mehreren Konstruktoren kann der folgende Code verwendet werden. Die erste Zeile der abgeleiteten Klassenkonstruktoren ist die `inherit` Klausel, und die `val` Felder werden als explizite Felder angezeigt, die mit dem Schlüsselwort deklariert werden. Weitere Informationen finden Sie unter [Explizite Felder: `val` Das Schlüsselwort](./members/explicit-fields-the-val-keyword.md).

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

In Fällen, in denen eine geringfügige Änderung eines Typs erforderlich ist, sollten Sie einen Objektausdruck als Alternative zur Vererbung verwenden. Das folgende Beispiel veranschaulicht die Verwendung eines Objektausdrucks als Alternative zum Erstellen eines neuen abgeleiteten Typs:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

Weitere Informationen zu Objektausdrücken finden Sie unter [Objektausdrücke](object-expressions.md).

Wenn Sie Objekthierarchien erstellen, sollten Sie eine diskriminierte Union anstelle der Vererbung verwenden. Diskriminierte Vereinigungen können auch unterschiedliches Verhalten verschiedener Objekte modellieren, die einen gemeinsamen Gesamttyp aufweisen. Eine einzelne diskriminierte Union kann oft die Notwendigkeit einer Reihe abgeleiteter Klassen eliminieren, die geringfügige Abweichungen voneinander sind. Informationen zu diskriminierten Gewerkschaften finden Sie unter [Diskriminierte Gewerkschaften](discriminated-unions.md).

## <a name="see-also"></a>Weitere Informationen

- [Objektausdrücke](object-expressions.md)
- [Sprachreferenz](index.md)
