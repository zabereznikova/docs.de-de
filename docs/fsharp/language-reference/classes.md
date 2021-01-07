---
title: Klassen
description: 'Erfahren Sie, wie F #-Klassentypen sind, die Objekte darstellen, die Eigenschaften, Methoden und Ereignisse aufweisen können.'
ms.date: 05/16/2016
ms.openlocfilehash: fd6638e0f1c08cf667a73582e19b2bb5bba46e20
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970166"
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

## <a name="remarks"></a>Bemerkungen

Klassen stellen die grundlegende Beschreibung von .NET-Objekttypen dar. bei der-Klasse handelt es sich um das primäre Typkonzept, das die objektorientierte Programmierung in F # unterstützt.

In der vorangehenden Syntax `type-name` ist ein beliebiger gültiger Bezeichner. `type-params`Beschreibt optionale generische Typparameter. Sie besteht aus Typparameter Namen und Einschränkungen in spitzen Klammern ( `<` und `>` ). Weitere Informationen finden Sie unter [Generika](./generics/index.md) und [Einschränkungen](./generics/constraints.md). `parameter-list`Beschreibt die Konstruktorparameter. Der erste Zugriffsmodifizierer bezieht sich auf den-Typ. die zweite bezieht sich auf den primären Konstruktor. In beiden Fällen ist der Standardwert `public` .

Sie geben die Basisklasse für eine Klasse an, indem Sie das- `inherit` Schlüsselwort verwenden. Sie müssen Argumente in Klammern für den Basisklassenkonstruktor angeben.

Sie deklarieren Felder oder Funktions Werte, die für die Klasse lokal sind `let` , mithilfe von Bindungen, und Sie müssen die allgemeinen Regeln für `let` Bindungen befolgen. Der- `do-bindings` Abschnitt enthält Code, der bei der Objekt Erstellung ausgeführt werden soll.

Das `member-list` besteht aus zusätzlichen Konstruktoren, Instanzen und statischen Methoden Deklarationen, Schnittstellen Deklarationen, abstrakten Bindungen und Eigenschaften-und Ereignis Deklarationen. Diese werden in [Members](./members/index.md)beschrieben.

Der `identifier` , der mit dem optionalen `as` Schlüsselwort verwendet wird, gibt einen Namen für die Instanzvariable oder den selbst Bezeichner an, der in der Typdefinition verwendet werden kann, um auf die Instanz des Typs zu verweisen. Weitere Informationen finden Sie im Abschnitt Self identifies weiter unten in diesem Thema.

Die Schlüsselwörter `class` und `end` , die den Anfang und das Ende der Definition markieren, sind optional.

Gegenseitig rekursive Typen, bei denen es sich um Typen handelt, die aufeinander verweisen, werden mit dem-Schlüsselwort verknüpft, ebenso `and` wie gegenseitig rekursive Funktionen. Ein Beispiel finden Sie im Abschnitt gegenseitig rekursive Typen.

## <a name="constructors"></a>Konstruktoren

Der Konstruktor ist ein Code, der eine Instanz des Klassen Typs erstellt. Konstruktoren für Klassen funktionieren in F # etwas anders als in anderen .NET-Sprachen. In einer F #-Klasse gibt es immer einen primären Konstruktor, dessen Argumente in der beschrieben werden, `parameter-list` der auf den Typnamen folgt und dessen Hauptteil aus den `let` Bindungen (und `let rec` ) am Anfang der Klassen Deklaration und den `do` folgenden Bindungen besteht. Die Argumente des primären Konstruktors liegen innerhalb der Klassen Deklaration im Gültigkeitsbereich.

Sie können zusätzliche Konstruktoren hinzufügen, indem Sie das- `new` Schlüsselwort verwenden, um ein Element wie folgt hinzuzufügen:

`new`(`argument-list`) = `constructor-body`

Der Hauptteil des neuen Konstruktors muss den primären Konstruktor aufrufen, der oben in der Klassen Deklaration angegeben wird.

Dieses Konzept wird im folgenden Beispiel veranschaulicht. Im folgenden Code `MyClass` verfügt über zwei Konstruktoren: einen primären Konstruktor, der zwei Argumente annimmt, und einen anderen Konstruktor, der keine Argumente annimmt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]

## <a name="let-and-do-bindings"></a>Let-und do-Bindungen

Die `let` `do` Bindungen und in einer Klassendefinition bilden den Hauptteil des Konstruktors der primären Klasse. Sie werden daher immer dann ausgeführt, wenn eine Klasseninstanz erstellt wird. Wenn eine `let` Bindung eine Funktion ist, wird Sie in einen Member kompiliert. Wenn die `let` Bindung ein Wert ist, der nicht in einer Funktion oder einem Member verwendet wird, wird Sie in eine lokale Variable für den Konstruktor kompiliert. Andernfalls wird Sie in ein-Feld der-Klasse kompiliert. Die `do` folgenden Ausdrücke werden in den primären Konstruktor kompiliert und führen Initialisierungs Code für jede Instanz aus. Da alle zusätzlichen Konstruktoren immer den primären Konstruktor aufrufen, werden die `let` Bindungen und `do` Bindungen immer ausgeführt, unabhängig davon, welcher Konstruktor aufgerufen wird.

Auf Felder, die durch Bindungen erstellt werden, `let` kann in den Methoden und Eigenschaften der-Klasse zugegriffen werden. auf Sie kann jedoch nicht von statischen Methoden aus zugegriffen werden, auch wenn die statischen Methoden eine Instanzvariable als Parameter annehmen. Auf Sie kann nicht mithilfe des selbst Bezeichners zugegriffen werden, wenn ein solcher vorhanden ist.

## <a name="self-identifiers"></a>Self-IDs

Ein *Self-Identifier* ist ein Name, der die aktuelle Instanz darstellt. Selbst Bezeichner ähneln dem- `this` Schlüsselwort in c# oder C++ oder `Me` in Visual Basic. Sie können einen Self-Identifier auf zwei verschiedene Arten definieren, je nachdem, ob der Self-Bezeichner im Gültigkeitsbereich für die gesamte Klassendefinition oder nur für eine einzelne Methode vorliegen soll.

Um einen selbst Bezeichner für die gesamte Klasse zu definieren, verwenden Sie das `as` -Schlüsselwort nach den schließenden Klammern der konstruktorparameterliste, und geben Sie den Bezeichnernamen an.

Um einen selbst Bezeichner für nur eine Methode zu definieren, geben Sie den selbst Bezeichner in der Element Deklaration an, direkt vor dem Methodennamen und einem Zeitraum (.) als Trennzeichen.

Im folgenden Codebeispiel werden die beiden Möglichkeiten zum Erstellen eines selbst Bezeichners veranschaulicht. In der ersten Zeile wird das `as` Schlüsselwort verwendet, um den selbst Bezeichner zu definieren. In der fünften Zeile wird der Bezeichner `this` verwendet, um einen selbst Bezeichner zu definieren, dessen Bereich auf die-Methode beschränkt ist `PrintMessage` .

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

Anders als bei anderen .NET-Sprachen können Sie den selbst Bezeichner nach Wunsch benennen. Sie sind nicht auf Namen wie `self` , oder beschränkt `Me` `this` .

Der selbst Bezeichner, der mit dem-Schlüsselwort deklariert wird, `as` wird erst nach dem Basiskonstruktor initialisiert. Daher wird bei Verwendung vor oder innerhalb des basiskonstruktors `System.InvalidOperationException: The initialization of an object or value resulted in an object or value being accessed recursively before it was fully initialized.` während der Laufzeit ausgelöst. Sie können den Self-Identifier nach dem Basiskonstruktor (z. b `let` . in Bindungen oder Bindungen) kostenlos verwenden `do` .

## <a name="generic-type-parameters"></a>Generische Typparameter

Generische Typparameter werden in spitzen Klammern ( `<` und `>` ) in Form eines einzelnen Anführungs Zeichens gefolgt von einem Bezeichner angegeben. Mehrere generische Typparameter werden durch Kommas getrennt. Der generische Typparameter befindet sich innerhalb der Deklaration im Gültigkeitsbereich. Im folgenden Codebeispiel wird gezeigt, wie generische Typparameter angegeben werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

Typargumente werden abgeleitet, wenn der Typ verwendet wird. Im folgenden Code ist der abherleitet Typ eine Sequenz von Tupeln.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]

## <a name="specifying-inheritance"></a>Angeben der Vererbung

Die- `inherit` Klausel identifiziert die direkte Basisklasse, sofern vorhanden. In F # ist nur eine direkte Basisklasse zulässig. Schnittstellen, die eine Klasse implementiert, werden nicht als Basisklassen angesehen. Schnittstellen werden im Thema " [Schnittstellen](Interfaces.md) " erläutert.

Sie können auf die Methoden und Eigenschaften der Basisklasse von der abgeleiteten Klasse aus zugreifen, indem Sie das Language-Schlüsselwort `base` als Bezeichner verwenden, gefolgt von einem Punkt (.) und dem Namen des Members.

Weitere Informationen finden Sie unter [Vererbung](inheritance.md).

## <a name="members-section"></a>Abschnitt "Mitglieder"

In diesem Abschnitt können Sie statische Methoden oder Instanzmethoden, Eigenschaften, Schnittstellen Implementierungen, abstrakte Member, Ereignis Deklarationen und zusätzliche Konstruktoren definieren. Let-und do-Bindungen können in diesem Abschnitt nicht angezeigt werden. Da Member zusätzlich zu Klassen zu einer Vielzahl von F #-Typen hinzugefügt werden [können, werden](./members/index.md)Sie in einem separaten Thema behandelt.

## <a name="mutually-recursive-types"></a>Gegenseitig rekursive Typen

Wenn Sie Typen definieren, die einander auf Zirkel Weise referenzieren, werden die Typdefinitionen mithilfe des- `and` Schlüssel Worts miteinander verknüpft. Das- `and` Schlüsselwort ersetzt das- `type` Schlüsselwort für alle außer der ersten Definition wie folgt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

Bei der Ausgabe handelt es sich um eine Liste aller Dateien im aktuellen Verzeichnis.

## <a name="when-to-use-classes-unions-records-and-structures"></a>Verwendungszwecke von Klassen, Unions, Datensätzen und Strukturen

Wenn Sie die verschiedenen Typen auswählen, die Sie auswählen können, benötigen Sie ein gutes Verständnis dafür, wofür die einzelnen Typen entworfen wurden, um den entsprechenden Typ für eine bestimmte Situation auszuwählen. Klassen sind für die Verwendung in objektorientierten Programmier Kontexten konzipiert. Die objektorientierte Programmierung ist das vorherrschende Paradigma, das in Anwendungen verwendet wird, die für die .NET Framework geschrieben wurden. Wenn der F #-Code eng mit dem .NET Framework oder einer anderen objektorientierten Bibliothek zusammenarbeiten muss, insbesondere, wenn Sie von einem objektorientierten Typsystem, z. b. einer UI-Bibliothek, erweitern müssen, sind Klassen wahrscheinlich geeignet.

Wenn Sie nicht eng mit objektorientiertem Code zusammenarbeiten oder wenn Sie Code schreiben, der eigenständig und daher vor häufigen Interaktionen mit objektorientiertem Code geschützt ist, sollten Sie die Verwendung von Datensätzen und Unterscheidungs-Unions in Erwägung gezogen. Eine einzelne, wohl gedachte –-Union, zusammen mit dem entsprechenden Muster Vergleichs Code, kann häufig als einfachere Alternative zu einer Objekthierarchie verwendet werden. Weitere Informationen zu Unterscheidungs-Unions finden Sie unter Unterscheidungs- [Unions](discriminated-unions.md).

Datensätze haben den Vorteil, dass Sie einfacher als Klassen sind, aber Datensätze sind nicht geeignet, wenn die Anforderungen eines Typs überschreiten, was mit der Einfachheit erreicht werden kann. Datensätze sind im Grunde einfache Aggregate von Werten ohne separate Konstruktoren, die benutzerdefinierte Aktionen ausführen können, ohne ausgeblendete Felder und ohne Vererbungs-oder Schnittstellen Implementierungen. Obwohl Elemente wie Eigenschaften und Methoden zu Datensätzen hinzugefügt werden können, um das Verhalten komplexer zu gestalten, sind die in einem Datensatz gespeicherten Felder weiterhin ein einfaches Aggregat von Werten. Weitere Informationen zu Datensätzen finden Sie unter [Datensätze](records.md).

Strukturen sind auch bei kleinen Daten Aggregaten nützlich, unterscheiden sich jedoch von Klassen und Datensätzen, da es sich dabei um .net-Werttypen handelt. Klassen und Datensätze sind .net-Verweis Typen. Die Semantik von Werttypen und Verweis Typen unterscheidet sich darin, dass Werttypen als Wert übermittelt werden. Dies bedeutet, dass Sie Bits für Bit kopiert werden, wenn Sie als Parameter übergeben oder von einer Funktion zurückgegeben werden. Sie werden auch auf dem Stapel gespeichert oder, wenn Sie als Feld verwendet werden, in das übergeordnete Objekt eingebettet, anstatt an einem eigenen separaten Speicherort auf dem Heap gespeichert zu werden. Daher eignen sich Strukturen für Daten, auf die häufig zugegriffen wird, wenn der Aufwand des Zugriffs auf den Heap ein Problem darstellt. Weitere Informationen zu Strukturen finden Sie unter [Strukturen](structures.md).

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [Mitglieder](./members/index.md)
- [Vererbung](inheritance.md)
- [Schnittstellen](interfaces.md)
