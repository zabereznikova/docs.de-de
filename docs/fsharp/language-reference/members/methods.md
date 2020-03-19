---
title: Methoden
description: Erfahren Sie, wie eine F-Methode eine Funktion ist, die einem Typ zugeordnet ist, der zum Verfügbarmachen und Implementieren der Funktionalität und des Verhaltens von Objekten und Typen verwendet wird.
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401064"
---
# <a name="methods"></a>Methoden

Eine *Methode* ist eine Funktion, die einem Typ zugeordnet ist. In der objektorientierten Programmierung werden Methoden verwendet, um die Funktionalität und das Verhalten von Objekten und Typen verfügbar zu machen und zu implementieren.

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

In der vorherigen Syntax können Sie die verschiedenen Formen von Methodendeklarationen und -definitionen anzeigen. In längeren Methodenkörpern folgt ein Zeilenumbruch dem Gleichheitszeichen (=), und der gesamte Methodenkörper wird eingerückt.

Attribute können auf jede Methodendeklaration angewendet werden. Sie gehen der Syntax für eine Methodendefinition voran und werden in der Regel in einer separaten Zeile aufgeführt. Weitere Informationen finden Sie unter [Attribute](../attributes.md).

Methoden können `inline`markiert werden. Informationen zu `inline` finden Sie unter [Inlinefunktionen](../functions/inline-functions.md).

Nicht-Inline-Methoden können rekursiv innerhalb des Typs verwendet werden. Es besteht keine Notwendigkeit, `rec` das Schlüsselwort explizit zu verwenden.

## <a name="instance-methods"></a>Instanzmethoden

Instanzmethoden werden mit `member` dem Schlüsselwort und einem *Selbstbezeichner*deklariert, gefolgt von einem Punkt (.) und dem Methodennamen und den Parametern. Wie bei `let` Bindungen kann die *Parameterliste* ein Muster sein. In der Regel schließen Sie Methodenparameter in Klammern in ein Tupelformular ein, d. h. die Art und Weise, wie Methoden in F- angezeigt werden, wenn sie in anderen .NET Framework-Sprachen erstellt werden. Die Curryform (Parameter, die durch Leerzeichen getrennt sind) ist jedoch ebenfalls üblich, und andere Muster werden ebenfalls unterstützt.

Das folgende Beispiel veranschaulicht die Definition und Verwendung einer nicht abstrakten Instanzmethode.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

Verwenden Sie innerhalb von Instanzmethoden nicht den Selbstbezeichner, um auf Felder zuzugreifen, die mithilfe von let-Bindungen definiert wurden. Verwenden Sie den Selbstbezeichner, wenn Sie auf andere Member und Eigenschaften zugreifen.

## <a name="static-methods"></a>Statische Methoden

Das `static` Schlüsselwort wird verwendet, um anzugeben, dass eine Methode ohne Instanz aufgerufen werden kann und keiner Objektinstanz zugeordnet ist. Andernfalls sind Methoden Instanzmethoden.

Das Beispiel im nächsten Abschnitt zeigt `let` Felder, die mit `member` dem Schlüsselwort deklariert wurden, Eigenschaftenmember, die mit dem Schlüsselwort deklariert wurden, und eine statische Methode, die mit dem `static` Schlüsselwort deklariert wurde.

Das folgende Beispiel veranschaulicht die Definition und Verwendung statischer Methoden. Angenommen, diese Methodendefinitionen `SomeType` befinden sich in der Klasse im vorherigen Abschnitt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Abstrakte und virtuelle Methoden

Das `abstract` Schlüsselwort gibt an, dass eine Methode über einen virtuellen Dispatch-Slot und möglicherweise keine Definition in der Klasse verfügt. Ein *virtueller Dispatch-Slot* ist ein Eintrag in einer intern verwalteten Funktionstabelle, der zur Laufzeit zum Nachschlagen virtueller Funktionsaufrufe in einem objektorientierten Typ verwendet wird. Der virtuelle Dispatch-Mechanismus ist der Mechanismus, der *Polymorphismus*implementiert, ein wichtiges Merkmal der objektorientierten Programmierung. Eine Klasse, die über mindestens eine abstrakte Methode ohne Definition verfügt, ist eine *abstrakte Klasse,* was bedeutet, dass keine Instanzen dieser Klasse erstellt werden können. Weitere Informationen zu abstrakten Klassen finden Sie unter [Abstrakte Klassen](../abstract-classes.md).

Abstrakte Methodendeklarationen enthalten keinen Methodentext. Stattdessen folgt auf den Namen der Methode ein Doppelpunkt (:) und eine Typsignatur für die Methode. Die Typsignatur einer Methode entspricht der von IntelliSense angezeigten, wenn Sie den Mauszeiger über einen Methodennamen im Visual Studio-Code-Editor anhalten, außer ohne Parameternamen. Typsignaturen werden auch vom Interpreter fsi.exe angezeigt, wenn Sie interaktiv arbeiten. Die Typsignatur einer Methode wird gebildet, indem die Typen der Parameter aufgelistet werden, gefolgt vom Rückgabetyp mit entsprechenden Trennzeichen. Curry-Parameter werden `->` durch und Tupelparameter `*`durch getrennt. Der Rückgabewert wird immer durch `->` ein Symbol von den Argumenten getrennt. Klammern können verwendet werden, um komplexe Parameter zu gruppieren, z. B. wenn ein Funktionstyp ein Parameter ist, oder um anzugeben, wann ein Tupel als einzelner Parameter und nicht als zwei Parameter behandelt wird.

Sie können auch abstrakte Methoden Standarddefinitionen geben, indem `default` Sie die Definition zur Klasse hinzufügen und das Schlüsselwort verwenden, wie im Syntaxblock in diesem Thema gezeigt. Eine abstrakte Methode mit einer Definition in derselben Klasse entspricht einer virtuellen Methode in anderen .NET Framework-Sprachen. Unabhängig davon, ob eine `abstract` Definition vorhanden ist oder nicht, erstellt das Schlüsselwort einen neuen Dispatch-Slot in der virtuellen Funktionstabelle für die Klasse.

Unabhängig davon, ob eine Basisklasse ihre abstrakten Methoden implementiert, können abgeleitete Klassen Implementierungen abstrakter Methoden bereitstellen. Um eine abstrakte Methode in einer abgeleiteten Klasse zu implementieren, definieren Sie eine `override` Methode, die denselben Namen und dieselbe Signatur in der abgeleiteten Klasse hat, außer verwenden Sie das schlüsselwortgebende Wort, `default` und stellen Sie den Methodentext bereit. Die `override` Schlüsselwörter `default` und bedeuten genau das gleiche. Verwenden `override` Sie diese Methode, wenn die neue Methode eine Basisklassenimplementierung überschreibt. verwenden `default` Sie, wenn Sie eine Implementierung in derselben Klasse wie die ursprüngliche abstrakte Deklaration erstellen. Verwenden Sie `abstract` das Schlüsselwort nicht für die Methode, die die Methode implementiert, die in der Basisklasse als abstrakt deklariert wurde.

Im folgenden Beispiel wird `Rotate` eine abstrakte Methode mit einer Standardimplementierung veranschaulicht, die einer virtuellen .NET Framework-Methode entspricht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

Das folgende Beispiel veranschaulicht eine abgeleitete Klasse, die eine Basisklassenmethode überschreibt. In diesem Fall ändert die Außerkraftsetzung das Verhalten, sodass die Methode nichts bewirkt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Überladene Methoden

Überladene Methoden sind Methoden, die identische Namen in einem bestimmten Typ haben, aber unterschiedliche Argumente aufweisen. Optionale Argumente werden in der Regel anstelle von überladenen Methoden verwendet. Überladene Methoden sind jedoch in der Sprache zulässig, vorausgesetzt, die Argumente sind in Tupelform und nicht in Curryform.

## <a name="optional-arguments"></a>Optionale Argumente

Ab F-4.1 können Sie auch optionale Argumente mit einem Standardparameterwert in Methoden haben.  Dies soll die Zusammenarbeit mit dem Code von C-Code erleichtern.  Im folgenden Beispiel wird die Syntax veranschaulicht:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Beachten Sie, dass `DefaultParameterValue` der übergebene Wert mit dem Eingabetyp übereinstimmen muss.  In der obigen Stichprobe `int`ist es eine .  Der Versuch, einen Nicht-Ganzzahlwert `DefaultParameterValue` zu übergeben, würde zu einem Kompilierungsfehler führen.

## <a name="example-properties-and-methods"></a>Beispiel: Eigenschaften und Methoden

Das folgende Beispiel enthält einen Typ mit Beispielen für Felder, private Funktionen, Eigenschaften und eine statische Methode.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Weitere Informationen

- [Mitglieder](index.md)
