---
title: Methoden (F#)
description: Erfahren Sie, wie eine F#-Methode eine Funktion, die ein Typ, der verwendet werden, um verfügbar zu machen, und implementieren Sie die Funktionalität und Verhalten von Objekten und Typen zugeordnet ist.
ms.date: 05/16/2016
ms.openlocfilehash: 02d5a7d22d1ce79a06e15462637c373b33623f61
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "44253207"
---
# <a name="methods"></a>Methoden

Ein *Methode* ist eine Funktion, die einem Typ zugeordnet ist. In der objektorientierten Programmierung werden Methoden verfügbar machen, und implementieren die Funktionalität und Verhalten von Objekten und Typen verwendet.

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

In der vorherigen Syntax ist sehen Sie die verschiedenen Formen von Deklarationen und Definitionen. In Methodentexten länger ein Zeilenumbruch folgt das Gleichheitszeichen (=) und der gesamten Methodentext eingezogen ist.

Attribute können auf eine Methodendeklaration angewendet werden. Sie die Syntax für eine Methodendefinition vorausgehen und sind in der Regel in einer eigenen Zeile aufgeführt. Weitere Informationen finden Sie unter [Attribute](../attributes.md).

Methoden können markiert werden `inline`. Informationen zu `inline` finden Sie unter [Inlinefunktionen](../functions/inline-functions.md).

Nicht-Inline-Methoden können rekursiv innerhalb des Typs verwendet werden; besteht keine Notwendigkeit, die explizit die `rec` Schlüsselwort.

## <a name="instance-methods"></a>Instanzmethoden

Instanzmethoden werden mit der `member` Schlüsselwort und *Selbstbezeichner*, gefolgt von einem Punkt (.) und dem Methodennamen und Parameter. Wie bei der Fall ist `let` Bindungen, die *Parameterliste* kann ein Muster sein. In der Regel setzen Sie Methode, die Parameter in Klammern in einem Formular handelt es sich die Methoden wie Tupel werden angezeigt in f#, wenn sie in anderen .NET Framework-Sprachen erstellt werden. Allerdings wird die Curry-Form (Parameter durch Leerzeichen getrennt) ist auch üblich, und andere Muster werden ebenfalls unterstützt.

Das folgende Beispiel veranschaulicht die Definition und Verwendung einer nicht abstrakten Instanzmethode.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

Innerhalb von Instanzenmethoden verwenden Sie nicht des Selbstbezeichners Access-Feldern, die mit der Let-Bindungen definiert. Verwenden Sie den Self-Bezeichner, den Zugriff auf andere Elemente und Eigenschaften.

## <a name="static-methods"></a>Statische Methoden

Das Schlüsselwort `static` wird verwendet, um anzugeben, dass eine Methode kann, ohne eine Instanz aufgerufen werden aus, und keine Objektinstanz zugeordnet ist. Andernfalls sind die Methoden Instanzmethoden zur Verfügung.

Im Beispiel im nächsten Abschnitt zeigt die Felder, die mit dem deklariert die `let` Schlüsselwort Eigenschaftenmember deklariert, mit der `member` -Schlüsselwort, und eine statische Methode deklariert, mit der `static` Schlüsselwort.

Das folgende Beispiel veranschaulicht die Definition und Verwendung von statischen Methoden. Wird davon ausgegangen, dass diese Methodendefinitionen sind die `SomeType` Klasse, die im vorherigen Abschnitt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Abstrakte und virtuelle Methoden

Das Schlüsselwort `abstract` gibt an, dass eine Methode befindet sich einen virtueller Dispatch-Slot und kann keine Definition in der Klasse. Ein *virtueller Dispatch-Slot* ist ein Eintrag in einer intern verwalteten Tabelle von Funktionen, die zur Laufzeit verwendet wird, suchen Sie die virtuelle Funktion, die in einem objektorientierten Typ aufgerufen. Der virtueller Dispatch-Mechanismus ist der Mechanismus, der implementiert *Polymorphie*, ein wichtiges Merkmal der objektorientierten Programmierung. Eine Klasse, die mindestens eine abstrakte Methode ohne Definition ist eine *abstrakte Klasse*, was bedeutet, dass keine Instanzen dieser Klasse erstellt werden können. Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).

Abstrakte Methodendeklarationen beinhalten keinen Methodentext. Stattdessen folgt der Name der Methode von einem Doppelpunkt (:) und eine Typsignatur für die Methode. Die Typsignatur einer Methode ist identisch, die von IntelliSense angezeigt werden, wenn Sie den Mauszeiger über den Namen einer Methode in der Visual Studio Code-Editor, mit Ausnahme ohne Parameternamen anhalten. Typsignaturen werden ebenfalls durch den Interpreter fsi.exe, angezeigt, wenn Sie interaktiv arbeiten. Die Typsignatur einer Methode wird durch die Typen der Parameter, gefolgt von den Rückgabetyp, mit der entsprechenden Trennzeichen gebildet. Curry-Parameter werden durch getrennt `->` und Tupel-Parameter werden durch getrennt `*`. Der Rückgabewert ist immer getrennt aus den Argumenten von einem `->` Symbol. Klammern können verwendet werden, um komplexe Parameter, z. B. wenn ein Funktionstyp einen Parameter, wird zu gruppieren oder um anzugeben, wenn ein Tupel als einen einzelnen Parameter anstatt als zwei Parameter behandelt wird.

Sie können auch erteilen, abstrakte Methoden Default-Definitionen durch die Definition der Klasse hinzufügen und Verwenden der `default` -Schlüsselwort, wie in den Syntaxblock "in diesem Thema dargestellt. Eine abstrakte Methode, die eine Definition in der gleichen Klasse entspricht einer virtuellen Methode in anderen .NET Framework-Sprachen. Gibt an, ob eine Definition vorhanden ist, die `abstract` Schlüsselwort erstellt einen neuen Dispatchslot in der virtuellen Funktionstabelle für die Klasse.

Unabhängig davon, ob eine Basisklasse abstrakten Methoden implementiert können abgeleitete Klassen über Implementierungen von abstrakten Methoden bereitstellen. Um eine abstrakte Methode in einer abgeleiteten Klasse zu implementieren, definieren Sie eine Methode mit dem gleichen Namen und die Signatur in der abgeleiteten Klasse, mit Ausnahme der Verwendung der `override` oder `default` -Schlüsselwort, und geben Sie den Methodentext. Die Schlüsselwörter `override` und `default` genau dieselbe Bedeutung. Verwenden Sie `override` verwenden, wenn die neue Methode eine Implementierung der Basisklasse; überschreibt `default` bei der Erstellung einer Implementierung in der gleichen Klasse wie die ursprünglichen abstrakten Deklaration. Verwenden Sie nicht die `abstract` -Schlüsselwort in die Methode, die die Methode implementiert, die abstrakte in der Basisklasse deklariert wurde.

Das folgende Beispiel veranschaulicht eine abstrakte Methode `Rotate` eine Standardimplementierung, die Entsprechung einer virtuellen .NET Framework-Methode aufweist.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

Im folgende Beispiel wird veranschaulicht, eine abgeleitete Klasse, die eine Basisklassenmethode überschreibt. In diesem Fall ändert der außer Kraft setzen das Verhalten so, dass die Methode keine Aktion ausgeführt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Überladene Methoden

Überladene Methoden sind Methoden, die über identische Namen in einem bestimmten Typ verfügen jedoch über unterschiedliche Argumente. In f# sind optionale Argumente in der Regel überladene Methoden verwendet. Überladene Methoden sind jedoch in der Sprache zulässig, vorausgesetzt, dass die Argumente in Tupelform und nicht Curry-Form sind.

## <a name="optional-arguments"></a>Optionale Argumente

Ab f# 4.1, können Sie auch optionale Argumente hat den Standardwert des Parameters in Methoden verfügen.  Dadurch wird die Interoperation mit C#-Code zu vereinfachen.  Im folgende Beispiel wird die Syntax veranschaulicht:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Beachten Sie, die der Wert für übergeben `DefaultParameterValue` muss den Eingabetyp übereinstimmen.  Im obigen Beispiel ist es ein `int`.  Es wird versucht, einen nicht ganzzahligen Wert in übergeben `DefaultParameterValue` führt zu einem Kompilierungsfehler.

## <a name="example-properties-and-methods"></a>Beispiel: Eigenschaften und Methoden

Das folgende Beispiel enthält einen Typ, der Beispiele für Felder, Eigenschaften, private Funktionen und eine statische Methode enthält.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Siehe auch

- [Mitglieder](index.md)
