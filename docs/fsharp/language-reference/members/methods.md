---
title: Methoden
description: 'Erfahren Sie, wie eine F #-Methode eine Funktion ist, die einem Typ zugeordnet ist, der verwendet wird, um die Funktionalität und das Verhalten von Objekten und Typen bereitzustellen und zu implementieren.'
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224109"
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

## <a name="remarks"></a>Bemerkungen

In der vorherigen Syntax können Sie die verschiedenen Formen von Methoden Deklarationen und-Definitionen sehen. In längeren Methoden Texten folgt ein Zeilenumbruch dem Gleichheitszeichen (=), und der gesamte Methoden Text wird eingezogen.

Attribute können auf jede Methoden Deklaration angewendet werden. Sie sind der Syntax für eine Methoden Definition vorangestellt und werden in der Regel in einer separaten Zeile aufgeführt. Weitere Informationen finden Sie unter [Attribute](../attributes.md).

Methoden können als gekennzeichnet werden `inline` . Informationen zu `inline` finden Sie unter [Inlinefunktionen](../functions/inline-functions.md).

Nicht Inline-Methoden können rekursiv innerhalb des Typs verwendet werden. Es ist nicht erforderlich, explizit das `rec` Schlüsselwort zu verwenden.

## <a name="instance-methods"></a>Instanzmethoden

Instanzmethoden werden mit dem `member` -Schlüsselwort und einem *selbst Bezeichner*, gefolgt von einem-Wert (.) und dem Methodennamen und-Parametern, deklariert. Wie bei `let` Bindungen, kann die *Parameter-List* ein Muster sein. In der Regel schließen Sie Methoden Parameter in Klammern in einem tupelformular ein. Dies ist die Methode, mit der Methoden in F # angezeigt werden, wenn Sie in anderen .NET Framework Sprachen erstellt werden. Das Curry-Formular (durch Leerzeichen getrennte Parameter) ist jedoch ebenfalls üblich, und andere Muster werden ebenfalls unterstützt.

Im folgenden Beispiel werden die Definition und die Verwendung einer nicht abstrakten Instanzmethode veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

Verwenden Sie in Instanzmethoden den Self-Identifier nicht für den Zugriff auf Felder, die mithilfe von let-Bindungen definiert wurden. Verwenden Sie den selbst Bezeichner, wenn Sie auf andere Member und Eigenschaften zugreifen.

## <a name="static-methods"></a>Statische Methoden

Das-Schlüsselwort `static` wird verwendet, um anzugeben, dass eine Methode ohne eine-Instanz aufgerufen werden kann und keiner Objektinstanz zugeordnet ist. Andernfalls sind Methoden Instanzmethoden.

Das Beispiel im nächsten Abschnitt zeigt Felder, die mit dem- `let` Schlüsselwort deklariert werden, mit dem-Schlüsselwort deklarierte Eigenschaften `member` und eine statische Methode, die mit dem- `static` Schlüsselwort deklariert wurde.

Das folgende Beispiel veranschaulicht die Definition und Verwendung statischer Methoden. Nehmen Sie an, dass sich diese Methoden Definitionen in der- `SomeType` Klasse des vorherigen Abschnitts befinden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Abstrakte und virtuelle Methoden

Das Schlüsselwort `abstract` gibt an, dass eine Methode einen virtuellen dispatchslot hat und möglicherweise keine Definition in der Klasse aufweist. Ein *virtueller dispatchslot* ist ein Eintrag in einer intern verwalteten Tabelle von Funktionen, die zur Laufzeit verwendet wird, um virtuelle Funktionsaufrufe in einem objektorientierten Typ zu suchen. Der virtuelle Dispatchmechanismus ist der Mechanismus, der *Polymorphie*implementiert, ein wichtiges Feature der objektorientierten Programmierung. Eine Klasse, die über mindestens eine abstrakte Methode ohne Definition verfügt, ist eine *abstrakte Klasse*, was bedeutet, dass keine Instanzen dieser Klasse erstellt werden können. Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).

Abstrakte Methoden Deklarationen enthalten keinen Methoden Text. Stattdessen folgt der Name der Methode einem Doppelpunkt (:) und eine Typsignatur für die Methode. Die Typsignatur einer Methode ist identisch mit der, die von IntelliSense angezeigt wird, wenn Sie den Mauszeiger über einen Methodennamen im Visual Studio Code-Editor bewegen, außer ohne Parameternamen. Typsignaturen werden auch vom Interpreter angezeigt, fsi.exe, wenn Sie interaktiv arbeiten. Die Typsignatur einer Methode wird gebildet, indem die Typen der Parameter, gefolgt vom Rückgabetyp, mit entsprechenden Trennzeichen aufgelistet werden. Curry-Parameter werden durch getrennt, `->` und tupelparameter werden durch getrennt `*` . Der Rückgabewert wird immer von den Argumenten durch ein `->` Symbol getrennt. Klammern können verwendet werden, um komplexe Parameter zu gruppieren, z. b. Wenn ein Funktionstyp ein Parameter ist, oder um anzugeben, dass ein Tupel als einzelner Parameter und nicht als zwei Parameter behandelt wird.

Sie können auch abstrakten Methoden Standarddefinitionen übergeben, indem Sie die Definition der-Klasse hinzufügen und das- `default` Schlüsselwort verwenden, wie im Syntax Block in diesem Thema gezeigt. Eine abstrakte Methode, die eine Definition in derselben Klasse aufweist, entspricht einer virtuellen Methode in anderen .NET Framework Sprachen. Unabhängig davon, ob eine Definition vorhanden ist, `abstract` erstellt das Schlüsselwort einen neuen dispatchslot in der virtuellen Funktions Tabelle für die Klasse.

Unabhängig davon, ob eine Basisklasse die abstrakten Methoden implementiert, können abgeleitete Klassen Implementierungen abstrakter Methoden bereitstellen. Um eine abstrakte Methode in einer abgeleiteten Klasse zu implementieren, definieren Sie eine Methode, die den gleichen Namen und die gleiche Signatur in der abgeleiteten Klasse aufweist, mit Ausnahme des `override` `default` -oder-Schlüssel Worts, und stellen den Methoden Text bereit. Die Schlüsselwörter `override` und `default` bedeuten genau dasselbe. Verwenden `override` Sie, wenn die neue Methode eine Basisklassen Implementierung überschreibt `default` . verwenden Sie diese Methode, wenn Sie in derselben Klasse wie die ursprüngliche abstrakte Deklaration eine Implementierung erstellen. Verwenden Sie das- `abstract` Schlüsselwort nicht für die Methode, die die Methode implementiert, die in der Basisklasse als abstrakt deklariert wurde.

Das folgende Beispiel veranschaulicht eine abstrakte Methode `Rotate` mit einer Standard Implementierung, die einer .NET Framework virtuellen Methode entspricht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

Im folgenden Beispiel wird eine abgeleitete Klasse veranschaulicht, die eine Basisklassen Methode überschreibt. In diesem Fall wird das Verhalten durch die-Überschreibung geändert, sodass die-Methode nichts bewirkt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Überladene Methoden

Überladene Methoden sind Methoden, die über identische Namen in einem bestimmten Typ verfügen, aber über unterschiedliche Argumente verfügen. In F # werden optionale Argumente normalerweise anstelle von überladenen Methoden verwendet. Allerdings sind überladene Methoden in der Sprache zulässig, vorausgesetzt, dass sich die Argumente in der tupelform und nicht in der Cursor Form befinden.

## <a name="optional-arguments"></a>Optionale Argumente

Ab F # 4,1 können Sie auch optionale Argumente mit einem Standardparameter Wert in-Methoden haben.  Dies dient der Vereinfachung der Interoperation mit c#-Code.  Im folgenden Beispiel wird die Syntax veranschaulicht:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Beachten Sie, dass der in übergebene Wert `DefaultParameterValue` dem Eingabetyp entsprechen muss.  Im obigen Beispiel ist es ein `int` .  Der Versuch, einen nicht ganzzahligen Wert in zu übergeben, `DefaultParameterValue` führt zu einem Kompilierungsfehler.

## <a name="example-properties-and-methods"></a>Beispiel: Eigenschaften und Methoden

Das folgende Beispiel enthält einen Typ, der Beispiele für Felder, private Funktionen, Eigenschaften und eine statische Methode enthält.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Weitere Informationen

- [Mitglieder](index.md)
