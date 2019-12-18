---
title: Neues in Visual Basic
ms.date: 10/24/2018
f1_keywords:
- VB.StartPage.WhatsNew
helpviewer_keywords:
- new features, Visual Basic
- what's new [Visual Basic]
- Visual Basic, what's new
ms.assetid: d7e97396-7f42-4873-a81c-4ebcc4b6ca02
ms.openlocfilehash: 45763504c2d25596b0adfb4b8a0236b332d89e8c
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802046"
---
# <a name="whats-new-for-visual-basic"></a>Neues in Visual Basic

In diesem Thema sind die Namen der wichtigsten Funktionen für jede Version von Visual Basic mit ausführlichen Beschreibungen der neuen und verbesserten Funktionen in der aktuellen Version der Sprache aufgelistet.

## <a name="current-version"></a>Aktuelle Version

Visual Basic 16.0/Visual Studio 2019 Version 16.0\
Weitere Informationen zu neuen Features finden Sie unter [Visual Basic 16.0](#visual-basic-160).

## <a name="previous-versions"></a>Frühere Versionen

Visual Basic 15.8/Visual Studio 2017 Version 15.8\
Informationen zu neuen Features finden Sie unter [Visual Basic 15.8](#visual-basic-158).

Visual Basic 15.5/Visual Studio 2017 Version 15.5\
Informationen zu neuen Features finden Sie unter [Visual Basic 15.5](#visual-basic-155).

Visual Basic 15.3/Visual Studio 2017 Version 15.3\
Informationen zu neuen Features finden Sie unter [Visual Basic 15.3](#visual-basic-153).

Visual Basic 2017/Visual Studio 2017\
Informationen zu neuen Features finden Sie unter [Visual Basic 2017](#visual-basic-2017).

Visual Basic/Visual Studio 2015\
Informationen zu neuen Features finden Sie unter [Visual Basic 14](#visual-basic-14).

Visual Basic/Visual Studio 2013\
Technologievorschau von .NET Compiler Platform („Roslyn“)

Visual Basic/Visual Studio 2012\
Die Schlüsselwörter `Async` und `await`, Iteratoren, Aufruferinformationsattribute

Visual Basic/Visual Studio 2010\
Automatisch implementierte Eigenschaften, Auflistungsinitialisierer, implizite Zeilenfortsetzung, dynamische, generische Ko-/Kontravarianz, Zugriff auf globalen Namespace

Visual Basic/Visual Studio 2008\
Language Integrated Query (LINQ), XML-Literale, lokaler Typrückschluss, Objektinitialisierer, anonyme Typen, Erweiterungsmethoden, lokaler `var`-Typrückschluss, Lambda-Ausdrücke, `if`-Operator, partielle Methoden, auf NULL festlegbare Werttypen

Visual Basic/Visual Studio 2005\
Der `My`-Typ und Hilfstypen (Zugriff auf App, Computer, Dateisystem, Netzwerk)

Visual Basic/Visual Studio .NET 2003\
Bitschiebeoperatoren, Deklaration von Schleifenvariablen

Visual Basic/Visual Studio .NET 2002\
Die erste Version von Visual Basic .NET

## <a name="visual-basic-160"></a>Visual Basic 16.0

Bei Visual Basic 16.0 liegt der Fokus darauf, weitere Features der Visual Basic-Laufzeit (microsoft.visualbasic.dll) für .NET Core bereitzustellen, und ist die erste Version von Visual Basic, die auf .NET Core ausgelegt ist. Viele Teile der Visual Basic-Laufzeit sind von WinForms abhängig und werden in einer späteren Version von Visual Basic hinzugefügt.

**Kommentare sind an weiteren Stellen innerhalb von Anweisungen zulässig**

In Visual Basic 15.8 und früheren Versionen sind Kommentare nur in leeren Zeilen, am Ende von Anweisungen oder an bestimmten Stellen in einer Anweisung zulässig, an denen implizite Zeilenfortsetzungen erlaubt sind. Ab Visual Basic 16.0 sind Kommentare auch nach expliziten Zeilenfortsetzungen und innerhalb von Anweisungen in Zeilen zulässig, die mit einem Leerzeichen gefolgt von einem Unterstrich beginnen.

```vb
Public Sub Main()
    cmd.CommandText = ' Comment is allowed here without _
        "SELECT * FROM Titles JOIN Publishers " _ ' This is a comment
        & "ON Publishers.PubId = Titles.PubID " _
 _ ' This is a comment on a line without code
        & "WHERE Publishers.State = 'CA'"
End Sub
```

## <a name="visual-basic-158"></a>Visual Basic 15.8

**Optimierte Konvertierung von Gleitkommazahlen in ganze Zahlen**

Frühere Visual Basic-Versionen erzielten beim Konvertieren von [doppelten](../language-reference/data-types/double-data-type.md) und [einzelnen](../language-reference/data-types/single-data-type.md) Werten in ganze Zahlen eine relativ schlechte Leistung. Visual Basic 15.8 weist eine deutlich verbesserte Leistung beim Konvertieren von Gleitkomma- in ganze Zahlen auf, wenn Sie den Wert, der durch eine der folgenden Methoden zurückgegeben wird, an eine [intrinsische Visual Basic-Konvertierungsfunktion für ganze Zahlen](../language-reference/functions/type-conversion-functions.md) (CByte, CShort, CInt, CLng, CSByte, CUShort, CUInt, CULng) übergeben, oder wenn der durch eine der folgenden Methoden zurückgegebene Wert implizit in einen integralen Typ umgewandelt wird, wenn [Option Strict](../language-reference/statements/option-strict-statement.md) auf `Off` festgelegt ist:

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

Dank dieser Optimierung kann Code schneller ausgeführt werden. Code, der viele Ganzzahltypen konvertiert, wird bis zu doppelt so schnell ausgeführt. Das folgende Beispiel veranschaulicht einige einfache Methodenaufrufe, die von dieser Optimierung betroffen sind:

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

Beachten Sie, dass diese Option die Gleitkommawerte kürzt und nicht rundet.

## <a name="visual-basic-155"></a>Visual Basic 15.5

[Nicht schließende benannte Argumente](../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md#mixing-arguments-by-position-and-by-name)

In Visual Basic 15.3 und früheren Versionen mussten positionelle vor benannten Argumenten stehen, wenn ein Methodenaufruf sowohl Argumente nach Position als auch nach Namen beinhaltete. Ab Visual Basic 15.5 können positionelle und benannte Argumente in beliebiger Reihenfolge angeordnet werden, solange sich alle Argumente bis zum letzten positionellen Argument an der korrekten Position befinden. Dies ist besonders dann nützlich, wenn benannte Argumente verwendet werden, um Code lesbarer zu machen.

Der folgende Methodenaufruf hat beispielsweise zwei positionelle Argumente zwischen einem benannten Argument. Das benannte Argument gibt an, dass der Wert 19 für ein Alter steht.

```vb
StudentInfo.Display("Mary", age:=19, #9/21/1998#)
```

[Zugriffsmodifizierer `Private Protected` für Member](../language-reference/modifiers/private-protected.md)

Diese neue Schlüsselwortkombination definiert einen Member, auf den alle Member seiner enthaltenden Klasse sowie Typen, die von der enthaltenden Klasse abgeleitet sind, zugreifen können, wenn sie sich auch in der enthaltenden Assembly befinden. Da Strukturen nicht geerbt werden können, kann `Private Protected` nur auf die Member einer Klasse angewendet werden.

**Führendes Hexadezimal-/Binär-/Oktaltrennzeichen**

Mit Visual Basic 2017 wurde Unterstützung für das Unterstrichzeichen (`_`) als Zifferntrennzeichen hinzugefügt. Sie können ab Visual Basic 15.5 den Unterstrich als vorangestelltes Trennzeichen zwischen dem Präfix und Hexadezimal-, Binär- oder Oktalziffern verwenden. Im folgenden Beispiel wird ein Trennzeichen für vorangestellte Ziffern verwendet, um 3.271.948.384 als hexadezimale Zahl zu definieren:

```vb
Dim number As Integer = &H_C305_F860
```

Um den Unterstrich als vorangestelltes Trennzeichen verwenden zu können, müssen Sie Ihrer Visual Basic-Projektdatei (\*.vbproj) das folgende Element hinzufügen:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="visual-basic-153"></a>Visual Basic 15.3

[**Rückschluss auf benannte Tupel**](../programming-guide/language-features/data-types/tuples.md#inferred-tuple-element-names)

Wenn Sie den Wert von Tupelelementen von Variablen zuweisen, leitet Visual Basic den Namen der Typelelemente von den entsprechenden Variablennamen ab. Sie müssen ein Tupelelement nicht explizit benennen. In folgendem Beispiel werden Rückschlüsse verwendet, um ein Tupel mit drei benannten Elementen, `state`, `stateName` und `capital`, zu erstellen.

[!code-vb[Inferred tuple names](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

**Zusätzliche Compileroptionen**

Der Visual Basic-Befehlszeilencompiler unterstützt nun die zusätzlichen Compileroptionen[**-refout**](../reference/command-line-compiler/refout-compiler-option.md) und [**-refonly**](../reference/command-line-compiler/refonly-compiler-option.md) zur Steuerung der Ausgabe von Verweisassemblys. **-refout** definiert das Ausgabeverzeichnis der Referenzassembly, und **-refonly** legt fest, dass nur eine Referenzassembly bei der Kompilierung ausgegeben wird.

## <a name="visual-basic-2017"></a>Visual Basic 2017

[**Tupel**](../programming-guide/language-features/data-types/tuples.md)

Tupel sind einfache Datenstrukturen, die am häufigsten für die Rückgabe von mehreren Werten aus einem einzelnen Methodenaufruf verwendet werden. Für gewöhnlich müssen Sie eine der folgenden Aktionen durchführen, um mehrere Werte aus einer Methode zurückzugeben:

- die Definition eines benutzerdefinierten Typs (eine `Class` oder eine `Structure`). Dabei handelt es sich um eine schwierige Lösung.

- die Definition von mindestens einem `ByRef`-Parameter zusätzlich zur Rückgabe eines Werts aus der Methode

Die Unterstützung für Tupel von Visual Basic erlaubt Ihnen die schnelle Definition von Tupeln, die optionale Zuweisung von semantischen Namen an deren Werte und das schnelle Abrufen dieser Werte. In folgendem Beispiel wird ein Aufruf der <xref:System.Int32.TryParse%2A>-Methode umschlossen und ein Tupel zurückgegeben.

[!code-vb[Tuple](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

Anschließend können Sie die Methode aufrufen und das zurückgegebene Tupel mit Code wie dem folgenden behandeln.

[!code-vb[ReturnTuple](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

**Binäre Literale und Zahlentrennzeichen**

Sie können ein binäres Literal definieren, indem Sie die Präfixe `&B` oder `&b` verwenden. Zusätzlich können Sie einen Unterstrich (`_`) als Zahlentrennzeichen verwenden, um die Lesbarkeit zu verbessern. In folgendem Beispiel werden Funktionen sowohl verwendet, um einen `Byte`-Wert zuzuweisen, als auch um ihn als Dezimal-, Hexadezimal- und binäre Zahl anzuzeigen.

[!code-vb[Binary](../../../samples/snippets/visualbasic/getting-started/bin-example.vb#1)]

Weitere Informationen finden Sie im Abschnitt „Zuweisung von Literalen“ der Datentypen [Byte](../language-reference/data-types/byte-data-type.md#literal-assignments), [Integer](../language-reference/data-types/integer-data-type.md#literal-assignments), [Long](../language-reference/data-types/long-data-type.md#literal-assignments), [Short](../language-reference/data-types/short-data-type.md#literal-assignments), [SByte](../language-reference/data-types/sbyte-data-type.md#literal-assignments), [UInteger](../language-reference/data-types/uinteger-data-type.md#literal-assignments), [ULong](../language-reference/data-types/ulong-data-type.md#literal-assignments) und [UShort](../language-reference/data-types/ushort-data-type.md#literal-assignments).

[**Support for C# reference return values (Unterstützung für Verweisrückgabewerte von C#)**](../programming-guide/language-features/procedures/ref-return-values.md)

Ab C# 7.0 unterstützt C# Verweisrückgabewerte. Das heißt, wenn die aufrufende Methode einen von einem Verweis zurückgegebenen Wert erhält, kann sie den Wert des Verweises ändern. In Visual Basic können Sie keine Methoden mit Verweisrückgabewerten erstellen. Allerdings können Sie Verweisrückgabewerte verarbeiten und modifizieren.

Die folgende in C# geschriebene `Sentence`-Klasse enthält z.B eine `FindNext`-Methode, die nach dem nächsten Wort in einer Sequenz sucht, die mit einer angegebenen Teilzeichenfolge beginnt. Die Zeichenfolge wird als Verweisrückgabewert zurückgegeben, und eine vom Verweis an die Methode übergebene `Boolean`-Variable gibt an, ob die Suche Erfolg hatte. Das bedeutet, dass der Aufrufer nicht nur den Rückgabewert lesen sondern auch modifizieren kann. Diese Modifizierung wird in der `Sentence`-Klasse widergespiegelt.

[!code-csharp[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

Sie können das in der Sequenz gefundene Wort in seiner einfachsten Form mit Code wie dem folgenden modifizieren. Beachten Sie, dass Sie nicht der Methode sondern dem Ausdruck, den die Methode zurückgibt, einen Wert zuweisen. Dabei handelt es sich um den Verweisrückgabewert.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return.vb#1)]

Bei diesem Code besteht jedoch das Problem, dass die Methode das erste Wort zurückgibt, wenn keine Übereinstimmung gefunden wurde. Da in dem Beispiel nicht der Wert des `Boolean`-Arguments untersucht wird, um festzustellen, ob eine Übereinstimmung gefunden wurde, wird das erste Wort modifiziert, wenn es keine Übereinstimmung gibt. In folgendem Beispiel wird dies korrigiert, indem das erste Wort durch sich selbst ersetzt wird, wenn es keine Übereinstimmung gibt.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return.vb#2)]

Eine sinnvollere Lösung ist das Verwenden einer Hilfsmethode, an die der Verweisrückgabewert vom Verweis übergeben wird. Die Hilfsmethode kann dann das an sie vom Verweis übergebene Argument modifizieren. In folgendem Beispiel wird dies getan.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

Weitere Informationen finden Sie unter [Verweisrückgabewerte](../programming-guide/language-features/procedures/ref-return-values.md).

## <a name="visual-basic-14"></a>Visual Basic 14

[NameOf](../language-reference/operators/nameof.md)

Sie können den nicht qualifizierten Zeichenfolgennamen eines Typs oder Members zur Verwendung in einer Fehlermeldung ohne Hartcodierung einer Zeichenfolge abrufen.  Dadurch bleibt der Code bei der Umgestaltung korrekt.  Diese Funktion eignet sich auch zum Einbinden von MVC-Links (Model-View-Controller) und das Auslösen von Ereignissen durch geänderte Eigenschaften.

[Zeichenfolgeninterpolation](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)

Sie können Ausdrücke für die Zeichenfolgeninterpolierung zum Erstellen von Zeichenfolgen verwenden.  Ein Ausdruck für eine interpolierte Zeichenfolge sieht wie eine Vorlagenzeichenfolge aus, die Ausdrücke enthält.  Eine interpolierte Zeichenfolge ist in Bezug auf die Argumente leichter zu verstehen als eine [Zusammengesetzte Formatierung](../../standard/base-types/composite-formatting.md).

[Memberzugriff und Indizierung mit NULL-Bedingung](../language-reference/operators/null-conditional-operators.md)

Sie können eine Prüfung auf null auf sehr einfache syntaktische Weise vornehmen, bevor Sie eine Operation für den Memberzugriff (`?.`) oder die Indizierung (`?[]`) ausführen.  Mithilfe dieser Operatoren müssen Sie für die Prüfung auf null weniger Code schreiben, insbesondere beim tieferen Eindringen in Datenstrukturen.  Wenn der linke Operand oder Objektverweis NULL ist, geben die Operationen NULL zurück.

[Multi-line string literals (Mehrzeilige Zeichenfolgenliterale)](../../visual-basic/programming-guide/language-features/strings/string-basics.md)

Zeichenfolgenliterale können Zeilenumbruchsequenzen enthalten.  Sie müssen nicht mehr die alte Problemumgehung mit `<xml><![CDATA[...text with newlines...]]></xml>.Value` verwenden.

**Kommentare**

Sie können Kommentare nach impliziten Zeilenfortsetzungen, innerhalb von Initialisierungsausdrücken und zwischen LINQ-Ausdrücken einfügen.

**Intelligentere Auflösung vollqualifizierter Namen**

Bei Code wie `Threading.Thread.Sleep(1000)` suchte Visual Basic bisher den Namespace "Threading", stellte fest, dass dieser mit "System.Threading" und "System.Windows.Threading" mehrdeutig war und meldete dann einen Fehler.  Nun berücksichtigt Visual Basic die beiden möglichen Namespaces gemeinsam.  Wenn Sie die Vervollständigungsliste anzeigen, listet der Visual Studio-Editor Member beider Typen in der Vervollständigungsliste auf.

**Datumsliterale mit Jahresangabe am Anfang**

Datumsliterale im Format jjjj-mm-tt sind möglich, z. B. `#2015-03-17 16:10 PM#`.

**Schreibgeschützte Schnittstelleneigenschaften**

Sie können mithilfe einer Readwrite-Eigenschaft schreibgeschützte Schnittstelleneigenschaften implementieren. Die Schnittstelle garantiert Mindestfunktionalität und hindert eine Implementierungsklasse nicht daran, die Festlegung der Eigenschaft zuzulassen.

[TypeOf \<expr> IsNot \<type>](../../visual-basic/language-reference/operators/typeof-operator.md)

Zur besseren Lesbarkeit des Codes können Sie nun `TypeOf` mit `IsNot` verwenden.

[#Disable Warning\<<ID> und #Enable Warning \<<ID>](../../visual-basic/language-reference/directives/index.md)

Sie können bestimmte Warnungen für Bereiche innerhalb einer Quelldatei deaktivieren und aktivieren.

**Verbesserungen bei XML-Dokumentationskommentaren**

Beim Schreiben von Dokumentationskommentaren steht intelligente Editor- und Buildunterstützung zum Überprüfen von Parameternamen, ordnungsgemäßer Handhabung von `crefs` (Generics, Operatoren usw.), Farben und Umgestaltung bereit.

[Partial Module and Interface Definitions (Partielle Modul- und Schnittstellendefinitionen)](../../visual-basic/language-reference/modifiers/partial.md)

Zusätzlich zu Klassen und Strukturen können Sie partielle Module und Schnittstellen deklarieren.

[#Region directives inside method bodies (#Region-Anweisungen in Methodentexten)](../../visual-basic/language-reference/directives/region-directive.md)

Sie können die Begrenzer #Region...#End Region an einer beliebigen Stelle in einer Datei, innerhalb von Funktionen und sogar Funktionsrümpfe übergreifend einfügen.

[Overrides definitions are implicitly overloads (Überschreibungsdefinitionen sind implizite Überladungen)](../../visual-basic/language-reference/modifiers/overrides.md)

Wenn Sie den `Overrides`-Modifizierer zu einer Definition hinzufügen, fügt der Compiler implizit `Overloads` hinzu, sodass Sie in allgemeinen Fällen weniger Code eingeben können.

**CObj in Attributargumenten zulässig**

Der Compiler gab gewöhnlich eine Fehlermeldung aus, dass CObj(...) bei Verwendung in Attributkonstruktionen keine Konstante war.

**Deklarieren und Verwenden mehrdeutiger Methoden von unterschiedlichen Schnittstellen**

Zuvor führte der folgende Code zu Fehlern, die Sie daran hinderten, `IMock` zu deklarieren oder `GetDetails` aufzurufen (wenn diese in C# deklariert waren):

```vb
Interface ICustomer
  Sub GetDetails(x As Integer)
End Interface

Interface ITime
  Sub GetDetails(x As String)
End Interface

Interface IMock : Inherits ICustomer, ITime
  Overloads Sub GetDetails(x As Char)
End Interface

Interface IMock2 : Inherits ICustomer, ITime
End Interface
```

Nun verwendet der Compiler normale Regeln zur Überladungsauflösung, um die am besten geeignete `GetDetails`-Methode zum Aufrufen auszuwählen, und Sie können Schnittstellenbeziehungen in Visual Basic deklarieren, wie sie im Beispiel gezeigt sind.

## <a name="see-also"></a>Siehe auch

- [Neues in Visual Studio 2017](/visualstudio/ide/whats-new-visual-studio-2017)
- [Neues in Visual Studio 2019](/visualstudio/ide/whats-new-visual-studio-2019)
