---
title: Neues in C# 6 – C#-Leitfaden
description: Neues zu den neuen Features in Version 6 von C#
ms.date: 09/22/2016
ms.assetid: 4d879f69-f889-4d3f-a781-75194e143400
ms.openlocfilehash: 5ba5d8f4cc5c7cecdda030594273324d14d1582a
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34565877"
---
# <a name="whats-new-in-c-6"></a>Neues in C# 6

Die Version 6.0 von C# enthält zahlreiche Features, die die Produktivität für Entwickler verbessern. Features in dieser Version sind:

* [Schreibgeschützte Auto-Eigenschaften](#read-only-auto-properties):
    - Sie können schreibgeschützte automatische Eigenschaften erstellen, die nur in Konstruktoren festgelegt werden können.
* [Auto-Eigenschaft-Initialisierer](#auto-property-initializers):
    - Sie können Initialisierungsausdrücke zum Festlegen des Anfangswerts einer Auto-Eigenschaft schreiben.
* [Ausdruckskörper-Funktionsmember](#expression-bodied-function-members):
    - Sie können einzeilige Methoden mithilfe von Lambdaausdrücken erstellen.
* [verwendet statische](#using-static):
    - Sie können alle Methoden einer einzelnen Klasse in den aktuellen Namespace importieren.
* [Bedingte NULL-Operatoren](#null-conditional-operators):
    - Sie können präzise und sicher auf Member eines Objekts zugreifen, während Sie noch nach NULL mit dem bedingten NULL-Operator suchen.
* [Zeichenfolgeninterpolierung](#string-interpolation):
    - Sie können die Zeichenfolgenformatierungsausdrücke mithilfe von Inlineausdrücken anstatt mit positionellen Argumenten schreiben.
* [Ausnahmefilter](#exception-filters):
    - Sie können Ausdrücke basierend auf den Eigenschaften der Ausnahme oder basierend auf anderen Programmstatus abfangen. 
* [„nameof“-Ausdrücke](#nameof-expressions):
    - Sie können den Compiler Zeichenfolgendarstellungen von Symbolen generieren lassen.
* [„Await“ in Catch- und Finally-Blöcken](#await-in-catch-and-finally-blocks)
    - Sie können `await`-Ausdrücke an Orten verwenden, die diese zuvor als unzulässig deklariert haben.
* [Indexinitialisierer](#index-initializers)
    - Sie können Initialisierungsausdrücke für assoziative Container sowie Sequenzcontainer erstellen.
* [Erweiterungsmethoden für Auflistungsinitialisierer](#extension-add-methods-in-collection-initializers):
    - Auflistungsinitialisierer können neben Membermethoden zugängliche Erweiterungsmethoden verwenden.
* [Verbesserte Überladungsauflösung](#improved-overload-resolution):
    - Einige Konstrukte, die zuvor mehrdeutige Methodenaufrufe generiert haben, werden nun korrekt aufgelöst.
* [Compileroption `deterministic`](#deterministic-compiler-output):
    - Die deterministische Compileroption stellt sicher, dass aufeinanderfolgende Kompilierungen der gleichen Quelle die gleiche binäre Ausgabe generieren.

Der Gesamteffekt dieser Features ist es, dass Sie präziseren Code schreiben, der zudem lesbarer ist. Die Syntax benötigt weniger Aufwand für viele allgemeine Methoden. Es ist einfacher, die Entwurfsabsicht mit weniger Aufwand anzuzeigen. Lernen Sie diese Features gut, und Sie können produktiver sein, mehr lesbaren Code schreiben und sich vermehrt auf Ihre Codefeatures konzentrieren, anstatt auf die Konstrukte der Sprache.

Im weiteren Verlauf dieses Themas werden die einzelnen Features detailliert erklärt.

## <a name="auto-property-enhancements"></a>Verbesserungen der Auto-Eigenschaft 

Die Syntax für automatisch implementierte Eigenschaften (in der Regel als „Auto-Eigenschaften“ bezeichnet) hat es stark vereinfacht, Eigenschaften zu erstellen, die einfache Get- und Set-Accessoren hatten.

[!code-csharp[ClassicAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicAutoProperty)]

Diese einfache Syntax beschränkte die Arten der Entwürfe, die Sie mithilfe von Auto-Eigenschaften unterstützen konnten. C# 6 verbessert die Funktionen der Auto-Eigenschaften, damit Sie sie in mehr Szenarios verwenden können. Sie müssen nicht so oft auf die ausführlichere Syntax zum Deklarieren und Bearbeiten des Unterstützungsfeld von Hand zurückgreifen.

Die neue Syntax eignet sich in Szenarios für schreibgeschützte Eigenschaften sowie jene zum Initialisieren des Speichers der Variable hinter einer Auto-Eigenschaft.

### <a name="read-only-auto-properties"></a>Schreibgeschützte Auto-Eigenschaften

*Schreibgeschützte Auto-Eigenschaften* ermöglichen eine präzisere Syntax um unveränderliche Typen zu erstellen. Sie kamen in früheren Versionen von C# am ehesten an unveränderlichen Typen heran, wenn Sie private Setter deklariert haben.

[!code-csharp[ClassicReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicReadOnlyAutoProperty)]
 
Mit dieser Syntax stellt der Compiler nicht sicher, dass der Typ tatsächlich unveränderlich ist. Sie erzwingt nur, dass die Eigenschaften `FirstName` und `LastName` nicht von Codes außerhalb der Klasse bearbeitet werden können.

Schreibgeschützte Auto-Eigenschaften lassen wahres schreibgeschütztes Verhalten zu. Sie deklarieren die Auto-Eigenschaft nur mit einem Get-Accessor:

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

Die `FirstName`- und `LastName`-Eigenschaften können nur im Text eines Konstruktors festgelegt werden:

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

Diese Feature ermöglicht wahrhaftige Sprachenunterstützung zum Erstellen unveränderlicher Typen und zum Verwenden der präziseren und einfacheren Auto-Eigenschaft-Syntax

### <a name="auto-property-initializers"></a>Auto-Eigenschaft-Initialisierer

Mit *Auto-Eigenschaft-Initialisierer* können Sie den ursprünglichen Wert für eine Auto-Eigenschaft als Teil der Eigenschaftendeklaration deklarieren.  In früheren Versionen mussten diese Eigenschaften über Setter verfügen und Sie müssten diesen Setter verwenden, um den vom Unterstützungsfeld verwendeten Datenspeicher zu initialisieren. Betrachten Sie diese Klasse als für einen Studenten, die den Namen sowie eine Liste der Noten des Studenten enthält:

[!code-csharp[Construction](../../../samples/snippets/csharp/new-in-6/oldcode.cs#Construction)]
 
Mit zunehmender Größe der Klasse, können Sie andere Konstruktoren einschließen. Jeder Konstruktor muss dieses Feld initialisieren, andernfalls werden Fehler verursacht.

Mit C# 6 können Sie einen Anfangswert für den von einer Auto-Eigenschaft verwendeten Speicher in der Auto-Eigenschaft-Deklaration zuweisen:

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

Der `Grades`-Member wird initialisiert, wo er deklariert ist. Dies erleichtert die einmalige Ausführung der Initialisierung. Die Initialisierung ist Teil der Eigenschaftendeklaration, was es einfacher macht, die Speicherzuweisung mit der öffentlichen Schnittstelle für `Student`-Objekte gleichzustellen.

Eigenschafteninitialisierer können wie im Folgenden dargestellt mit Lese-/Schreibeigenschaften sowie mit schreibgeschützten Eigenschaften verwendet werden.

[!code-csharp[ReadWriteInitialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadWriteInitialization)]

## <a name="expression-bodied-function-members"></a>Ausdruckskörper-Funktionsmember

Der Text von vielen Member, die wir schreiben, besteht aus nur einer Anweisung, die als Ausdruck dargestellt werden kann. Sie können diese Syntax reduzieren, indem Sie stattdessen einen Ausdruckskörpermember schreiben. Dies funktioniert für Methoden und schreibgeschützte Eigenschaften. Das Außerkraftsetzen von `ToString()` ist z.B. oft eine gute Wahl:

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

Sie können auch Ausdruckskörpermember in schreibgeschützten Eigenschaften verwenden:

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

## <a name="using-static"></a>verwendet statische

Die Erweiterung *verwendet statische* erlaubt Ihnen das Importieren der statischen Methoden einer einzelnen Klasse. Zuvor hat die `using`-Anweisungen alle Typen in einen Namespace importiert. 

Häufig verwenden wir die statischen Methoden einer Klasse für unseren Code. Das wiederholte Eingeben des Klassennamens kann die Bedeutung Ihres Codes verschleiern. Ein häufig verwendetes Beispiel ist, wenn Sie Klassen schreiben, die viele numerische Berechnungen ausführen.
Ihr Code wird mit <xref:System.Math.Sin%2A>, <xref:System.Math.Sqrt%2A> und anderen Aufrufen von unterschiedlichen Methoden in der <xref:System.Math>-Klasse überhäuft. Durch die neue `using static`-Syntax können die Klassen viel besser gelesen werden. Sie geben die von Ihnen verwendete Klasse ein:

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

Nun können Sie beliebige statische Methoden in der <xref:System.Math>-Klasse verwenden, ohne die <xref:System.Math>-Klasse zu qualifizieren. Die <xref:System.Math>-Klasse ist ein hervorragender Anwendungsfall für dieses Feature, da keine Instanzenmethoden enthalten sind. Sie können auch `using static` zum Importieren von statischen Methoden einer Klasse für eine Klasse verwenden, die jeweils über statische Methoden und Instanzenmethoden verfügt. Eines der nützlichsten Beispiele ist <xref:System.String>:

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> Sie müssen den vollqualifizierten Klassennamen `System.String` in einer statischen using-Anweisung verwenden. Sie können das `string`-Schlüsselwort nicht stattdessen verwenden. 

Sie können nun statische Methoden aufrufen, die in der <xref:System.String>-Klasse definiert sind, ohne diese Methoden als Member der Klasse zu qualifizieren.

[!code-csharp[UsingStaticString](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticString)]

Die `static using`-Funktionen und Erweiterungsmethoden interagieren auf interessante Weise, und der Sprachentwurf erhielt einige Regeln, die besonders diese Interaktionen ansprechen. Das Ziel ist, die Risiken von beeinträchtigenden Änderungen in vorhandenen Codebasen – einschließlich der Ihren – zu minimieren.

Erweiterungsmethoden befinden sich nur bei Aufruf mithilfe der Aufrufsyntax der Erweiterungsmethode im Gültigkeitsbereich und nicht, wenn sie als statische Methode aufgerufen werden.
Sie sehen dies oft in LINQ-Abfragen. Sie können das LINQ-Muster importieren, indem Sie <xref:System.Linq.Enumerable> importieren.

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

Daraufhin werden alle Methoden in der <xref:System.Linq.Enumerable>-Klasse importiert.
Allerdings befinden sich Erweiterungsmethoden nur im Gültigkeitsbereich, wenn sie als Erweiterungsmethoden aufgerufen werden. Sie befinden sich nicht im Gültigkeitsbereich, wenn sie mithilfe der Syntax für statische Methoden aufgerufen werden.

[!code-csharp[UsingStaticLinqMethod](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticLinkMethod)]

Diese Entscheidung beruht darauf, dass Erweiterungsmethoden normalerweise mithilfe von Aufrufausdrücken für Erweiterungsmethoden aufgerufen werden. Im seltenen Fall, wenn sie mithilfe der Syntax für statische Methoden aufgerufen werden, dient dies zur Auflösung von Mehrdeutigkeit.
Es scheint wohlüberlegt zu sein, dass der Klassenname als Teil des Aufrufs erforderlich ist.

Es gibt noch eine weitere Funktion von `static using`. Die `static using`-Direktive importiert auch keine geschachtelten Typen. Dadurch können Sie auf alle geschachtelten Typen ohne Qualifikation verweisen.

## <a name="null-conditional-operators"></a>Bedingter NULL-Operator

NULL-Werte erschweren den Code. Sie müssen jeden Zugriff von Variablen überprüfen, um sicherzugehen, dass Sie `null` nicht dereferenzieren. Der *NULL-bedingte Operator* erleichtert diese Überprüfungen und macht sie flüssiger.

Ersetzen Sie einfach den Memberzugriff `.` mit `?.`:

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

Im vorangegangenen Beispiel, ist die Variable `first` `null` zugewiesen, wenn das Person-Objekt `null` ist. Andernfalls wird ihr der Wert der `FirstName`-Eigenschaft zugewiesen. Beachten Sie, dass `?.` bedeutet, dass diese Codezeile keine `NullReferenceException` generiert, wenn die `person`-Variable `null` ist. Stattdessen wird direkt `null` zurückgegeben.

Beachten Sie auch, die dieser Ausdruck einen `string` zurückgibt, unabhängig vom Wert der `person`.
Im Falle einer Verkürzung wird der zurückgegebene `null`-Wert aufgelistet, damit er mit dem vollständigen Ausdruck übereinstimmt.

Häufig können Sie dieses Konstrukt mit dem *NULL-Sammeloperator* verwenden, um die Standardwerte zuzuweisen, wenn eines der Eigenschaften `null` ist:

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

Der Operand auf der rechten Seite des `?.`-Operators ist nicht auf Eigenschaften oder Felder beschränkt.
Sie können ihn auch verwenden, um Methoden bedingt aufzurufen. Die häufigste Verwendung von Memberfunktionen mit dem NULL-bedingten Operator ist, Delegaten (oder Ereignishandler), die möglicherweise `null` sind, sicher aufzurufen.  Dazu müssen sie die `Invoke`-Methode des Delegaten mithilfe des `?.`-Operators aufrufen, um auf den Member zuzugreifen. Ein Beispiel dazu finden Sie im  
Thema [delegate patterns (Delegieren von Mustern)](../delegates-patterns.md#handling-null-delegates).

Die Regeln des `?.`-Operators stellen sicher, dass die linke Seite des Operators nur einmal ausgewertet wird. Dies ist wichtig und aktiviert viele Idiome, einschließlich das Beispiel mithilfe von Ereignishandlern. Beginnen wir mit dem Gebrauch des Ereignishandlers. In früheren Versionen von C# wurden Sie ermutigt, Code wie folgt zu schreiben:

```csharp
var handler = this.SomethingHappened;
if (handler != null)
    handler(this, eventArgs);
```

Dies war einer einfacheren Syntax vorzuziehen:

```csharp
// Not recommended
if (this.SomethingHappened != null)
    this.SomethingHappened(this, eventArgs);
```

> [!IMPORTANT]
> Das obige Beispiel führt eine Racebedingung ein. Das `SomethingHappened`-Ereignis hat womöglich Abonnenten, wenn es mit `null` verglichen wird. Diese Abonnenten wurden möglicherweise entfernt, bevor das Ereignis ausgelöst wird. Das würde dazu führen, dass eine <xref:System.NullReferenceException> ausgelöst wird.

In der zweiten Version, ist der `SomethingHappened`-Ereignishändler bei der Überprüfung möglicherweise nicht NULL. Wenn jedoch ein Handler von einem anderen Code entfernt wird, kann er trotzdem NULL sein, wenn der Ereignishandler aufgerufen wurde.

Der Compiler generiert Code für den `?.`-Operator, der gewährleistet, dass die linke Seite (`this.SomethingHappened`) des `?.`-Ausdrucks einmal ausgewertet und das Ergebnis zwischengespeichert wird:

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

Wenn gewährleistet werden kann, dass die linke Seite nur einmal ausgewertet wird, dann können Sie beliebige Ausdrücke verwenden. Dazu gehören Methodenaufrufe auf der linken Seite von `?.` Auch wenn diese Nebeneffekte haben, werden sie nur einmal ausgewertet, sodass der Nebeneffekt nur einmal auftritt. Ein Beispiel dazu finden Sie unter [Introduction to Events (Einführung in Ereignisse)](../events-overview.md#language-support-for-events).

## <a name="string-interpolation"></a>Zeichenfolgeninterpolierung

C# 6 enthält eine neue Syntax für die Zusammensetzung von Zeichenfolgen aus einer Formatzeichenfolge und aus Ausdrücken, die mit dem Ziel evaluiert werden, andere Zeichenfolgenwerte auszugeben.

In der Vergangenheit mussten Sie positionelle Parameter in einer Methode wie `string.Format` verwenden:

[!code-csharp[stringFormat](../../../samples/snippets/csharp/new-in-6/oldcode.cs#stringFormat)]

Ab C# 6 hilft Ihnen das neue Feature [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) dabei, die Ausdrücke in die Formatzeichenfolge einzubetten. Stellen sie ganz einfach `$` vor die Zeichenfolge:

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

In diesem ersten Beispiel werden Eigenschaftsausdrücke für die ersetzten Ausdrücke verwendet. Sie können diese Syntax erweitern, damit Sie jeden beliebigen Ausdruck verwenden können Sie können z.B. den Notendurchschnitt eines Studenten als Teil der Interpolation berechnen:

[!code-csharp[stringInterpolationExpression](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationExpression)]

Sie bemerken vielleicht, dass die Ausgabe von `Grades.Average()`, die im vorherigen Beispiel ausgeführt wird, womöglich mehr Dezimalstellen hat, als Ihnen lieb ist. Die Zeichenfolgen-Interpolationssyntax unterstützt alle verfügbaren Formatzeichenfolgen mithilfe der vorherigen Formatierungsmethoden. Sie fügen die Formatzeichenfolgen innerhalb der geschweiften Klammern ein. Fügen Sie ein `:` nach dem zu formatierenden Ausdruck ein:

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

Die vorherige Codezeile formatiert den Wert für `Grades.Average()` als Gleitkommazahl mit zwei Dezimalstellen.

Der `:` wird immer als Trennlinie zwischen dem Ausdruck, der formatiert wird, und der Formatzeichenfolge interpretiert. Dies kann zu Problemen führen, wenn Ihr Ausdruck einen `:` anders verwendet, z.B. ein bedingter Operator:

```csharp
public string GetGradePointPercentages() =>
    $"Name: {LastName}, {FirstName}. G.P.A: {Grades.Any() ? Grades.Average() : double.NaN:F2}";
```

Im vorhergehenden Beispiel wird der `:` als der Anfang der Formatzeichenfolge analysiert und nicht als Teil des bedingter Operator. In den Fällen, in denen dies vorkommt, können Sie den Ausdruck mit Klammern umschließen, um den Compiler zu zwingen, den Ausdruck wie gewünscht zu interpretieren:

[!code-csharp[stringInterpolationConditional](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationConditional)]

Es gibt keine Einschränkungen für Ausdrücke, die Sie zwischen die geschweiften Klammern platzieren können. Sie können eine komplexe LINQ-Abfrage in eine interpolierten Zeichenfolge ausführen, um Berechnungen auszuführen die Ergebnisse anzuzeigen:

[!code-csharp[stringInterpolationLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationLinq)]

Sie können in diesem Beispiel sehen, dass Sie sogar eine Zeichenfolgeninterpolation in ein andere Zeichenfolgeninterpolation verschachteln können. Dieses Beispiel ist sicherlich viel komplexer, als wie Sie es im Produktionscode haben möchten.
Es ist viel mehr zur Veranschaulichung der Breite der Funktion gedacht. Jeder C#-Ausdruck kann zwischen die geschweiften Klammern einer interpolierten Zeichenfolge platziert werden.

### <a name="string-interpolation-and-specific-cultures"></a>Zeichenfolgeninterpolation und bestimmte Kulturen

Alle Beispiele aus dem vorherigen Abschnitt formatieren die Zeichenfolgen mithilfe der aktuellen Kultur und Sprache auf dem Computer, auf dem der Code ausgeführt wird. Häufig müssen Sie die Zeichenfolge formatieren, die unter Verwendung einer bestimmten Kultur erstellt wurde.
Hierbei nutzen Sie die Tatsache, dass das Objekt, das durch die Zeichenfolgeninterpolation erstellt wurde, implizit in <xref:System.FormattableString> konvertiert werden kann.

Die <xref:System.FormattableString>-Instanz enthält die Formatzeichenfolge sowie die Ergebnisse der Auswertung der Ausdrücke, bevor sie in Zeichenfolgen konvertiert werden. Sie können öffentliche Methoden von <xref:System.FormattableString> verwenden, um die Kultur anzugeben, wenn Sie eine Zeichenfolge formatieren. Im folgenden Beispiel wird mit der deutschen Kultur eine Zeichenfolge erstellt. Dazu wird das Zeichen „,“ für das Dezimaltrennzeichen sowie das Zeichen „.“ als Tausendertrennzeichen verwendet.

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

Weitere Informationen finden Sie unter [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md).

## <a name="exception-filters"></a>Ausnahmefilter

Ein weiteres neues Feature in C# 6 ist das der *Ausnahmefilter*. Ausnahmefilter sind Klauseln, die festlegen, wenn eine bestimmte Catch-Klausel angewendet werden muss.
Wenn der für einen Ausnahmefilter verwendete Ausdruck `true` ergibt, führt die Catch-Klausel die normale Verarbeitung auf einer Ausnahme durch. Wenn der Ausdruck `false` ergibt, wird die `catch`-Klausel übersprungen.

Eine Verwendung ist, Informationen über eine Ausnehme zu untersuchen, um zu bestimmen, ob eine `catch`-Klausel die Ausnahme verarbeiten kann:

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

Der vom Ausnahmefilter generierte Code bietet bessere Informationen zu einer Ausnahme, die ausgelöst und nicht verarbeitet wird. Bevor Ausnahmefilter zur Sprache hinzugefügt wurden, muss der Code wie folgt erstellt worden sein:

[!code-csharp[ExceptionFilterOld](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilterOld)]

Der Zeitpunkt, an dem die Ausnahme ausgelöst wird, ändert sich zwischen diesen beiden Beispielen.
Im vorherigen Code, in dem eine `throw`-Klausel verwendet wird, zeigt jede Stapelüberwachungsanalyse oder Untersuchung von Absturzimages, dass die Ausnahme von der `throw`-Anweisung in Ihrer Catch-Klausel ausgelöst wurde. Das tatsächliche Ausnahmeobjekt enthält die ursprüngliche Aufrufliste, jedoch sind alle anderen Informationen über Variablen in der Aufrufliste zwischen diesem Auslösepunkt und dem Ort des ursprünglichen Auslösepunkts verloren. 

Im Gegensatz dazu steht die Vorgehensweise, wie der Code mithilfe einer Ausnahmedatei verarbeitet wird: Der Ausnahmefilterausdruck ergibt `false`. Daher geht die Ausnahme nie in die `catch`-Klausel hinein. Da die `catch`-Klausel nicht ausgeführt wird, findet keine Stapelentladung statt. Das bedeutet, dass die ursprüngliche Auslöseposition für jegliche Debugaktivitäten beibehalten wird, die später ausgeführt werden wird.

Wann immer Sie Felder oder Eigenschaften einer Ausnahme auswerten müssen, anstatt sich ausschließlich auf den Ausnahmetyp zu verlassen, verwenden Sie einen Ausnahmefilter, um weitere Debuginformationen beizubehalten.

Ein weiteres empfohlenen Muster mit Ausnahmefiltern ist, diese für die Protokollierung von Routinen zu verwenden. Diese Verwendung nutzt auch die Art, wie der Auslösepunkt der Ausnahme beibehalten wird, wenn ein Ausnahmefilter `false` ergibt.

Eine Protokollierungsmethode wäre eine Methode, deren Argument die Ausnahme ist, die ohne Bedingung `false` zurückgibt:

[!code-csharp[ExceptionFilterLogging](../../../samples/snippets/csharp/new-in-6/ExceptionFilterHelpers.cs#ExceptionFilterLogging)]

Wenn Sie eine Ausnahme protokollieren möchten, können Sie eine Catch-Klausel hinzufügen und diese Methode als Ausnahmefilter verwenden:

[!code-csharp[LogException](../../../samples/snippets/csharp/new-in-6/program.cs#LogException)]

Die Ausnahmen werden nie abgefangen, da die `LogException`-Methode immer `false` zurückgibt. Der Ausnahmefilter „always false“ (immer falsch) bedeutet, dass Sie diesen Logging Handler vor jedem anderen Ausnahmehandler platzieren können.

[!code-csharp[LogExceptionRecovery](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionRecovery)]

Im vorherigen Beispiel wird ein sehr wichtiger Aspekt der Ausnahmefilter hervorgehoben.
Die Ausnahmefilter ermöglichen Szenarios, in denen eine allgemeine Ausnahme-Catch-Klausel vor einer spezifischeren angezeigt werden kann. Es ist auch möglich, dass derselbe Ausnahmetyp in mehrere Catch-Klauseln vorkommt:

[!code-csharp[HandleNotChanged](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#HandleNotChanged)]

Ein weiteres empfohlenen Muster hilft zu verhindern, dass Catch-Klauseln Ausnahmen verarbeiten, wenn ein Debugger angefügt wird. Mit dieser Technik können Sie eine Anwendung mit dem Debugger ausführen und diese Ausführung anhalten, wenn eine Ausnahme ausgelöst wird.

Fügen Sie in ihrem Code einen Ausnahmefilter hinzu, damit jeder Wiederherstellungscode nur ausgeführt wird, wenn kein Debugger angefügt ist.

[!code-csharp[LogExceptionDebugger](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionDebugger)]

Nachdem Sie diesen in den Code hinzugefügt haben, richten Sie Ihren Debugger so ein, dass er alle Ausnahmefehler unterbrechen soll. Führen Sie das Programm unter dem Debugger aus, und der Debugger unterbricht jedes Mal, wenn `PerformFailingOperation()` eine `RecoverableException` auslöst.
Der Debugger unterbricht das Programm, da aufgrund des falsch zurückgegebenen Ausnahmefilters die Catch-Klausel nicht ausgeführt werden würde.

## <a name="nameof-expressions"></a>`nameof`-Ausdrücke

Der `nameof`-Ausdruck wertet den Namen des Symbols aus. Es ist eine hervorragende Möglichkeit, Tools zum Arbeiten zu bringen, wenn Sie den Namen einer Variable, Eigenschaften oder eines Memberfelds benötigen.

Eine der häufigsten Verwendungszwecke für `nameof` besteht darin, den Namen eines Symbols bereitzustellen, die eine Ausnahme ausgelöst hat:

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

Sie können den Ausdruck auch mit auf XAML basierenden Anwendungen verwenden, die die `INotifyPropertyChanged`-Schnittstelle implementieren.

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

Der Vorteil der Verwendung des `nameof`-Operators im Gegensatz zu einer konstanten Zeichenfolge ist, dass Tools das Symbol verstehen können. Wenn Sie Umgestaltungstools verwenden, um das Symbol umzubenennen, wird es im `nameof`-Ausdruck umbenannt. Konstante Zeichenfolgen besitzen nicht diesen Vorteil. Probieren Sie es in Ihrem bevorzugten Editor aus: Benennen Sie eine Variable um, und jeder `nameof`-Ausdruck wird ebenso aktualisiert.

Der `nameof`-Ausdruck erstellt den unqualifizierten Namen seines Arguments (`LastName` in den vorherigen Beispielen), auch wenn Sie den vollqualifizierten Namen für das Argument verwenden:

[!code-csharp[QualifiedNameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#QualifiedNameofNotify)]

Dieser `nameof`-Ausdruck erzeugt `FirstName` und nicht `UXComponents.ViewModel.FirstName`.

## <a name="await-in-catch-and-finally-blocks"></a>„Await“ in Catch- und Finally-Blöcken

C# 5 hat mehrere Einschränkungen im Hinblick auf die Position von `await`-Ausdrücken.
Eine solche wurde in C#6 entfernt. Sie können nun `await` in `catch`- oder `finally`-Ausdrücken verwenden. 

Das Hinzufügen von await-Ausdrücken in Catch- und Finally-Blöcken scheint die Verarbeitung von diesen zu erschweren. Lassen Sie uns ein Beispiel hinzufügen, um zu Erläutern, warum das so ist. In einer async-Methode können Sie einen await-Ausdruck in einer Finally-Klausel verwenden.

Mit C# 6 können Sie await auch in Catch-Ausdrücken verwenden. Dies wird am häufigsten in Protokollierungsszenarios verwendet:

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

Die Implementierungsdetails für das Hinzufügen von `await`-Unterstützung in `catch`- und `finally`-Klauseln stellt sicher, dass das Verhalten konsistent mit dem Verhalten für synchronen Code ist. Wenn Code, der in einer `catch`- oder `finally`-Klausel ausgeführt wird, ausgelöst wird, so sucht die Ausführung nach einer passenden `catch`-Klausel im nächsten Block in der Umgebung. Wenn eine aktuelle Ausnahme aufgetreten ist, geht diese Ausnahme verloren. Das Gleiche passiert bei erwarteten Ausdrücken in `catch`- und `finally`-Klauseln: eine passende `catch` wird gesucht und die aktuelle Ausnahme, falls vorhanden, geht verloren.  

> [!NOTE]
> Dieses Verhalten ist der Grund, warum es empfohlen wird, `catch`- und `finally`-Klauseln sorgfältig zu schreiben, um die Einführung neuer Ausnahmen zu vermeiden.

## <a name="index-initializers"></a>Indexinitialisierer

Der *Indexinitialisierer* ist eines von zwei Features, die Auflistungsinitialisierer konsistenter mit der Indexnutzung machen. In früheren Releases von C# konnten Sie *Auflistungsinitialisierer* nur mit Auflistungen im Sequenzformat mit <xref:System.Collections.Generic.Dictionary%602> verwenden, indem Sie Klammern um Schlüssel- und Wertpaare gesetzt haben:

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#ListInitializer)]

Sie können diese nun mit <xref:System.Collections.Generic.Dictionary%602>-Auflistungen und ähnlichen Typen verwenden. Die neue Syntax unterstützt Zuweisungen mit einem Index in die Auflistung:

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

Dieses Feature bedeutet, dass assoziative Container mithilfe von Syntax initialisiert werden können, die ähnlich dem ist, was für Sequenzcontainern für einige Versionen vorhanden war.

## <a name="extension-add-methods-in-collection-initializers"></a>Erweiterungs-`Add`-Methoden in Auflistungsinitialisierern

Ein weiteres Feature zur Vereinfachung der Auflistungsinitialisierer ist die Möglichkeit, eine *Erweiterungsmethode* für die `Add`-Methode zu verwenden. Dieses Feature wurde für die Parität mit Visual Basic hinzugefügt. 

Das Feature ist am nützlichsten, wenn Sie über eine benutzerdefinierte Auflistungsklasse verfügen, die eine Methode mit einem anderen Namen besitzt, um semantisch neue Elemente hinzuzufügen.

Betrachten Sie z.B. eine Auflistung von Studenten, die wie folgt aussieht:

[!code-csharp[Enrollment](../../../samples/snippets/csharp/new-in-6/enrollment.cs#Enrollment)]

Die `Enroll`-Methode fügt einen Studenten hinzu. Aber dies entspricht nicht den Regeln des `Add`-Musters.
In früheren Versionen von C# konnten Sie keine Auflistungsinitialisierer mit einem `Enrollment`-Objekt benutzen.

[!code-csharp[InitializeEnrollment](../../../samples/snippets/csharp/new-in-6/classList.cs#InitializeEnrollment)]

Das können Sie nun tun, jedoch nur, wenn Sie eine Erweiterungsmethode erstellen, die `Add` `Enroll` zuordnet.

[!code-csharp[ExtensionAdd](../../../samples/snippets/csharp/new-in-6/classList.cs#ExtensionAdd)]

Mit diesem Feature ordnen Sie die Methode, die Elemente zu einer Auflistung hinzufügt, einer Methode mit dem Namen `Add` zu, indem Sie eine Erweiterungsmethode erstellen.

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

