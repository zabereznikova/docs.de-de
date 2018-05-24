---
title: Methoden (F#)
description: Erfahren Sie, wie eine f#-Methode ist eine Funktion, die ein Typ, der verwendet werden, zur Verfügung stellen, und implementieren die Funktionalität und Verhalten von Objekten und Typen zugeordnet.
ms.date: 05/16/2016
ms.openlocfilehash: e30300b4dd6cc26712a5adbc8abf720f2c312a6f
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="methods"></a>Methoden

Ein *Methode* ist eine Funktion, die ein Typ zugeordnet ist. In einer objektorientierten Programmierung werden Methoden zur Verfügung stellen, und implementieren die Funktionalität und Verhalten von Objekten und Typen verwendet.


## <a name="syntax"></a>Syntax

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a>Hinweise
In der vorherigen Syntax können Sie die verschiedenen Formen von Deklarationen und Definitionen finden Sie unter. In längeren Methodentexte ein Zeilenumbruch folgt das Gleichheitszeichen (=) und der gesamte Methodentext eingezogen ist.

Attribute können auf eine Methodendeklaration angewendet werden. Die Syntax für eine Methodendefinition vorausgehen, und sind in der Regel in einer eigenen Zeile aufgeführt. Weitere Informationen finden Sie unter [Attribute](../attributes.md).

Methoden können markiert werden `inline`. Informationen zu `inline` finden Sie unter [Inlinefunktionen](../functions/inline-functions.md).

Nicht-Inlinemethoden können rekursiv im Typ verwendet werden; Es ist nicht erforderlich, explizit verwenden die `rec` Schlüsselwort.


## <a name="instance-methods"></a>Instanzmethoden
Instanzmethoden werden mit der `member` Schlüsselwort und ein *Selbstbezeichner*, gefolgt von einem Punkt (.) und den Methodennamen und Parameter. Wie bei der Fall ist `let` Bindungen, die *Parameterliste* kann ein Muster sein. In der Regel setzen Sie Methode, die Parameter in Klammern in Tupelform, also die Möglichkeit Methoden angezeigt werden in F# erläutert werden, wenn sie in anderen .NET Framework-Sprachen erstellt werden. Allerdings Curry-Form (Parameter durch Leerzeichen voneinander getrennt) ist auch häufig und andere Muster werden ebenfalls unterstützt.

Das folgende Beispiel veranschaulicht die Definition und Verwendung von einer nicht abstrakten Instanzmethode auf.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

Innerhalb von Instanzmethoden verwenden Sie nicht des Selbstbezeichners Zugriff Feldern mit Let-Bindungen definiert. Verwenden Sie beim Zugriff auf andere Elemente und Eigenschaften des Selbstbezeichners.


## <a name="static-methods"></a>Statische Methoden
Das Schlüsselwort `static` wird verwendet, um anzugeben, dass eine Methode ohne Instanz aufgerufen werden kann und keine Objektinstanz zugeordnet ist. Andernfalls sind Methoden Instanzmethoden.

Im Beispiel im nächsten Abschnitt zeigt Felder an, die mit deklariert die `let` Schlüsselwort, Eigenschaftenmember deklariert, mit der `member` -Schlüsselwort verwenden und eine statische Methode deklariert, mit der `static` Schlüsselwort.

Das folgende Beispiel veranschaulicht die Definition und Verwendung von statischen Methoden. Angenommen, dass diese Methodendefinitionen sind die `SomeType` Klasse im vorherigen Abschnitt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Abstrakte und virtuelle Methoden
Das Schlüsselwort `abstract` gibt an, dass eine Methode verfügt über einen virtuellen Dispatch-Slot und möglicherweise nicht in der Klasse. Ein *virtuellen Dispatch-Slot* wird ein Eintrag in einer internen Tabelle von Funktionen, die zur Laufzeit verwendet wird, suchen Sie die virtuelle Funktion, die in einem Typ mit dem objektorientierten aufruft. Der virtuelle Dispatchmechanismus ist der Mechanismus, der implementiert *Polymorphie*, ein wichtiges Feature von einer objektorientierten Programmierung. Ist eine Klasse, die mindestens eine abstrakte Methode ohne Definition verfügt über eine *abstrakte Klasse*, was bedeutet, dass keine Instanz dieser Klasse erstellt werden kann. Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).

Abstrakten Methodendeklarationen enthalten keine keinen Methodentext. Stattdessen folgt der Name der Methode von einem Doppelpunkt (:)) und eine Typsignatur für die Methode. Die Typsignatur einer Methode ist identisch, die von IntelliSense angezeigt werden, wenn Sie den Mauszeiger über den Namen einer Methode im Code-Editor von Visual Studio außer ohne Parameternamen anhalten. Typsignaturen werden ebenfalls von den Interpreter fsi.exe, angezeigt, wenn Sie interaktiv arbeiten. Die Typsignatur einer Methode wird durch die Typen der Parameter, gefolgt von den Rückgabetyp mit entsprechenden Trennzeichensymbole gebildet. Mit Currying Parameter werden getrennt vom `->` und Tupel-Parameter werden getrennt vom `*`. Der Rückgabewert ist immer aus den Argumenten von getrennt ein `->` Symbol. Klammern können verwendet werden, zu komplexe Parameter, z. B. wenn ein Funktionstyp einen Parameter, wird Gruppe oder um anzugeben, wenn ein Tupel als einen einzelnen Parameter anstatt als zwei Parameter behandelt wird.

Sie können auch geben abstrakte Methoden Default-Definitionen durch die Definition der Klasse hinzufügen und mithilfe der `default` -Schlüsselwort, wie in der Syntaxblock in diesem Thema gezeigt. Eine abstrakte Methode, die eine Definition in der gleichen Klasse hat entspricht eine virtuelle Methode in anderen .NET Framework-Sprachen. Gibt an, ob eine Definition vorhanden ist, die `abstract` Schlüsselwort erstellt einen neuen Dispatch-Platz in die virtuelle Funktionstabelle für die Klasse.

Unabhängig davon, ob eine Basisklasse abstrakten Methoden implementiert können abgeleitete Klassen die Implementierung der abstrakten Methoden angeben. Um eine abstrakte Methode in einer abgeleiteten Klasse zu implementieren, definieren Sie eine Methode mit dem gleichen Namen und derselben Signatur in der abgeleiteten Klasse, mit Ausnahme der Verwendung der `override` oder `default` -Schlüsselwort, und geben Sie den Methodentext. Die Schlüsselwörter `override` und `default` genau dieselbe Bedeutung. Verwenden Sie `override` verwenden, wenn die neue Methode überschreibt die basisklassenimplementierung; `default` beim Erstellen einer Implementierung in der gleichen Klasse wie die ursprüngliche abstrakte Deklaration. Verwenden Sie nicht die `abstract` -Schlüsselwort in der Methode, die die Methode implementiert, die in der Basisklasse abstrakt deklariert wurde.

Das folgende Beispiel veranschaulicht eine abstrakte Methode `Rotate` , besitzt eine Standardimplementierung, die Entsprechung einer virtuellen .NET Framework-Methode.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

Das folgende Beispiel veranschaulicht eine abgeleitete Klasse, die eine Basisklassenmethode überschreibt. In diesem Fall ändert die Überschreibung das Verhalten, damit die Methode keine Aktionen ausführt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Überladene Methoden
Überladene Methoden sind Methoden, die über identische Namen in einem bestimmten Typ verfügen, die über andere Argumente verfügen. In F# erläutert werden werden optionale Argumente in der Regel überladene Methoden verwendet. Überladene Methoden sind jedoch in der Sprache zulässig, vorausgesetzt, dass die Argumente in Tupelform und nicht mit Currying Formular sind.

## <a name="optional-arguments"></a>Optionale Argumente

Ab f# 4.1, können Sie auch optionale Argumente mit einem Standard-Parameterwert in Methoden verfügen.  Dies ist die Interoperation mit C#-Code zu vereinfachen.  Im folgende Beispiel wird die Syntax veranschaulicht:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Beachten Sie, die für der Wert übergeben `DefaultParameterValue` muss den Typ der Eingabe übereinstimmen.  Im obigen Beispiel ist ein `int`.  Bei dem Versuch, einen nicht ganzzahlige Wert übergeben `DefaultParameterValue` in einem Kompilierungsfehler führen würde.

## <a name="example-properties-and-methods"></a>Beispiel: Eigenschaften und Methoden
Das folgende Beispiel enthält einen Typ, der Beispiele für Felder, private Funktionen, Eigenschaften und eine statische Methode enthält.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Siehe auch
[Mitglieder](index.md)
