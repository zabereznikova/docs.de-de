---
title: Methoden
description: Erfahren Sie, F# wie eine Methode eine Funktion ist, die einem Typ zugeordnet ist, mit dem die Funktionen und das Verhalten von Objekten und Typen verfügbar gemacht und implementiert werden.
ms.date: 05/16/2016
ms.openlocfilehash: 13503690a59ace13dacba93b6fce9ea3240c5cc2
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627438"
---
# <a name="methods"></a>Methoden

Eine *Methode* ist eine-Funktion, die einem-Typ zugeordnet ist. Bei der objektorientierten Programmierung werden Methoden verwendet, um die Funktionalität und das Verhalten von Objekten und Typen verfügbar zu machen und zu implementieren.

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

In der vorherigen Syntax können Sie die verschiedenen Formen von Methoden Deklarationen und-Definitionen sehen. In längeren Methoden Texten folgt ein Zeilenumbruch dem Gleichheitszeichen (=), und der gesamte Methoden Text wird eingezogen.

Attribute können auf jede Methoden Deklaration angewendet werden. Sie sind der Syntax für eine Methoden Definition vorangestellt und werden in der Regel in einer separaten Zeile aufgeführt. Weitere Informationen finden Sie unter [Attribute](../attributes.md).

Methoden können als gekennzeichnet `inline`werden. Informationen zu `inline` finden Sie unter [Inlinefunktionen](../functions/inline-functions.md).

Nicht Inline-Methoden können rekursiv innerhalb des Typs verwendet werden. Es ist nicht erforderlich, explizit das `rec` Schlüsselwort zu verwenden.

## <a name="instance-methods"></a>Instanzmethoden

Instanzmethoden werden mit dem `member` -Schlüsselwort und einem *selbst Bezeichner*, gefolgt von einem-Wert (.) und dem Methodennamen und-Parametern, deklariert. Wie bei `let` Bindungen, kann die *Parameter-List* ein Muster sein. In der Regel setzen Sie Methode, die Parameter in Klammern in einem Formular handelt es sich die Methoden wie Tupel werden angezeigt in F#, wenn sie in anderen .NET Framework-Sprachen erstellt werden. Das Curry-Formular (durch Leerzeichen getrennte Parameter) ist jedoch ebenfalls üblich, und andere Muster werden ebenfalls unterstützt.

Im folgenden Beispiel werden die Definition und die Verwendung einer nicht abstrakten Instanzmethode veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

Verwenden Sie in Instanzmethoden den Self-Identifier nicht für den Zugriff auf Felder, die mithilfe von let-Bindungen definiert wurden. Verwenden Sie den selbst Bezeichner, wenn Sie auf andere Member und Eigenschaften zugreifen.

## <a name="static-methods"></a>Statische Methoden

Das- `static` Schlüsselwort wird verwendet, um anzugeben, dass eine Methode ohne eine-Instanz aufgerufen werden kann und keiner Objektinstanz zugeordnet ist. Andernfalls sind Methoden Instanzmethoden.

Das Beispiel im nächsten Abschnitt zeigt Felder, die mit dem `let` -Schlüsselwort deklariert werden, mit `member` dem-Schlüsselwort deklarierte Eigenschaften und eine `static` statische Methode, die mit dem-Schlüsselwort deklariert wurde.

Das folgende Beispiel veranschaulicht die Definition und Verwendung statischer Methoden. Nehmen Sie an, dass sich diese Methoden `SomeType` Definitionen in der-Klasse des vorherigen Abschnitts befinden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Abstrakte und virtuelle Methoden

Das Schlüssel `abstract` Wort gibt an, dass eine Methode einen virtuellen dispatchslot hat und möglicherweise keine Definition in der Klasse aufweist. Ein *virtueller dispatchslot* ist ein Eintrag in einer intern verwalteten Tabelle von Funktionen, die zur Laufzeit verwendet wird, um virtuelle Funktionsaufrufe in einem objektorientierten Typ zu suchen. Der virtuelle Dispatchmechanismus ist der Mechanismus, der *Polymorphie*implementiert, ein wichtiges Feature der objektorientierten Programmierung. Eine Klasse, die über mindestens eine abstrakte Methode ohne Definition verfügt, ist eine *abstrakte Klasse*, was bedeutet, dass keine Instanzen dieser Klasse erstellt werden können. Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).

Abstrakte Methoden Deklarationen enthalten keinen Methoden Text. Stattdessen folgt der Name der Methode einem Doppelpunkt (:) und eine Typsignatur für die Methode. Die Typsignatur einer Methode ist identisch mit der, die von IntelliSense angezeigt wird, wenn Sie den Mauszeiger über einen Methodennamen im Visual Studio Code-Editor bewegen, außer ohne Parameternamen. Typsignaturen werden auch vom Interpreter "FSI. exe" angezeigt, wenn Sie interaktiv arbeiten. Die Typsignatur einer Methode wird gebildet, indem die Typen der Parameter, gefolgt vom Rückgabetyp, mit entsprechenden Trennzeichen aufgelistet werden. Curry-Parameter werden durch `->` getrennt, und tupelparameter werden durch `*`getrennt. Der Rückgabewert wird immer von den Argumenten durch ein `->` Symbol getrennt. Klammern können verwendet werden, um komplexe Parameter zu gruppieren, z. b. Wenn ein Funktionstyp ein Parameter ist, oder um anzugeben, dass ein Tupel als einzelner Parameter und nicht als zwei Parameter behandelt wird.

Sie können auch abstrakten Methoden Standarddefinitionen übergeben, indem Sie die Definition der-Klasse hinzufügen `default` und das-Schlüsselwort verwenden, wie im Syntax Block in diesem Thema gezeigt. Eine abstrakte Methode, die eine Definition in derselben Klasse aufweist, entspricht einer virtuellen Methode in anderen .NET Framework Sprachen. Unabhängig davon, ob eine Definition vorhanden ist `abstract` , erstellt das Schlüsselwort einen neuen dispatchslot in der virtuellen Funktions Tabelle für die Klasse.

Unabhängig davon, ob eine Basisklasse die abstrakten Methoden implementiert, können abgeleitete Klassen Implementierungen abstrakter Methoden bereitstellen. Um eine abstrakte Methode in einer abgeleiteten Klasse zu implementieren, definieren Sie eine Methode, die den gleichen Namen und die gleiche Signatur in der abgeleiteten `default` Klasse aufweist, mit Ausnahme des `override` -oder-Schlüssel Worts, und stellen den Methoden Text bereit. Die Schlüssel `override` Wörter `default` und bedeuten genau dasselbe. Verwenden `override` Sie, wenn die neue Methode eine Basisklassen Implementierung überschreibt `default` . verwenden Sie diese Methode, wenn Sie in derselben Klasse wie die ursprüngliche abstrakte Deklaration eine Implementierung erstellen. Verwenden Sie das `abstract` -Schlüsselwort nicht für die Methode, die die Methode implementiert, die in der Basisklasse als abstrakt deklariert wurde.

Das folgende Beispiel veranschaulicht eine abstrakte Methode `Rotate` mit einer Standard Implementierung, die einer .NET Framework virtuellen Methode entspricht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

Im folgenden Beispiel wird eine abgeleitete Klasse veranschaulicht, die eine Basisklassen Methode überschreibt. In diesem Fall wird das Verhalten durch die-Überschreibung geändert, sodass die-Methode nichts bewirkt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Überladene Methoden

Überladene Methoden sind Methoden, die über identische Namen in einem bestimmten Typ verfügen, aber über unterschiedliche Argumente verfügen. In F# sind optionale Argumente in der Regel überladene Methoden verwendet. Allerdings sind überladene Methoden in der Sprache zulässig, vorausgesetzt, dass sich die Argumente in der tupelform und nicht in der Cursor Form befinden.

## <a name="optional-arguments"></a>Optionale Argumente

Ab F# 4.1, können Sie auch optionale Argumente hat den Standardwert des Parameters in Methoden verfügen.  Dies dient der Erleichterung der Interoperation mit C# Code.  Im folgenden Beispiel wird die Syntax veranschaulicht:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Beachten Sie, dass der in `DefaultParameterValue` übergebene Wert dem Eingabetyp entsprechen muss.  Im obigen Beispiel ist es ein `int`.  Der Versuch, einen nicht ganzzahligen Wert `DefaultParameterValue` in zu übergeben, führt zu einem Kompilierungsfehler.

## <a name="example-properties-and-methods"></a>Beispiel: Eigenschaften und Methoden

Das folgende Beispiel enthält einen Typ, der Beispiele für Felder, private Funktionen, Eigenschaften und eine statische Methode enthält.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Siehe auch

- [Mitglieder](index.md)
