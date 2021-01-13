---
title: Aktualisieren der Codebasis zur Verwendung von Nullable-Verweistypen
description: Wählen Sie die beste Strategie für ein Upgrade der Codebasis zur Verwendung von Nullable-Verweistypen.
ms.technology: csharp-null-safety
ms.date: 07/31/2019
ms.openlocfilehash: ab0970247c7e3f3c20d7fdb40ef035c4ba1d8b01
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "97866821"
---
# <a name="update-libraries-to-use-nullable-reference-types-and-communicate-nullable-rules-to-callers"></a>Aktualisieren von Bibliotheken zur Verwendung von Nullable-Verweistypen sowie zur Übermittlung von Regeln zum Zulassen von Nullwerten an Aufrufer

Die zusätzliche Verwendung von [Nullable-Verweistypen](nullable-references.md) bedeutet, dass Sie für jede Variable deklarieren können, ob ein `null`-Wert zulässig ist bzw. erwartet wird oder nicht. Darüber hinaus können Sie eine Reihe von Attributen anwenden (`AllowNull`, `DisallowNull`, `MaybeNull`, `NotNull`, `NotNullWhen`, `MaybeNullWhen` und `NotNullIfNotNull`), um die NULL-Status von Argument- und Rückgabewerten umfassend zu beschreiben. Dies ist beim Schreiben von Code ideal. Sie erhalten Warnungen, wenn eine Non-Nullable-Variable auf `null` festgelegt werden kann. Sie erhalten Warnungen, wenn eine Nullable-Variable vor dem Dereferenzieren nicht auf NULL überprüft wurde. Die Aktualisierung Ihrer Bibliotheken kann einige Zeit in Anspruch nehmen, aber es lohnt sich. Je mehr Informationen Sie dem Compiler darüber bereitstellen, *wann* ein `null`-Wert zulässig oder unzulässig ist, umso besser werden die Warnungen für die Benutzer Ihrer API. Beginnen wir mit einem bekannten Beispiel. Angenommen, Ihre Bibliothek verfügt über die folgende API zum Abrufen einer Ressourcenzeichenfolge:

```csharp
bool TryGetMessage(string key, out string message)
```

Das vorstehende Beispiel folgt dem bekannten `Try*`-Muster in .NET. Es sind zwei Verweisargumente für diese API vorhanden: die Parameter `key` und `message`. Diese API umfasst die folgenden Regeln in Bezug auf die NULL-Zulässigkeit dieser Argumente:

- Aufrufer dürfen nicht `null` als Argument für `key` übergeben.
- Aufrufer können eine Variable übergeben, deren Wert `null` als Argument für `message` lautet.
- Wenn die Methode `TryGetMessage` den Wert `true` zurückgibt, ist der Wert von `message` ungleich NULL. Wenn der Rückgabewert `false,` lautet, ist der Wert von `message` (und der zugehörige NULL-Zustand) NULL.

Die Regel für `key` kann durch den Variablentyp umfassend ausgedrückt werden: `key` muss ein Non-Nullable-Verweistyp sein. Der Parameter `message` ist komplexer. Er lässt `null` als Argument zu, aber garantiert bei einem erfolgreichen Vorgang, dass das `out`-Argument nicht NULL ist. Für diese Szenarien ist ein umfangreicheres Vokabular zum Beschreiben der Erwartungen erforderlich.

Die Aktualisierung der Bibliothek für Nullable-Verweise erfordert mehr als die Verteilung von `?` in einigen Variablen und Typnamen. Wie das vorangehende Beispiel zeigt, müssen Sie Ihre APIs untersuchen und Ihre Erwartungen für jedes Eingabeargument überprüfen. Berücksichtigen Sie die Garantien für die Rückgabewerte und alle `out`- oder `ref`-Argumente bei der Rückgabe der Methode. Übermitteln Sie diese Regeln an den Compiler, der dann Warnungen ausgibt, wenn Aufrufer diese Regeln nicht einhalten.

Diese Aufgabe nimmt einige Zeit in Anspruch. Beginnen wir mit Strategien, mit denen Ihre Bibliothek oder Anwendung Nullable-fähig gemacht wird und gleichzeitig andere Anforderungen ausgeglichen werden. Hier erfahren Sie, wie Sie die fortlaufende Entwicklung anpassen können, indem Sie Nullable-Verweistypen zulassen. Sie lernen Herausforderungen für generische Typdefinitionen kennen. Sie erfahren, wie Sie Attribute anwenden, um Vor- und Nachbedingungen einzelner APIs zu beschreiben.

## <a name="choose-a-strategy-for-nullable-reference-types"></a>Auswählen einer Strategie für Nullable-Verweistypen

Zunächst einmal muss festgelegt werden,ob Nullable-Verweistypen standardmäßig aktiviert oder deaktiviert sein sollen. Es gibt zwei Strategien:

- Aktivieren Sie Nullable-Verweistypen für das gesamte Projekt, und deaktivieren Sie sie in Code, der noch nicht fertig ist.
- Aktivieren Sie Nullable-Verweistypen nur für Code, der für Nullable-Verweistypen kommentiert wurde.

Die erste Strategie funktioniert am besten, wenn Sie der Bibliothek beim Aktualisieren für Nullable-Verweistypen weitere Features hinzufügen. Alle neuen Entwicklungen sind Nullable-fähig. Wenn Sie vorhandenen Code aktualisieren, aktivieren Sie in diesen Klassen Nullable-Verweistypen.

Führen Sie nach dieser ersten Strategie die folgenden Schritte aus:

1. Aktivieren Sie Nullable-Verweistypen für das gesamte Projekt, indem Sie Ihren *CSPROJ*-Dateien das `<Nullable>enable</Nullable>`-Element hinzufügen.
1. Fügen Sie allen Quelldateien in Ihrem Projekt das `#nullable disable`-Pragma hinzu.
1. Entfernen Sie bei der Bearbeitung der einzelnen Dateien das Pragma und kümmern Sie sich ggf. um Warnungen.

Diese erste Strategie ist im Vorfeld mit mehr Arbeit verbunden, da das Pragma allen Dateien hinzugefügt werden muss. Sie hat jedoch den Vorteil, dass jede neue Codedatei, die dem Projekt hinzugefügt wird, Nullable-fähig ist. Jede neue Arbeit ist Nullable-fähig. Nur bereits vorhandener Code muss aktualisiert werden.

Die zweite Strategie funktioniert besser, wenn die Bibliothek stabil ist und das Hauptaugenmerk der Entwicklung auf der Einführung von Nullable-Verweistypen liegt. Aktivieren Sie Nullable-Verweistypen beim Kommentieren von APIs. Aktivieren Sie anschließend Nullable-Verweistypen für das gesamte Projekt.

Führen Sie nach dieser zweiten Strategie die folgenden Schritte aus:

1. Fügen Sie das `#nullable enable`-Pragma der Datei hinzu, die Sie Nullable-fähig machen möchten.
1. Kümmern Sie sich um Warnungen.
1. Führen Sie die ersten beiden Schritte aus, bis die gesamte Bibliothek Nullable-fähig ist.
1. Aktivieren Sie Nullable-Typen für das gesamte Projekt, indem Sie Ihren *CSPROJ*-Dateien das `<Nullable>enable</Nullable>`-Element hinzufügen.
1. Entfernen Sie die `#nullable enable`-Pragmas, da sie nicht mehr benötigt werden.

Diese zweite Strategie ist im Vorfeld mit weniger Arbeit verbunden. Sie hat jedoch den Nachteil, dass beim Erstellen einer neuen Datei immer zuerst das Pragma hinzugefügt und Nullable-fähig gemacht werden muss. Wenn Entwickler in Ihrem Team das vergessen, ist dieser neue Code nun im Arbeitsrückstand, da der gesamte Code Nullable-fähig gemacht werden muss.

Für welche Strategie Sie sich entscheiden, hängt davon ab, wie viel aktive Entwicklung in Ihrem Projekt stattfindet. Je ausgereifter und stabiler Ihr Projekt ist, umso besser eignet sich die zweite Strategie. Je mehr Features entwickelt werden, umso besser eignet sich die erste Strategie.

> [!IMPORTANT]
> Der globale Nullable-Kontext gilt nicht für generierte Codedateien. Der Nullable-Kontext ist unabhängig von der Strategie für alle als generiert gekennzeichneten Quelldateien *deaktiviert*. Das bedeutet, dass alle in generierten Dateien enthaltenen APIs nicht mit Anmerkungen versehen werden. Es gibt viel Möglichkeiten, eine Datei als generiert zu markieren:
>
> 1. Geben Sie in der EDITORCONFIG-Datei `generated_code = true` in einem Abschnitt an, der für diese Datei gilt.
> 1. Fügen Sie `<auto-generated>` oder `<auto-generated/>` ganz oben in der Datei in einem Kommentar ein. Dabei kann es sich um eine beliebige Zeile des Kommentars handeln, jedoch muss es sich beim Kommentarblock um das erste Element in der Datei handeln.
> 1. Beginnen Sie den Dateinamen mit *TemporaryGeneratedFile_* .
> 1. Enden Sie den Dateinamen mit *.designer.cs*, *.generated.cs*, *.g.cs* oder *.g.i.cs*.
>
> Generatoren können die Präprozessoranweisung [`#nullable`](language-reference/preprocessor-directives/preprocessor-nullable.md) verwenden.

## <a name="should-nullable-warnings-introduce-breaking-changes"></a>Sollten mit Nullable-Warnungen Breaking Changes eingeführt werden?

Vor dem Aktivieren von Nullable-Verweistypen wird bei Variablen die *Nullable-Eigenschaft ignoriert*. Nach dem Aktivieren von Nullable-Verweistypen sind diese Variablen alle *Non-Nullable-Variablen*. Der Compiler gibt Warnungen aus, wenn diese Variablen nicht mit Werten ungleich NULL initialisiert werden.

Eine weitere wahrscheinliche Quelle für Warnungen sind Rückgabewerte, wenn der Wert nicht initialisiert wurde.

Der erste Schritt bei der Behandlung von Compilerwarnungen besteht darin, `?`-Anmerkungen für Parameter- und Rückgabetypen zu verwenden, um anzugeben, wann Argumente oder Rückgabewerte NULL sein können. Wenn Verweisvariablen nicht NULL sein dürfen, ist die ursprüngliche Deklaration richtig. Bei dieser Aufgabe geht es nicht nur darum, Warnungen zu behandeln. Vielmehr geht es darum, dafür zu sorgen, dass der Compiler versteht, warum NULL-Werte verwendet werden sollen. Bei der Untersuchung der Warnungen kommen Sie zur nächsten wichtigen Entscheidung für Ihre Bibliothek. Möchten Sie eine Änderung der API-Signaturen in Betracht ziehen, um Ihre Entwurfsabsicht klarer zu kommunizieren? Eine bessere API-Signatur für die zuvor untersuchte `TryGetMessage`-Methode könnte wie folgt lauten:

```csharp
string? TryGetMessage(string key);
```

Der Rückgabewert gibt an, ob der Vorgang erfolgreich oder fehlerhaft war, und enthält den Wert, sofern er gefunden wurde. Häufig lässt sich die Kommunikation von NULL-Werten durch Ändern der API-Signaturen verbessern.

Bei öffentlichen Bibliotheken oder Bibliotheken mit einer großen Benutzerbasis ist es jedoch möglicherweise besser, an API-Signaturen keine Änderungen vorzunehmen. In diesen Fällen oder bei anderen gängigen Mustern können Sie Attribute anwenden, um klarer zu definieren, wann ein Argument oder Rückgabewert `null` sein darf. Unabhängig davon, ob Sie eine Änderung der Oberfläche Ihrer API in Betracht ziehen oder nicht, werden Sie wahrscheinlich feststellen, dass Typanmerkungen allein nicht ausreichen, um `null`-Werte für Argumente oder Rückgabewerte zu beschreiben. In diesen Fällen können Sie Attribute anwenden, um eine API deutlicher zu beschreiben.

## <a name="attributes-extend-type-annotations"></a>Attribute erweitern Typanmerkungen

Es wurden mehrere Attribute hinzugefügt, um zusätzliche Informationen über den NULL-Zustand von Variablen auszudrücken. In jeglichem Code, der vor C# 8.0 und der Einführung von Nullable-Verweistypen geschrieben wurde, wurden *NULL-Werte nicht beachtet*. Dies bedeutet, dass eine Verweistypvariable NULL sein konnte, aber NULL-Überprüfungen nicht erforderlich waren. Sobald Ihr Code *Nullable-fähig* ist, ändern sich diese Regeln. Verweistypen dürfen nie den Wert `null` aufweisen, und Nullable-Verweistypen müssen auf `null` überprüft werden, bevor sie dereferenziert werden können.

Die Regeln für Ihre APIs sind wahrscheinlich komplizierter, wie im `TryGetValue`-API-Szenario deutlich geworden ist. Viele Ihrer APIs umfassen komplexere Regeln in Bezug darauf, wann Variablen den Wert `null` annehmen können oder nicht. In diesen Fällen verwenden Sie Attribute, um diese Regeln auszudrücken. Die Attribute, mit der Sie die Semantik Ihrer API beschreiben können, finden Sie im Artikel über [Attribute, die sich auf die Nullable-Analyse auswirken](./language-reference/attributes/nullable-analysis.md).

## <a name="generic-definitions-and-nullability"></a>Generische Definitionen und NULL-Zulässigkeit

Die korrekte Kommunikation des NULL-Status von generischen Typen und generischen Methoden erfordert besondere Sorgfalt. Die besondere Sorgfalt ist deshalb erforderlich, weil sich Nullable-Werttypen und Nullable-Verweistypen grundlegend voneinander unterscheiden. `int?` ist ein Synonym für `Nullable<int>`, während `string?` ein `string` mit einem vom Compiler hinzugefügten Attribut ist. Das führt dazu, dass der Compiler für `T?` nur dann den richtigen Code generieren kann, wenn er weiß, ob `T` eine `class`- oder `struct`-Einschränkung ist.

Das bedeutet nicht, dass Sie keinen Nullable-Typ (Werttyp oder Verweistyp) als Typargument für einen geschlossenen generischen Typ verwenden können. Sowohl `List<string?>` als auch `List<int?>` sind gültige Instanziierungen von `List<T>`.

Vielmehr bedeutet das, dass Sie `T?` in einer generischen Klassen- oder Methodendeklaration nur mit Einschränkungen verwenden können. <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable%7B%60%600%7D)?displayProperty=nameWithType> wird beispielsweise für die Rückgabe von `T?` nicht geändert. Sie können diese Einschränkung umgehen, indem Sie entweder die `struct`- oder die `class`-Einschränkung hinzufügen. Bei beiden Einschränkungen weiß der Compiler, wie Code für `T` und `T?`generiert werden kann.

Sie sollten die für ein generisches Typargument verwendeten Typen auf Non-Nullable-Typen beschränken. Hierzu fügen Sie für dieses Typargument die `notnull`-Einschränkung hinzu. Wenn diese Einschränkung angewendet wird, darf das Typargument kein Nullable-Typ sein.

## <a name="late-initialized-properties-data-transfer-objects-and-nullability"></a>Spät initialisierte Eigenschaften, Datenübertragungsobjekte und NULL-Zulässigkeit

Wenn Sie die NULL-Zulässigkeit von Eigenschaften angeben, die spät initialisiert, d. h. nach der Konstruktion festgelegt werden, ist möglicherweise eine besondere Überlegung erforderlich, um sicherzustellen, dass Ihre Klasse die ursprüngliche Entwurfsabsicht weiterhin korrekt zum Ausdruck bringt.

Typen, die spät initialisierte Eigenschaften wie Datenübertragungsobjekte (Data Transfer Objects, DTOs) enthalten, werden häufig durch eine externe Bibliothek wie etwa durch einen Datenbank-ORM (Object Relational Mapper), ein Deserialisierungsprogramm oder eine andere Komponente instanziiert, die Eigenschaften automatisch aus einer anderen Quelle auffüllt.

Betrachten Sie die folgende DTO-Klasse, die einen Kursteilnehmer darstellt, bevor Nullable-Verweistypen aktiviert werden:

```csharp
class Student
{
    [Required]
    public string FirstName { get; set; }

    [Required]
    public string LastName { get; set; }

    public string VehicleRegistration { get; set; }
}
```

Die Entwurfsabsicht (in diesem Fall durch das `Required`-Attribut angegeben) deutet darauf hin, dass in diesem System die Eigenschaften `FirstName` und `LastName` **obligatorisch** und somit nicht NULL sind.

Die `VehicleRegistration`-Eigenschaft ist **nicht obligatorisch**, kann daher NULL sein.

Beim Aktivieren von Nullable-Verweistypen sollten Sie angeben, welche Eigenschaften in Ihrem DTO entsprechend Ihrer ursprünglichen Entwurfsabsicht Nullwerte zulassen sollen:

```csharp
class Student
{
    [Required]
    public string FirstName { get; set; }

    [Required]
    public string LastName { get; set; }

    public string? VehicleRegistration { get; set; }
}
```

Bei diesem DTO ist ``VehicleRegistration`` die einzige Eigenschaft, die NULL sein darf.

Der Compiler löst jedoch sowohl für `FirstName` als auch für `LastName` `CS8618`-Warnungen aus, was darauf hindeutet, dass die Non-Nullable-Eigenschaften nicht initialisiert wurden.

Es gibt drei Möglichkeiten, mit denen die Compilerwarnungen so aufgelöst werden können, dass die ursprüngliche Absicht erhalten bleibt. Jede dieser drei Möglichkeiten ist zulässig. Sie sollten diejenige auswählen, die am besten zu Ihrem Codierungsstil und zu Ihren Entwurfsanforderungen passt.

### <a name="initialize-in-the-constructor"></a>Initialisieren im Konstruktor

Warnungen zu nicht initialisierten Eigenschaften lassen sich am besten durch Initialisieren der Eigenschaften im Konstruktor auflösen:

```csharp
class Student
{
    public Student(string firstName, string lastName)
    {
        FirstName = firstName;
        LastName = lastName;
    }

    [Required]
    public string FirstName { get; set; }

    [Required]
    public string LastName { get; set; }

    public string? VehicleRegistration { get; set; }
}
```

Dieser Ansatz funktioniert nur, wenn die Bibliothek, die Sie zum Instanziieren der Klasse verwenden, die Übergabe von Parametern im Konstruktor unterstützt.

Eine Bibliothek unterstützt möglicherweise die Übergabe von *einigen*, aber nicht von allen Eigenschaften im Konstruktor. EF Core unterstützt beispielsweise die [Konstruktorbindung](/ef/core/modeling/constructors) für normale Spalteneigenschaften, Navigationseigenschaften werden dagegen nicht unterstützt.

In der Dokumentation zu der Bibliothek, die Ihre Klasse instanziiert, finden Sie Informationen dazu, in welchem Umfang die Konstruktorbindung unterstützt wird.

### <a name="property-with-nullable-backing-field"></a>Eigenschaft mit Nullable-Unterstützungsfeld

Wenn Sie die Konstruktorbindung nicht verwenden können, können Sie dieses Problem mithilfe einer Non-Nullable-Eigenschaft mit einem Nullable-Unterstützungsfeld beheben:

```csharp
private string? _firstName;

[Required]
public string FirstName
{
    set => _firstName = value;
    get => _firstName
           ?? throw new InvalidOperationException("Uninitialized " + nameof(FirstName))
}
```

Wenn in diesem Szenario auf die `FirstName`-Eigenschaft zugegriffen wird, bevor sie initialisiert wurde, löst der Code eine `InvalidOperationException` aus, da dies nicht dem API-Vertrag entspricht.

Beachten Sie, dass bei einigen Bibliotheken bei der Verwendung von Unterstützungsfeldern bestimmte Aspekte berücksichtigt werden müssen. So muss EF Core beispielsweise für die richtige Verwendung von [Unterstützungsfeldern](/ef/core/modeling/backing-field) konfiguriert werden.

### <a name="initialize-the-property-to-null"></a>Initialisieren der Eigenschaft mit NULL

Als kürzere Alternative zur Verwendung eines Nullable-Unterstützungsfelds oder für den Fall, dass die Bibliothek, die Ihre Klasse instanziiert, mit diesem Ansatz nicht kompatibel ist, können Sie die Eigenschaft mithilfe des NULL-toleranten Operators (`!`) direkt mit `null` initialisieren:

```csharp
[Required]
public string FirstName { get; set; } = null!;

[Required]
public string LastName { get; set; } = null!;

public string? VehicleRegistration { get; set; }
```

Sie werden keinen tatsächlichen NULL-Wert zur Laufzeit beobachten, außer aufgrund eines Programmierfehlers, indem Sie auf die Eigenschaft zugreifen, bevor sie ordnungsgemäß initialisiert wurde.

## <a name="see-also"></a>Siehe auch

- [Tutorial: Migrieren vorhandenen Codes mit Verweistypen, die NULL-Werte zulassen](tutorials/upgrade-to-nullable-references.md)
- [Verwenden von Nullable-Verweistypen in EF Core](/ef/core/miscellaneous/nullable-reference-types)
