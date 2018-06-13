---
title: Klassen (F#)
description: Erfahren Sie, wie Klassen F#-Typen sind, die Objekte darstellen, die Eigenschaften, Methoden und Ereignisse aufweisen können.
ms.date: 05/16/2016
ms.openlocfilehash: 67164bd9f91c14f465bf05630259ad70cb8d90e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565885"
---
# <a name="classes"></a>Klassen

*Klassen* sind Typen, die Objekte darstellen, die Eigenschaften, Methoden und Ereignisse aufweisen können.


## <a name="syntax"></a>Syntax

```fsharp
// Class definition:
type [access-modifier] type-name [type-params] [access-modifier] ( parameter-list ) [ as identifier ] =
[ class ]
[ inherit base-type-name(base-constructor-args) ]
[ let-bindings ]
[ do-bindings ]
member-list
...
[ end ]
// Mutually recursive class definitions:
type [access-modifier] type-name1 ...
and [access-modifier] type-name2 ...
...
```

## <a name="remarks"></a>Hinweise
Klassen stellen die grundlegende Beschreibung des .NET Objekttypen; die Klasse ist der primäre Typkonzept, das objektorientierte Programmierung in f# unterstützt.

In der vorherigen Syntax der `type-name` ist gültiger Bezeichner. Die `type-params` beschreibt optionale generische Typparameter. Er besteht aus Typparameternamen und Einschränkungen, die in spitzen Klammern eingeschlossen (`<` und `>`). Weitere Informationen finden Sie unter [Generika](generics/index.md) und [Einschränkungen](generics/constraints.md). Die `parameter-list` beschreibt Konstruktorparameter. Der erste Zugriffsmodifizierer bezieht sich auf den Typ; die zweite bezieht sich auf den primären Konstruktor. In beiden Fällen ist die Standardeinstellung `public`.

Sie geben die Basisklasse für eine Klasse mit dem `inherit` Schlüsselwort. Sie müssen die Argumente in Klammern ein, für den Konstruktor der Basisklasse angeben.

Deklarieren Sie Felder oder Werte, die lokal auf die Klasse mithilfe von Funktion `let` Bindungen, und Sie müssen die allgemeinen Regeln für folgen `let` Bindungen. Die `do-bindings` Abschnitt enthält Code, der bei der objekterstellung ausgeführt werden.

Die `member-list` besteht aus zusätzliche Konstruktoren, Instanz und statische Methodendeklarationen Schnittstellendeklarationen, abstrakte Bindungen und -Eigenschaft und Ereignis-Deklarationen. Diese Angaben werden in [Elemente](members/index.md).

Die `identifier` wird, mit dem optionalen `as` Schlüsselwort weist einen Namen der Instanzvariablen oder Selbstbezeichner, die in der Typdefinition verwendet werden kann, um auf die Instanz des Typs verweisen. Weitere Informationen finden Sie unter dem Abschnitt Selbstbezeichner weiter unten in diesem Thema.

Die Schlüsselwörter `class` und `end` , die markiert des Beginns und Ende der Definition sind optional.

Wechselseitig rekursive-Typen, die Typen, die aufeinander verweisen sind, werden zusammen mit verknüpft die `and` Schlüsselwort ebenso wie wechselseitig rekursive Funktionen sind. Ein Beispiel finden Sie im Abschnitt Wechselseitig Rekursive Typen.


## <a name="constructors"></a>Konstruktoren
Der Konstruktor ist Code, der eine Instanz des Klassentyps erstellt. Konstruktoren für Klassen funktioniert etwas anders in f# als in anderen Sprachen .NET ausführen. In einer F#-Klasse, ist immer ein primärer Konstruktor, dessen Argumente sind in beschrieben, die `parameter-list` , folgt den vollständigen Typnamen sowie besteht, dessen Text den `let` (und `let rec`) Bindungen am Anfang der Klassendeklaration, und die `do`Bindungen, die folgen. Die Argumente des Konstruktors primären sind im Gültigkeitsbereich der Klassendeklaration.

Sie können zusätzliche Konstruktoren hinzufügen, indem Sie mit der `new` Schlüsselwort, um ein Element wie folgt hinzufügen:

`new`(`argument-list`) = `constructor-body`

Der Hauptteil der neue Konstruktor muss den primären Konstruktor aufrufen, der am oberen Rand der Klassendeklaration angegeben wird.

Das folgende Beispiel veranschaulicht dieses Konzept. Im folgenden Code `MyClass` verfügt über zwei Konstruktoren, ein primärer Konstruktor, der zwei Argumente und einen anderen Konstruktor, die akzeptiert akzeptiert keine Argumente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]
    
## <a name="let-and-do-bindings"></a>Teilen Sie und do-Bindungen

Die `let` und `do` Bindungen in einer Klassendefinition bilden den Hauptteil der primären Klassenkonstruktor, und daher ausgeführt, wenn eine Instanz der Klasse erstellt wird. Wenn eine `let` Bindung ist eine Funktion, und klicken Sie dann in einen Member kompiliert wird. Wenn die `let` Bindung ist ein Wert, der nicht in einer Funktion oder Member verwendet wird, und klicken Sie dann in eine Variable, die lokal an den Konstruktor kompiliert wird. Andernfalls wird es in ein Feld der Klasse kompiliert. Die `do` Ausdrücke, die folgen, werden in den primären Konstruktor kompiliert, und führen Sie Initialisierungscode für jede Instanz. Da keine zusätzlichen Konstruktoren immer den primären Konstruktor aufrufen der `let` Bindungen und `do` Bindungen immer ausgeführt, unabhängig davon, welche Konstruktor aufgerufen wird.

Durch die erstellte Felder `let` Bindungen in den Methoden und Eigenschaften der Klasse zugegriffen werden können; allerdings sie können nicht zugegriffen werden statische Methoden, auch wenn die statische Methoden eine Instanzvariablen als Parameter akzeptieren. Darauf können nicht zugegriffen werden mithilfe des Selbstbezeichners, falls vorhanden.


## <a name="self-identifiers"></a>Selbstbezeichner

Ein *Selbstbezeichner* ist ein Name, der die aktuelle Instanz darstellt. Selbstbezeichner ähneln den `this` -Schlüsselwort in c# oder C++ oder `Me` in Visual Basic. Sie können einen Selbstbezeichner definieren, auf zwei unterschiedliche Arten, je nachdem, ob den Selbstbezeichner im Bereich für die gesamte Klassendefinition oder nur für eine einzelne Methode werden soll.

Um einen Selbstbezeichner für die gesamte Klasse zu definieren, verwenden die `as` Schlüsselwort nach der schließenden Klammer des Konstruktorparameters aus, und geben Sie den Namen des Bezeichners.

Geben Sie einen Selbstbezeichner für nur eine Methode definieren, des Selbstbezeichners in der Memberdeklaration unmittelbar vor dem Methodennamen und einen Punkt (.) als Trennzeichen ein.

Im folgenden Codebeispiel wird veranschaulicht, die zwei Möglichkeiten, einen Selbstbezeichner zu erstellen. In der ersten Zeile der `as` Schlüsselwort wird verwendet, um der Selbstbezeichner definieren. In der fünften Zeile wird der Bezeichner `this` wird verwendet, um einen Selbstbezeichner definieren, deren Bereich beschränkt auf die Methode ist `PrintMessage`.

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

Im Gegensatz zu können in anderen .NET-Sprachen Sie den Selbstbezeichner name beliebig; Sie sind nicht eingeschränkten Namen wie z. B. `self`, `Me`, oder `this`.

Der Selbstbezeichner, die mit deklariert wird die `as` Schlüsselwort wird nicht initialisiert, bis nach der `let` Bindungen ausgeführt werden. Es kann nicht aus diesem Grund verwendet werden, der `let` Bindungen. Sie können den Selbstbezeichner in der `do` im Abschnitt über Bindungen.


## <a name="generic-type-parameters"></a>Generische Typparameter

Generische Typparameter in spitzen Klammern angegeben werden (`<` und `>`), in Form eines einfachen Anführungszeichens gefolgt von einem Bezeichner. Mehrere generischen Typparameter sind durch Kommas getrennt. Der generische Typparameter ist der Gültigkeitsbereich der Deklaration. Im folgenden Codebeispiel wird veranschaulicht, wie an generischer Typparameter.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

Typargumente werden hergeleitet, wenn der Typ verwendet wird. Im folgenden Code ist der abgeleitete Typ eine Sequenz von Tupeln.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]
    
## <a name="specifying-inheritance"></a>Angeben von Vererbung

Die `inherit` -Klausel kennzeichnet die direkte Basisklasse aus, sofern vorhanden. In F# erläutert werden ist nur eine direkte Basisklasse zulässig. Schnittstellen, die eine Klasse implementiert, werden die Basisklassen nicht berücksichtigt. Schnittstellen werden in erläutert die [Schnittstellen](Interfaces.md) Thema.

Sie können die Methoden und Eigenschaften der Basisklasse der abgeleiteten Klasse zugreifen, mit dem Programmiersprachen-Schlüsselwort `base` als Bezeichner an, gefolgt von einem Punkt (.) und den Namen des Elements.

Weitere Informationen finden Sie unter [Vererbung](inheritance.md).


## <a name="members-section"></a>Abschnitt "Mitglieder"
In diesem Abschnitt können Sie statische oder Instanzmethoden, Eigenschaften, schnittstellenimplementierungen, abstrakte Member, Ereignisdeklarationen und zusätzliche Konstruktoren definieren. Können, und führen Sie Bindungen darf nicht in diesem Abschnitt. Da eine Vielzahl von f#-Typen, zusätzlich zu den Klassen Elemente hinzugefügt werden können, diese in einem separaten Thema behandelt [Elemente](members/index.md).


## <a name="mutually-recursive-types"></a>Wechselseitig rekursive Typen
Wenn Sie Typen, die miteinander in einer kreisförmigen Weise verweisen definieren, Sie Zeichenfolge zusammen die Typdefinitionen unter Verwendung der `and` Schlüsselwort. Die `and` -Schlüsselwort ersetzt die `type` Schlüsselwort für alle außer der ersten Definition wie folgt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

Die Ausgabe ist eine Liste aller Dateien im aktuellen Verzeichnis.


## <a name="when-to-use-classes-unions-records-and-structures"></a>Verwenden von Klassen, Unions, Datensätze und Strukturen
Angesichts der Vielzahl von Typen zur Auswahl, müssen Sie genau verstehen, was für jeden Typ entwickelt wurde, um den geeigneten Typ für eine bestimmte Situation auszuwählen. Klassen sind für die Verwendung in objektorientierten Programmierung Kontexten vorgesehen. Objektorientierte Programmierung ist der bestimmende Paradigma in Anwendungen, die für .NET Framework geschrieben wurden verwendet. Wenn der f#-Code hat enge Zusammenarbeit mit .NET Framework oder einer anderen objektorientierten Bibliothek ermöglicht und besonders, wenn Sie z. B. eine UI-Bibliothek eine objektorientierte Typsystem erweitern müssen, Klassen eignen sich wahrscheinlich.

Wenn Sie nicht eng mit dem objektorientierten Code Zusammenwirken mit sind oder wenn Sie Code schreiben, die eigenständig und daher über häufige Interaktion mit Code mit dem objektorientierten geschützt ist, Sie sollten erwägen, Datensätze und Unterscheidungs-Unions. Eine einzelne, gut, um herauszufinden,: Out Unterscheidungs-Union, zusammen mit den entsprechenden Code für den Musterabgleich häufig als eine einfachere Alternative zu einer Objekthierarchie verwendet werden kann. Weitere Informationen zu Unterscheidungs-Unions, finden Sie unter [Unterscheidungs-Unions](discriminated-unions.md).

Datensätze haben den Vorteil, dass er einfacher als Klassen allerdings Datensätze sind nicht geeignet, wenn die Anforderungen eines Typs überschreiten, was mit ihren Einfachheit erreicht werden kann. Datensätze sind im Grunde einfache Aggregate für Werte ohne separate Konstruktoren, die benutzerdefinierte Aktionen ausführen können, ohne ausgeblendete Felder und ohne Vererbung oder schnittstellenimplementierungen. Auch Elemente wie z. B. Eigenschaften und Methoden auf Datensätze, deren Verhalten zu komplizieren hinzugefügt werden können, werden die Felder in einem Datensatz gespeichert nach wie vor ein einfaches Aggregat von Werten. Weitere Informationen zu Datensätzen finden Sie unter [Datensätze](records.md).

Strukturen sind auch nützlich für kleine Datenaggregate, aber sie unterscheiden sich von Klassen und Datensätzen insofern, dass sie .NET Werttypen sind. Klassen und Datensätzen sind .NET Verweistypen. Die Semantik von Werttypen und Verweistypen unterscheiden sich insofern, dass Werttypen als Wert übergeben werden. Dies bedeutet, dass sie kopiert werden bit für Bit, wenn sie als Parameter übergeben oder von einer Funktion zurückgegeben werden. Sie werden auch auf dem Stapel gespeichert oder, wenn sie als ein Feld, in das übergeordnete Objekt anstelle von eingebetteten verwendet werden, die in eigenen Position auf dem Heap gespeichert sind. Strukturen sind deshalb für häufig verwendete Daten geeignet, wenn der Aufwand für den Zugriff auf den Heap ein Problem aufgetreten ist. Weitere Informationen über Strukturen finden Sie unter [Strukturen](structures.md).


## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Mitglieder](members/index.md)

[Vererbung](inheritance.md)

[Schnittstellen](interfaces.md)

