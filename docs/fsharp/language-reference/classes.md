---
title: Klassen (F#)
description: Erfahren Sie, wie Klassen F#-Typen sind, die Objekte darstellen, die Eigenschaften, Methoden und Ereignisse aufweisen können.
ms.date: 05/16/2016
ms.openlocfilehash: 71cd713d192d28565e879b79b2fc9e0530e5f841
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035232"
---
# <a name="classes"></a>Klassen

*Klassen* sind Typen, die Objekte darstellen, Eigenschaften, Methoden und Ereignisse verfügen können.

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

Klassen stellen die grundlegende Beschreibung von .NET Objekttypen dar; die Klasse ist das primäre Konzept, das objektorientierte Programmierung in f# unterstützt.

In der vorherigen Syntax wird die `type-name` ist gültige Bezeichner. Die `type-params` beschreibt optionale generische Typparameter. Es besteht aus Typparameternamen und Einschränkungen, die in spitze Klammern eingeschlossen (`<` und `>`). Weitere Informationen finden Sie unter [Generika](generics/index.md) und [Einschränkungen](generics/constraints.md). Die `parameter-list` Konstruktorparameter beschreibt. Der erste Zugriffsmodifizierer bezieht sich auf den Typ; die zweite bezieht sich auf den primären Konstruktor. In beiden Fällen ist die Standardeinstellung `public`.

Sie geben die Basisklasse für eine Klasse, mit der `inherit` Schlüsselwort. Sie müssen die Argumente in Klammern ein, für den Konstruktor der Basisklasse angeben.

Sie deklarieren Sie Felder oder Werte, die lokal auf der Klasse mithilfe der werden Funktion `let` Bindungen, und Sie müssen die allgemeinen Regeln für folgen `let` Bindungen. Die `do-bindings` Abschnitt enthält Code, der bei der objekterstellung ausgeführt werden.

Die `member-list` besteht aus zusätzliche Konstruktoren, Instanz und statische Methodendeklarationen, Deklarationen von Schnittstellen, abstrakten Bindungen und -Eigenschaft und Ereignis-Deklarationen. Diese werden beschrieben [Mitglieder](members/index.md).

Die `identifier` wird, mit dem optionalen `as` Schlüsselwort vergibt einen Namen für die Instanzvariable oder Selbstbezeichner, die in der Typdefinition verwendet werden können, um auf die Instanz des Typs verweisen. Weitere Informationen finden Sie im Abschnitt "Self-IDs" weiter unten in diesem Thema.

Die Schlüsselwörter `class` und `end` zu markieren, die den Beginn und Ende der Definition sind optional.

Wechselseitig rekursive-Typen, die Typen, die aufeinander verweisen sind, werden zusammen mit verknüpft die `and` Schlüsselwort wie wechselseitig rekursive Funktionen sind. Ein Beispiel finden Sie im Abschnitt Wechselseitig Rekursive Typen.

## <a name="constructors"></a>Konstruktoren

Der Konstruktor ist Code, der eine Instanz des Klassentyps erstellt wird. Konstruktoren für Klassen funktionieren etwas anders in F# erläutert werden, als Sie dies, in anderen .NET-Sprachen tun. In einer F#-Klasse ist immer ein primärer Konstruktor, deren Argumente finden Sie unter, den `parameter-list` , folgt den Typnamen, und, dessen Text besteht aus den `let` (und `let rec`) Bindungen am Anfang der Klassendeklaration und der `do`Bindungen, die folgen. Die Argumente des primären Konstruktors sind im Gültigkeitsbereich der Deklaration der Klasse.

Sie können zusätzliche Konstruktoren hinzufügen, indem Sie mit der `new` Schlüsselwort, um ein Element wie folgt hinzufügen:

`new`(`argument-list`) = `constructor-body`

Der Text, der der neue Konstruktor muss den primären Konstruktor aufrufen, der am oberen Rand der Klassendeklaration angegeben wird.

Das folgende Beispiel veranschaulicht dieses Konzept. In den folgenden Code `MyClass` besitzt zwei Konstruktoren, ein primärer Konstruktor, der zwei Argumente und ein anderer Konstruktor akzeptiert keine Argumente akzeptiert.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]

## <a name="let-and-do-bindings"></a>Lassen Sie und do-Bindungen

Die `let` und `do` Bindungen in eine Klassendefinition bilden den Text des primären Klassenkonstruktor, und daher ausgeführt, wenn eine Instanz der Klasse erstellt wird. Wenn eine `let` Bindung ist eine Funktion, und klicken Sie dann in einem Member kompiliert wird. Wenn die `let` Bindung ist ein Wert, der nicht in einer Funktion oder Member verwendet wird, und klicken Sie dann in eine Variable, die lokal an den Konstruktor ist kompiliert wird. Andernfalls wird es in ein Feld der Klasse kompiliert. Die `do` Ausdrücke, die folgen, werden die in den primären Konstruktor kompiliert werden, und führen Sie Code für die Initialisierung für jede Instanz. Da keine zusätzlichen Konstruktoren immer den primären Konstruktor, rufen Sie die `let` Bindungen und `do` Bindungen immer ausgeführt, unabhängig davon, welche Konstruktor aufgerufen wird.

Felder, die vom erstellten `let` Bindungen in den Methoden und Eigenschaften der Klasse zugegriffen werden können; jedoch, sie können nicht zugegriffen werden statische Methoden, selbst wenn die statischen Methoden eine Instanzvariable als Parameter akzeptieren. Sie können nicht zugegriffen werden mithilfe des Selbstbezeichners, sofern vorhanden.

## <a name="self-identifiers"></a>Selbstbezeichner

Ein *Selbstbezeichner* ist ein Name, der die aktuelle Instanz darstellt. Selbstbezeichner ähneln den `this` -Schlüsselwort in c# oder C++ oder `Me` in Visual Basic. Sie können einen Selbstbezeichner definieren, zwei Möglichkeiten, je nachdem, ob den Selbstbezeichner im Bereich für die gesamte Klassendefinition oder nur für eine einzelne Methode liegen soll.

Um einen Selbstbezeichner für die gesamte Klasse zu definieren, verwenden die `as` Schlüsselwort nach der schließenden Klammer des Konstruktorparameters aus, und geben Sie den Namen des Bezeichners.

Geben Sie zum Definieren eines Selbstbezeichners für nur eine Methode des Selbstbezeichners in der Element-Deklaration wird unmittelbar vor dem Methodennamen und einen Punkt (.) als Trennzeichen ein.

Im folgenden Codebeispiel wird veranschaulicht, die zwei Möglichkeiten, eine Self-ID zu erstellen. In der ersten Zeile der `as` -Schlüsselwort wird verwendet, um der Selbstbezeichner zu definieren. In der fünften Zeile, die den Bezeichner `this` wird verwendet, um einen Selbstbezeichner definieren, deren Bereich auf die Methode ist `PrintMessage`.

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

Im Gegensatz zu können in anderen, den Selbstbezeichner weisen Sie beliebig; Sie sind nicht darauf beschränkt Namen wie z. B. `self`, `Me`, oder `this`.

Der Selbstbezeichner, die mit deklariert ist die `as` Schlüsselwort ist nicht initialisiert. erst nach der `let` Bindungen ausgeführt. Es kann nicht aus diesem Grund verwendet werden, der `let` Bindungen. Sie können den Selbstbezeichner in die `do` im Abschnitt über Bindungen.

## <a name="generic-type-parameters"></a>Generische Typparameter

Generische Typparameter in spitzen Klammern angegeben sind (`<` und `>`), in Form von einem einfachen Anführungszeichen, ein Bezeichner folgen. Es sind mehrere generische Typparameter durch Kommas getrennt. Der generische Typparameter ist der Gültigkeitsbereich der Deklaration. Im folgenden Codebeispiel wird veranschaulicht, wie generische Typparameter angeben wird.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

Typargumente abgeleitet werden, wenn der Typ verwendet wird. Im folgenden Code wird der abgeleitete Typ eine Sequenz von Tupeln.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]

## <a name="specifying-inheritance"></a>Angeben von Vererbung

Die `inherit` -Klausel kennzeichnet die direkte Basisklasse aus, sofern vorhanden. In f# ist nur eine direkte Basisklasse zulässig. Eine Klasse implementierten Schnittstellen werden Basisklassen nicht berücksichtigt werden. Schnittstellen werden in erläutert die [Schnittstellen](Interfaces.md) Thema.

Sie können die Methoden und Eigenschaften der Basisklasse aus der abgeleiteten Klasse zugreifen, mit dem Programmiersprachen-Schlüsselwort `base` als Bezeichner an, gefolgt von einem Punkt (.) und den Namen des Members.

Weitere Informationen finden Sie unter [Vererbung](inheritance.md).

## <a name="members-section"></a>Abschnitt "Mitglieder"

Sie können statische oder Instanzmethoden, Eigenschaften, schnittstellenimplementierungen, abstrakte Member, Ereignisdeklarationen und zusätzliche Konstruktoren definieren, in diesem Abschnitt. Können und werden Bindungen können nicht angezeigt, in diesem Abschnitt. Da Mitglieder mit einer Vielzahl von f#-Typen, zusätzlich zu den Klassen hinzugefügt werden können, werden diese in einem separaten Thema behandelt [Mitglieder](members/index.md).

## <a name="mutually-recursive-types"></a>Wechselseitig rekursive Typen

Wenn Sie Typen, die aufeinander in einer kreisförmigen Weise verweisen definieren, Sie Zeichenfolge zusammen die Typdefinitionen unter Verwendung der `and` Schlüsselwort. Die `and` -Schlüsselwort ersetzt die `type` Schlüsselwort für alle mit Ausnahme der ersten Definition wie folgt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

Die Ausgabe ist eine Liste aller Dateien im aktuellen Verzeichnis.

## <a name="when-to-use-classes-unions-records-and-structures"></a>Verwenden von Klassen, Unions, Datensätze und Strukturen

Wenn die verschiedenen Arten von verbindungsanbietern, benötigen Sie einen fundierten Überblick darüber, was für jeden Typ entwickelt wurde, den entsprechenden Typ für eine bestimmte Situation auswählen. Klassen dienen zur Verwendung in der objektorientierten Programmierung Kontexte. Objektorientierte Programmierung ist das vorherrschende Paradigma in Anwendungen, die für .NET Framework geschrieben wurden verwendet. Wenn der F#-Code arbeiten eng mit .NET Framework oder einer anderen objektorientierten-Bibliothek zu und insbesondere dann, wenn man von einem System mit objektorientierten Typ wie z. B. eine UI-Bibliothek zu erweitern, sind Klassen vermutlich geeignet.

Wenn Sie nicht eng mit objektorientiertem Code Zusammenwirken sind oder wenn Sie Code schreiben, die eigenständig und daher vor häufige Interaktion mit objektorientiertem Code geschützt ist, Sie sollten auf Datensätze und Unterscheidungs-Unions. Eine einzelne auch Überlegungen – Out Unterscheidungs-Union, zusammen mit den entsprechenden Code für den Musterabgleich häufig als eine einfachere Alternative zu einer Objekthierarchie verwendet werden kann. Weitere Informationen zu Unterscheidungs-Unions, finden Sie unter [Unterscheidungs-Unions](discriminated-unions.md).

Datensätze haben den Vorteil, dass er als Klassen einfacher, aber die Einträge sind nicht geeignet, wenn die Anforderungen eines Typs überschreiten, was mit ihrer Einfachheit erreicht werden kann. Datensätze sind im Grunde einfache Aggregate von Werten ohne separate Konstruktoren, die benutzerdefinierte Aktionen ausführen können, ohne die ausgeblendete Felder und ohne Vererbung oder schnittstellenimplementierungen. Obwohl die Datensätze, deren Verhalten komplexer machen Member wie etwa Eigenschaften und Methoden hinzugefügt werden können, sind die Felder, die in einem Datensatz gespeichert noch ein einfaches Aggregat von Werten. Weitere Informationen zu Datensätzen finden Sie unter [Datensätze](records.md).

Strukturen sind auch nützlich für kleine Datenaggregate, aber sie unterscheiden sich von Klassen und Datensätzen, dass sie .NET Werttypen sind. Klassen und Datensätzen sind Verweistypen für .NET. Die Semantik für Werttypen und Verweistypen unterscheiden sich, dass Werttypen als Wert übergeben werden. Dies bedeutet, dass sie kopiert werden bit für Bit-Version, wenn sie als Parameter übergeben oder von einer Funktion zurückgegeben werden. Sie sind auch auf dem Stapel gespeichert oder, wenn sie als ein Feld, das innerhalb des übergeordneten Objekts anstelle von eingebetteten verwendet werden, die in ihre eigenen separaten Speicherort auf dem Heap gespeichert sind. Aus diesem Grund sind die Strukturen für häufig verwendete Daten geeignet, wenn der Aufwand für den Zugriff auf den Heap ein Problem aufgetreten ist. Weitere Informationen über Strukturen finden Sie unter [Strukturen](structures.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Mitglieder](members/index.md)
- [Vererbung](inheritance.md)
- [Schnittstellen](interfaces.md)
