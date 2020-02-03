---
title: Dim-Anweisung
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: 1b0c3089c366c417af926c8c0703cea021674432
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744721"
---
# <a name="dim-statement-visual-basic"></a>Dim-Anweisung (Visual Basic)

Deklariert und ordnet Speicherplatz für eine oder mehrere Variablen zu.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a>Bestandteile

- `attributelist`

  Optional. Siehe [Attribut Liste](attribute-list.md).

- `accessmodifier`

  Optional. Dabei kann es sich um eine der folgenden Methoden handeln:

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Privat](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Private Protected](../modifiers/private-protected.md)

  Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `Shared`

  Optional. Siehe [Shared](../modifiers/shared.md).

- `Shadows`

  Optional. Siehe [Shadows](../modifiers/shadows.md).

- `Static`

  Optional. Siehe [static](../modifiers/static.md).

- `ReadOnly`

  Optional. Siehe [nur](../modifiers/readonly.md)lesen.

- `WithEvents`

  Optional. Gibt an, dass es sich hierbei um Objektvariablen handelt, die auf Instanzen einer Klasse verweisen, die Ereignisse hervorrufen können. Siehe [wiwitvents](../modifiers/withevents.md).

- `variablelist`

  Erforderlich. Liste der Variablen, die in dieser Anweisung deklariert werden.

  `variable [ , variable ... ]`

  Jede `variable` weist folgende Syntax und Bestandteile auf:

  `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`

  |Teil|BESCHREIBUNG|
  |---|---|
  |`variablename`|Erforderlich. Name der Variable. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
  |`boundslist`|Optional. Die Liste der Begrenzungen der einzelnen Dimensionen einer Array Variablen.|
  |`New`|Optional. Erstellt eine neue Instanz der-Klasse, wenn die `Dim`-Anweisung ausgeführt wird.|
  |`datatype`|Optional. Datentyp der Variablen.|
  |`With`|Optional. Führt die Objektinitialisiererliste ein.|
  |`propertyname`|Optional. Der Name einer Eigenschaft in der Klasse, von der Sie eine Instanz erstellen.|
  |`propinitializer`|Erforderlich nach `propertyname` =. Der Ausdruck, der ausgewertet und dem Eigenschaftsnamen zugewiesen wird.|
  |`initializer`|Optional, wenn `New` nicht angegeben ist. Ausdruck, der ausgewertet und der Variablen bei der Erstellung zugewiesen wird.|

## <a name="remarks"></a>Hinweise

Der Visual Basic-Compiler verwendet die `Dim`-Anweisung, um den Datentyp der Variablen und andere Informationen zu bestimmen, z. b. den Code, auf den die Variable zugreifen kann. Im folgenden Beispiel wird eine Variable deklariert, die einen `Integer` Wert enthält.

```vb
Dim numberOfStudents As Integer
```

Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

Für einen Referenztyp verwenden Sie das `New`-Schlüsselwort, um eine neue Instanz der Klasse oder Struktur zu erstellen, die durch den-Datentyp angegeben wird. Wenn Sie `New`verwenden, verwenden Sie keinen initialisiererausdruck. Stattdessen geben Sie Argumente (falls erforderlich) an den Konstruktor der Klasse an, aus der Sie die Variable erstellen.

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

Sie können eine Variable in einer Prozedur, einem Block, einer Klasse, einer Struktur oder einem Modul deklarieren. Sie können eine Variable nicht in einer Quelldatei, einem Namespace oder einer Schnittstelle deklarieren. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).

Eine Variable, die auf Modulebene, außerhalb einer Prozedur deklariert wird, ist eine *Member-Variable* oder ein- *Feld*. Element Variablen befinden sich im Gültigkeitsbereich der Klasse, Struktur oder des Moduls. Eine Variable, die auf Prozedur Ebene deklariert wird, ist eine *lokale Variable*. Lokale Variablen befinden sich nur innerhalb ihrer Prozedur oder Ihres Blocks im Gültigkeitsbereich.

Die folgenden Zugriffsmodifizierer werden verwendet, um Variablen außerhalb einer Prozedur zu deklarieren: `Public`, `Protected`, `Friend`, `Protected Friend`und `Private`. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Das `Dim`-Schlüsselwort ist optional und wird normalerweise ausgelassen, wenn Sie einen der folgenden Modifizierer angeben: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`oder `WithEvents`.

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

Wenn `Option Explicit` aktiviert ist (Standardeinstellung), benötigt der Compiler eine Deklaration für jede Variable, die Sie verwenden. Weitere Informationen finden Sie unter [Option explizite Anweisung](option-explicit-statement.md).

## <a name="specifying-an-initial-value"></a>Angeben eines Anfangs Werts

Sie können einer Variablen einen Wert zuweisen, wenn Sie erstellt wird. Bei einem Werttyp verwenden Sie einen *Initialisierer* , um einen Ausdruck anzugeben, der der Variablen zugewiesen werden soll. Der Ausdruck muss zu einer Konstanten ausgewertet werden, die zur Kompilierzeit berechnet werden kann.

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

Wenn ein Initialisierer angegeben wird und ein Datentyp nicht in einer `As`-Klausel angegeben ist, wird der *Typrückschluss* verwendet, um den Datentyp vom Initialisierer abzuleiten. Im folgenden Beispiel sind sowohl `num1` als auch `num2` stark als ganze Zahlen typisiert. In der zweiten Deklaration leitet der Typrückschluss den Typ aus dem Wert 3 ab.

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

Der Typrückschluss gilt für die Prozedur Ebene. Sie gilt nicht außerhalb einer Prozedur in einer Klasse, Struktur, einem Modul oder einer Schnittstelle. Weitere Informationen zum Typrückschluss finden Sie unter [Option Infer-Anweisung](option-infer-statement.md) und [lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md).

Informationen dazu, was geschieht, wenn ein Datentyp oder ein Initialisierer nicht angegeben wird, finden Sie unter [Standard Datentypen und-Werte](dim-statement.md#default) weiter unten in diesem Thema.

Sie können einen *Objektinitialisierer* verwenden, um Instanzen von benannten und anonymen Typen zu deklarieren. Der folgende Code erstellt eine Instanz einer `Student`-Klasse und verwendet einen Objektinitialisierer, um Eigenschaften zu initialisieren.

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

Weitere Informationen zu Objektinitialisierern finden Sie unter Gewusst [wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Objektinitialisierer: benannte und anonyme Typen](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)und [Anonyme Typen](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).

## <a name="declaring-multiple-variables"></a>Deklarieren mehrerer Variablen

Sie können mehrere Variablen in einer Deklarations Anweisung deklarieren, den Variablennamen für jede Deklaration angeben und den einzelnen Array Namen mit Klammern folgen. Mehrere Variablen werden durch Kommas voneinander getrennt.

```vb
Dim lastTime, nextTime, allTimes() As Date
```

Wenn Sie mehr als eine Variable mit einer `As`-Klausel deklarieren, können Sie keinen Initialisierer für diese Gruppe von Variablen bereitstellen.

Sie können unterschiedliche Datentypen für verschiedene Variablen angeben, indem Sie für jede deklarierte Variable eine separate `As`-Klausel verwenden. Jede Variable übernimmt den Datentyp, der in der ersten `As`-Klausel nach dem `variablename` Teil angegeben wurde.

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a>Arrays

Sie können eine Variable so deklarieren, dass Sie ein *Array*enthält, das mehrere Werte enthalten kann. Um anzugeben, dass eine Variable ein Array enthält, befolgen Sie die entsprechenden `variablename` sofort mit Klammern. Weitere Informationen zu Arrays finden Sie unter [Arrays](../../programming-guide/language-features/arrays/index.md).

Sie können die untere und obere Grenze der einzelnen Dimensionen eines Arrays angeben. Fügen Sie zu diesem Zweck eine `boundslist` in die Klammern ein. Für jede Dimension gibt das `boundslist` die obere Grenze und optional die untere Grenze an. Die untere Grenze ist immer 0 (null), unabhängig davon, ob Sie Sie angeben oder nicht. Jeder Index kann von 0 (null) bis zum oberen Grenzwert abweichen.

Die folgenden zwei Anweisungen sind gleichwertig. Jede-Anweisung deklariert ein Array aus 21 `Integer`-Elementen. Wenn Sie auf das Array zugreifen, kann der Index von 0 bis 20 abweichen.

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

Mit der folgenden Anweisung wird ein zweidimensionales Array vom Typ "`Double`" deklariert. Das Array hat vier Zeilen (3 + 1) von 6 Spalten (jeweils 5 + 1). Beachten Sie, dass eine obere Grenze den höchstmöglichen Wert für den Index und nicht die Länge der Dimension darstellt. Die Länge der Dimension ist die obere Grenze plus 1.

```vb
Dim matrix2(3, 5) As Double
```

Ein Array kann zwischen 1 und 32 Dimensionen aufweisen.

Sie können alle Begrenzungen in einer Array Deklaration leer lassen. Wenn Sie dies tun, verfügt das Array über die Anzahl der Dimensionen, die Sie angeben, aber es ist nicht initialisiert. Sie weist den Wert `Nothing` auf, bis Sie mindestens einige ihrer Elemente initialisieren. Die `Dim`-Anweisung muss Begrenzungen entweder für alle Dimensionen oder für keine Dimensionen angeben.

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

Wenn das Array über mehr als eine Dimension verfügt, müssen Sie Kommas zwischen den Klammern einschließen, um die Anzahl der Dimensionen anzugeben.

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

Sie können ein *Array der Länge 0 (null* ) deklarieren, indem Sie eine der Dimensionen des Arrays als-1 deklarieren. Eine Variable, die ein Array der Länge 0 (null) enthält, hat nicht den Wert `Nothing`. Arrays der Länge 0 (null) sind für bestimmte Common Language Runtime Funktionen erforderlich. Wenn Sie versuchen, auf ein solches Array zuzugreifen, tritt eine Lauf Zeit Ausnahme auf. Weitere Informationen finden Sie unter [Arrays](../../programming-guide/language-features/arrays/index.md).

Sie können die Werte eines Arrays mithilfe eines Arrayliterals initialisieren. Umschließen Sie zu diesem Zweck die Initialisierungs Werte mit geschweiften Klammern (`{}`).

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

Bei mehrdimensionalen Arrays wird die Initialisierung für jede separate Dimension in geschweifte Klammern in der äußeren Dimension eingeschlossen. Die Elemente werden in der Reihenfolge der Zeilen angegeben.

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

Weitere Informationen zu Array literalen finden Sie unter [Arrays](../../programming-guide/language-features/arrays/index.md).

## <a name="default"></a>Standard Datentypen und-Werte

Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Spezifizierung von Datentyp und Initialisierung in einer `Dim`-Anweisung.

|Datentyp angegeben?|Initialisierung angegeben?|Beispiel|Ergebnis|
|---|---|---|---|
|Nein|Nein|`Dim qty`|Wenn [Option Strict](option-strict-statement.md) auf OFF festgelegt ist (Standardeinstellung), wird die Variable auf `Nothing`festgelegt.<br /><br /> Wenn `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.|
|Nein|Ja|`Dim qty = 5`|Wenn die [Option Infer](option-infer-statement.md) auf on (The default) (Standard) eingestellt ist, übernimmt die Variable den Datentyp des Initialisierers. Siehe [lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.<br /><br /> Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.|
|Ja|Nein|`Dim qty As Integer`|Die Variable wird auf den Standardwert für den Datentyp initialisiert. Informationen finden Sie in der Tabelle weiter unten in diesem Abschnitt.|
|Ja|Ja|`Dim qty  As Integer = 5`|Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.|

Wenn Sie einen Datentyp angeben, aber keinen Initialisierer angeben, initialisiert Visual Basic die Variable mit dem Standardwert für ihren Datentyp. In der folgenden Tabelle werden die Standardinitialisierungswerte angezeigt.

|Datentyp|Standardwert|
|---|---|
|Alle numerischen Typen (einschließlich `Byte` und `SByte`)|0|
|`Char`|Binärdatei 0|
|Alle Verweis Typen (einschließlich `Object`, `String`und alle Arrays)|`Nothing`|
|`Boolean`|`False`|
|`Date`|12:00 Uhr vom 1. Januar des Jahres 1 (01/01/0001 12:00:00 Uhr)|

Jedes Element einer Struktur wird initialisiert, als handele es sich um eine separate Variable. Wenn Sie die Länge eines Arrays deklarieren, jedoch nicht die zugehörigen Elemente initialisieren, wird jedes Element so initialisiert, als wäre es eine separate Variable.

## <a name="static-local-variable-lifetime"></a>Lebensdauer statischer lokaler Variablen

Eine `Static` lokale Variable hat eine längere Lebensdauer als die der Prozedur, in der Sie deklariert ist. Die Grenzen der Variablen Lebensdauer hängen davon ab, wo die Prozedur deklariert wird und ob Sie `Shared`ist.

|Prozedur Deklaration|Variable initialisiert|Variable beendet vorhandene|
|---|---|---|
|In einem Modul|Wenn die Prozedur zum ersten Mal aufgerufen wird|Wenn das Programm die Ausführung beendet|
|In einer Klasse oder Struktur ist die Prozedur `Shared`|Wenn die Prozedur zum ersten Mal entweder für eine bestimmte Instanz oder für die Klasse oder Struktur selbst aufgerufen wird.|Wenn das Programm die Ausführung beendet|
|In einer Klasse oder Struktur ist die Prozedur nicht `Shared`|Wenn die Prozedur zum ersten Mal für eine bestimmte Instanz aufgerufen wird|Wenn die Instanz für Garbage Collection (GC) freigegeben wird|

## <a name="attributes-and-modifiers"></a>Attribute und modifiziererer

Attribute können nur auf Element Variablen, nicht auf lokale Variablen angewendet werden. Ein Attribut trägt Informationen zu den Metadaten der Assembly bei, was für temporäre Speicherung, z. b. lokale Variablen, nicht sinnvoll ist.

Auf Modulebene können Sie den `Static` Modifizierer nicht verwenden, um Element Variablen zu deklarieren. Auf Prozedur Ebene können Sie keine `Shared`, `Shadows`, `ReadOnly`, `WithEvents`oder Zugriffsmodifizierer verwenden, um lokale Variablen zu deklarieren.

Sie können angeben, welcher Code auf eine Variable zugreifen kann, indem Sie eine `accessmodifier`bereitstellen. Klassen-und Modulmember-Variablen (außerhalb einer beliebigen Prozedur) werden standardmäßig auf den privaten Zugriff und die Strukturelement Variablen standardmäßig auf den öffentlichen Zugriff eingestellt. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Sie können keine Zugriffsmodifizierer für lokale Variablen (innerhalb einer Prozedur) verwenden.

Sie können `WithEvents` nur für Element Variablen angeben, nicht für lokale Variablen in einer Prozedur. Wenn Sie `WithEvents`angeben, muss es sich beim Datentyp der Variablen um einen bestimmten Klassentyp handeln, nicht um `Object`. Sie können ein Array nicht mit `WithEvents`deklarieren. Weitere Informationen zu Ereignissen finden Sie unter [Ereignisse](../../programming-guide/language-features/events/index.md).

> [!NOTE]
> Code außerhalb einer Klasse, Struktur oder eines Moduls muss den Namen einer Element Variablen mit dem Namen der Klasse, Struktur oder des Moduls qualifizieren. Code außerhalb einer Prozedur oder eines Blocks kann nicht auf lokale Variablen innerhalb dieser Prozedur oder eines Blocks verweisen.

## <a name="releasing-managed-resources"></a>Freigeben von verwalteten Ressourcen

Der .NET Framework Garbage Collector verwaltete Ressourcen frei, ohne dass zusätzliche Codierungen vorhanden sind. Sie können jedoch die Freigabe einer verwalteten Ressource erzwingen, anstatt auf die Garbage Collector zu warten.

Wenn eine Klasse eine besonders wertvolle und knappe Ressource (z. b. eine Datenbankverbindung oder ein Datei Handle) speichert, möchten Sie möglicherweise nicht warten, bis die nächste Garbage Collection eine nicht mehr verwendete Klasseninstanz bereinigen. Eine Klasse kann die <xref:System.IDisposable>-Schnittstelle implementieren, um eine Möglichkeit bereitzustellen, Ressourcen vor einem Garbage Collection freizugeben. Eine Klasse, die diese Schnittstelle implementiert, macht eine `Dispose` Methode verfügbar, die aufgerufen werden kann, um zu erzwingen, dass wertvolle Ressourcen sofort freigegeben werden.

Die `Using`-Anweisung automatisiert das Abrufen einer Ressource, das Ausführen eines Satzes von Anweisungen und das anschließende verwerfen der Ressource. Die Ressource muss jedoch die <xref:System.IDisposable>-Schnittstelle implementieren. Weitere Informationen finden Sie unter [using-Anweisung](using-statement.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden Variablen mithilfe der `Dim`-Anweisung mit verschiedenen Optionen deklariert.

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden die Primzahlen zwischen 1 und 30 aufgelistet. Der Bereich der lokalen Variablen wird in den Code Kommentaren beschrieben.

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die `speedValue` Variable auf Klassenebene deklariert. Das `Private`-Schlüsselwort wird verwendet, um die Variable zu deklarieren. Auf die Variable kann von jeder Prozedur in der `Car`-Klasse zugegriffen werden.

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a>Weitere Informationen

- [Const-Anweisung](const-statement.md)
- [ReDim-Anweisung](redim-statement.md)
- [Option Explicit-Anweisung](option-explicit-statement.md)
- [Option Infer-Anweisung](option-infer-statement.md)
- [Option Strict-Anweisung](option-strict-statement.md)
- [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Variablendeklaration](../../programming-guide/language-features/variables/variable-declaration.md)
- [Arrays](../../programming-guide/language-features/arrays/index.md)
- [Objektinitialisierer: Benannte und anonyme Typen](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Anonyme Typen](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Objektinitialisierer: Benannte und anonyme Typen](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [Lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md)
