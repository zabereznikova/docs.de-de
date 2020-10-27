---
title: Neues in C# 6 – C#-Leitfaden
description: Neues zu den neuen Features in Version 6 von C#
ms.date: 12/12/2018
ms.openlocfilehash: da40b4c9d4af0094fdd907c542e971ba55086e0f
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224236"
---
# <a name="whats-new-in-c-6"></a>Neues in C# 6

Die Version 6.0 von C# enthält zahlreiche Features, die die Produktivität für Entwickler verbessern. Der Gesamteffekt dieser Features ist es, dass Sie präziseren Code schreiben, der zudem lesbarer ist. Die Syntax benötigt weniger Aufwand für viele allgemeine Methoden. Es ist einfacher, die Entwurfsabsicht mit weniger Aufwand anzuzeigen. Mit diesen Features sind Sie produktiver und können besser lesbaren Code schreiben. Zudem können Sie sich besser auf Ihre Features statt auf die Sprachkonstrukte konzentrieren.

Im weiteren Verlauf dieses Artikels finden Sie eine Übersicht über die einzelnen Features, in der jeweils ein Link enthalten ist, über den Sie weitere Informationen zum Feature erhalten. Die Funktionen werden zusätzlich in einem [interaktiven Tutorial zur Einführung von C# 6](../tutorials/exploration/csharp-6.yml) im Abschnitt „Tutorials“ näher erklärt.

## <a name="read-only-auto-properties"></a>Schreibgeschützte Auto-Eigenschaften

*Schreibgeschützte Auto-Eigenschaften* ermöglichen eine präzisere Syntax um unveränderliche Typen zu erstellen. Sie deklarieren die Auto-Eigenschaft nur mit einem Get-Accessor:

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

Die `FirstName`- und `LastName`-Eigenschaften können nur im Text des Konstruktors der gleichen Klasse festgelegt werden:

[!code-csharp[ReadOnlyAutoPropertyConstructor](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoPropertyConstructor)]

Wenn Sie versuchen, `LastName` in einer anderen Methode festzulegen, wird ein `CS0200`-Kompilierungsfehler erzeugt:

```csharp
public class Student
{
    public string LastName { get;  }

    public void ChangeName(string newLastName)
    {
        // Generates CS0200: Property or indexer cannot be assigned to -- it is read only
        LastName = newLastName;
    }
}
```

Dieses Feature ermöglicht eine korrekte Sprachenunterstützung zum Erstellen unveränderlicher Typen und nutzt die präzisere und praktischere Syntax für automatische Eigenschaften.

Wenn durch das Hinzufügen dieser Syntax eine zugängliche Methode nicht entfernt wird, handelt es sich um eine [binärkompatible Änderung](version-update-considerations.md#binary-compatible-changes).

## <a name="auto-property-initializers"></a>Auto-Eigenschaft-Initialisierer

Mit *Initialisierern für automatische Eigenschaften* können Sie den ursprünglichen Wert für eine automatische Eigenschaft als Teil der Eigenschaftendeklaration deklarieren.

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

Der `Grades`-Member wird dort initialisiert, wo er deklariert ist. Dies erleichtert die einmalige Ausführung der Initialisierung. Die Initialisierung ist Teil der Eigenschaftendeklaration. Dadurch ist es einfacher, die Speicherbelegung mit der öffentlichen Schnittstelle für `Student`-Objekte gleichzustellen.

## <a name="expression-bodied-function-members"></a>Ausdruckskörper-Funktionsmember

Viele Member, die Sie schreiben, sind einzelne Anweisungen, die einzelne Ausdrücke darstellen können. Schreiben Sie stattdessen einen Ausdruckskörpermember. Dies funktioniert für Methoden und schreibgeschützte Eigenschaften. Das Außerkraftsetzen von `ToString()` ist z.B. oft eine gute Wahl:

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

Sie können diese Syntax auch für schreibgeschützte Eigenschaften verwenden:

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

Das Ändern eines vorhandenen Members in ein Ausdruckskörpermember ist eine [binärkompatible Änderung](version-update-considerations.md#binary-compatible-changes).

## <a name="using-static"></a>verwendet statische

Die Erweiterung *verwendet statische* erlaubt Ihnen das Importieren der statischen Methoden einer einzelnen Klasse. Sie geben die von Ihnen verwendete Klasse ein:

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

Die <xref:System.Math>-Klasse enthält keine Instanzmethoden. Sie können auch `using static` zum Importieren von statischen Methoden einer Klasse für eine Klasse verwenden, die jeweils über statische Methoden und Instanzenmethoden verfügt. Eines der nützlichsten Beispiele ist <xref:System.String>:

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> Sie müssen den vollqualifizierten Klassennamen `System.String` in einer statischen using-Anweisung verwenden.  Sie können das `string`-Schlüsselwort nicht stattdessen verwenden.

Beim Importieren einer `static using`-Anweisung befinden sich Erweiterungsmethoden nur im Gültigkeitsbereich, wenn Sie mithilfe der Aufrufsyntax für Erweiterungsmethoden aufgerufen werden. Wenn sie als statische Methode aufgerufen werden, befinden sie sich nicht im Gültigkeitsbereich. Sie sehen dies oft in LINQ-Abfragen. Sie können das LINQ-Muster importieren, indem Sie <xref:System.Linq.Enumerable> oder <xref:System.Linq.Queryable> importieren.

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

Erweiterungsmethoden werden normalerweise mithilfe von Aufrufausdrücken für Erweiterungsmethoden aufgerufen. Für den seltenen Fall, dass sie durch die Aufrufsyntax für statische Methoden aufgerufen werden, wird der Klassenname hinzugefügt, um Mehrdeutigkeiten zu vermeiden.

Die `static using`-Direktive importiert auch keine geschachtelten Typen. Sie können auf alle geschachtelten Typen ohne Qualifikation verweisen.

## <a name="null-conditional-operators"></a>Bedingter NULL-Operator

Der *NULL-bedingte Operator* erleichtert und optimiert NULL-Überprüfungen. Ersetzen Sie einfach den Memberzugriff `.` durch `?.`:

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

Im vorangegangenen Beispiel, ist die Variable `first``null` zugewiesen, wenn das Person-Objekt `null` ist. Andernfalls wird ihr der Wert der `FirstName`-Eigenschaft zugewiesen. Beachten Sie vor allem, dass `?.` bedeutet, dass diese Codezeile keine `NullReferenceException` generiert, wenn die `person`-Variable `null` ist. Stattdessen wird sie vorzeitig abgebrochen (Kurzschlussauswertung) und gibt `null` zurück. Sie können auch einen bedingten NULL-Operator für den Zugriff von Array oder Indexern verwenden. Ersetzen Sie `[]` durch `?[]` im Indexausdruck.

Dieser Ausdruck gibt einen `string`-Wert zurück, unabhängig vom Wert von `person`. Häufig können Sie dieses Konstrukt mit dem *NULL-Sammeloperator* verwenden, um die Standardwerte zuzuweisen, wenn eine der Eigenschaften `null` ist. Im Falle einer Verkürzung im Ausdruck wird der zurückgegebene `null`-Wert aufgelistet, damit er mit dem vollständigen Ausdruck übereinstimmt.

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

Sie können auch `?.` verwenden, um Methoden bedingt aufzurufen. Die häufigste Verwendung von Memberfunktionen mit dem bedingten NULL-Operator besteht darin, Delegaten (oder Ereignishandler), die möglicherweise `null` sind, sicher aufzurufen.  Dazu müssen Sie die `Invoke`-Methode des Delegaten mithilfe des `?.`-Operators aufrufen, um auf den Member zuzugreifen. Im Artikel zum [Delegieren von Mustern](../delegates-patterns.md#handling-null-delegates) finden Sie ein Beispiel dazu.

Die Regeln des `?.`-Operators stellen sicher, dass die linke Seite des Operators nur einmal ausgewertet wird. Dadurch werden viele Idiome aktiviert, einschließlich folgendes Beispiel, in dem Ereignishandler verwendet werden:

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

Stellen Sie sicher, dass die linke Seite nur einmal ausgewertet wird, um einen beliebigen Ausdruck sowie Methodenaufrufe auf der linken Seite von `?.` zu verwenden.

## <a name="string-interpolation"></a>Zeichenfolgeninterpolation

Ab C# 6 können Sie mit dem neuen Feature für [Zeichenfolgeninterpolationen](../language-reference/tokens/interpolated.md) Ausdrücke in eine Zeichenfolge einbetten. Stellen Sie einfach `$` vor die Zeichenfolge, und verwenden Sie Ausdrücke zwischen `{` und `}` anstelle von Ordnungszahlen:

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

In diesem Beispiel werden Eigenschaften für die ersetzten Ausdrücke verwendet. Sie können einen beliebigen Ausdruck verwenden. Sie können z.B. den Notendurchschnitt eines Studenten als Teil der Interpolation berechnen:

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

Die vorherige Codezeile formatiert den Wert für `Grades.Average()` als Gleitkommazahl mit zwei Dezimalstellen.

Häufig müssen Sie die Zeichenfolge formatieren, die unter Verwendung einer bestimmten Kultur erstellt wurde. Hierbei nutzen Sie die Tatsache, dass das Objekt, das durch die Zeichenfolgeninterpolation erstellt wurde, implizit in <xref:System.FormattableString?displayProperty=nameWithType> konvertiert werden kann. Die <xref:System.FormattableString>-Instanz enthält die zusammengesetzte Formatzeichenfolge sowie die Ergebnisse der Auswertung der Ausdrücke, bevor sie in Zeichenfolgen konvertiert werden. Verwenden Sie die <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType>-Methode, um die Kultur anzugeben, wenn Sie eine Zeichenfolge formatieren. Im folgenden Beispiel wird eine Zeichenfolge mit deutscher Kultur (de-DE) erstellt. (In der deutschen Kultur wird standardmäßig das Zeichen „,“ als Dezimaltrennzeichen sowie das Zeichen „.“ als Tausendertrennzeichen verwendet.)

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

Wenn Sie mehr über die Zeichenfolgeninterpolation erfahren möchten, sehen Sie sich das interaktive Tutorial [Zeichenfolgeninterpolation in C#](../tutorials/exploration/interpolated-strings.yml), den Artikel [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) und das Tutorial [Zeichenfolgeninterpolation in C#](../tutorials/string-interpolation.md) an.

## <a name="exception-filters"></a>Ausnahmefilter

*Ausnahmefilter* sind Klauseln, die festlegen, wann eine bestimmte Catch-Klausel angewendet werden muss. Wenn der für einen Ausnahmefilter verwendete Ausdruck `true` ergibt, führt die Catch-Klausel die normale Verarbeitung auf einer Ausnahme durch. Wenn der Ausdruck `false` ergibt, wird die `catch`-Klausel übersprungen. Eine Verwendung ist, Informationen über eine Ausnehme zu untersuchen, um zu bestimmen, ob eine `catch`-Klausel die Ausnahme verarbeiten kann:

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

## <a name="the-nameof-expression"></a>Der `nameof`-Ausdruck

Der Ausdruck [nameof](../language-reference/operators/nameof.md) wird zum Namen eines Symbols ausgewertet. Es ist eine hervorragende Möglichkeit, Tools zum Arbeiten zu bringen, wenn Sie den Namen einer Variable, Eigenschaften oder eines Memberfelds benötigen. Eine der häufigsten Verwendungszwecke für `nameof` besteht darin, den Namen eines Symbols bereitzustellen, die eine Ausnahme ausgelöst hat:

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

Sie können den Ausdruck auch mit auf XAML basierenden Anwendungen verwenden, die die `INotifyPropertyChanged`-Schnittstelle implementieren:

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

## <a name="await-in-catch-and-finally-blocks"></a>„Await“ in Catch- und Finally-Blöcken

C# 5 hat mehrere Einschränkungen im Hinblick auf die Position von `await`-Ausdrücken. Sie können mit C# 6 nun `await` in `catch`- oder `finally`-Ausdrücken verwenden. Dies wird am häufigsten in Protokollierungsszenarios verwendet:

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

Die Implementierungsdetails für das Hinzufügen von `await`-Unterstützung in `catch`- und `finally`-Klauseln stellt sicher, dass das Verhalten konsistent mit dem Verhalten für synchronen Code ist. Wenn Code, der in einer `catch`- oder `finally`-Klausel ausgeführt wird, ausgelöst wird, so sucht die Ausführung nach einer passenden `catch`-Klausel im nächsten Block in der Umgebung. Wenn eine aktuelle Ausnahme aufgetreten ist, geht diese Ausnahme verloren. Das Gleiche passiert bei erwarteten Ausdrücken in `catch`- und `finally`-Klauseln: eine passende `catch` wird gesucht und die aktuelle Ausnahme, falls vorhanden, geht verloren.  

> [!NOTE]
> Dieses Verhalten ist der Grund, warum es empfohlen wird, `catch`- und `finally`-Klauseln sorgfältig zu schreiben, um die Einführung neuer Ausnahmen zu vermeiden.

## <a name="initialize-associative-collections-using-indexers"></a>Initialisieren von assoziativen Sammlungen unter Verwendung von Indexern

Der *Indexinitialisierer* ist eines von zwei Features, die Auflistungsinitialisierer konsistenter mit der Indexnutzung machen. In früheren Releases von C# konnten Sie *Sammlungsinitialisierer* nur mit Sammlungen im Sequenzformat (einschließlich <xref:System.Collections.Generic.Dictionary%602>) verwenden, indem Sie Klammern um Schlüssel- und Wertpaare gesetzt haben:

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#CollectionInitializer)]

Sie können sie mit <xref:System.Collections.Generic.Dictionary%602>-Sammlungen und anderen Typen verwenden, wenn die zugängliche `Add`-Methode mehr als ein Argument akzeptiert. Die neue Syntax unterstützt Zuweisungen mit einem Index in die Auflistung:

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

Dieses Feature bedeutet, dass assoziative Container mithilfe von Syntax initialisiert werden können, die ähnlich dem ist, was für Sequenzcontainern für einige Versionen vorhanden war.

## <a name="extension-add-methods-in-collection-initializers"></a>Erweiterungs-`Add`-Methoden in Auflistungsinitialisierern

Ein weiteres Feature zur Vereinfachung der Auflistungsinitialisierer ist die Möglichkeit, eine *Erweiterungsmethode* für die `Add`-Methode zu verwenden. Dieses Feature wurde für die Parität mit Visual Basic hinzugefügt. Das Feature ist am nützlichsten, wenn Sie über eine benutzerdefinierte Auflistungsklasse verfügen, die eine Methode mit einem anderen Namen besitzt, um semantisch neue Elemente hinzuzufügen.

## <a name="improved-overload-resolution"></a>Verbesserte Überladungsauflösung

Dieses letzte Feature ist eines, das Sie bestimmt nicht bemerken. Es gab Konstrukte, bei denen die vorherige Version des C#-Compilers womögliche einige Methodenaufrufe erkannt hat, einschließlich mehrdeutige Lambdaausdrücke. Betrachten Sie diese Methode:

[!code-csharp[AsyncMethod](../../../samples/snippets/csharp/new-in-6/overloads.cs#AsyncMethod)]

In früheren Methoden von C# schlug der Aufruf dieser Methode mithilfe der Syntax für die Methodengruppe fehl:

[!code-csharp[MethodGroup](../../../samples/snippets/csharp/new-in-6/overloads.cs#MethodGroup)]

Der frühere Compiler konnte nicht richtig zwischen `Task.Run(Action)` und `Task.Run(Func<Task>())` unterscheiden. In früheren Versionen müssten Sie einen Lambdaausdruck als Argument verwenden:

[!code-csharp[Lambda](../../../samples/snippets/csharp/new-in-6/overloads.cs#Lambda)]

Der C# 6-Compiler bestimmt ordnungsgemäß, dass `Task.Run(Func<Task>())` eine bessere Wahl ist.

### <a name="deterministic-compiler-output"></a>Deterministische Compilerausgabe

Die Option `-deterministic` weist den Compiler an, eine Byte für Byte identische Ausgabeassembly für aufeinanderfolgende Kompilierungen der gleichen Quelldateien zu erstellen.

Jede Kompilierung erzeugt standardmäßig eine eindeutige Ausgabe. Der Compiler fügt einen Zeitstempel und eine aus zufälligen Zahlen generierte GUID hinzu. Sie können diese Option verwenden, wenn Sie die Byte für Byte Ausgabe vergleichen möchten, um die Konsistenz über Builds hinweg sicherzustellen.

Weitere Informationen finden Sie im Artikel zur Compileroption [-deterministic](../language-reference/compiler-options/deterministic-compiler-option.md).
