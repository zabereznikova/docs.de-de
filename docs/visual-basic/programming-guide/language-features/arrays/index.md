---
title: Arrays
ms.date: 12/06/2017
f1_keywords:
- vb.Array
helpviewer_keywords:
- arrays [Visual Basic]
- Visual Basic, arrays
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
ms.openlocfilehash: 5093f28f05c5b72294dce9a4e69723acafb31a9f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413091"
---
# <a name="arrays-in-visual-basic"></a>Arrays in Visual Basic

Ein Array ist ein Satz von Werten, die als *Elemente*bezeichnet werden, die logisch miteinander verknüpft sind. Ein Array kann z. b. aus der Anzahl von Schülern in den einzelnen Stufen in einer Grammatikschule bestehen. jedes Element des Arrays ist die Anzahl der Schüler/Studenten in einer einzelnen Klasse. Ebenso kann ein Array aus den Noten eines Studenten für eine Klasse bestehen. jedes Element des Arrays ist eine einzelne Klasse.

Einzelne Variablen können jedes unserer Datenelemente speichern. Wenn unsere Anwendung z. b. die Studenten Qualitäten analysiert, können wir eine separate Variable für die Qualität der einzelnen Studenten verwenden, z `englishGrade1` `englishGrade2` . b., usw. Dieser Ansatz hat drei wesentliche Einschränkungen:

- Wir müssen zur Entwurfszeit genau wissen, wie viele Qualitäten verarbeitet werden müssen.
- Die Verarbeitung einer großen Anzahl von Noten wird schnell zu unhandlich. Dies wiederum führt zu einer größeren Wahrscheinlichkeit, dass eine Anwendung schwerwiegende Fehler aufweist.
- Die Wartung ist schwierig. Jede neue, von uns hinzu zufügende Stufe erfordert, dass die Anwendung geändert, neu kompiliert und erneut bereitgestellt wird.

Mithilfe eines Arrays können Sie mit demselben Namen auf diese verknüpften Werte verweisen und eine Zahl verwenden, die als *Index oder Index* bezeichnet *wird, um* ein einzelnes Element auf der Grundlage seiner Position im Array zu identifizieren. Die Indizes eines Arrays reichen von 0 bis eins kleiner als die Gesamtzahl der Elemente im Array. Wenn Sie Visual Basic Syntax verwenden, um die Größe eines Arrays zu definieren, geben Sie den höchsten Index und nicht die Gesamtzahl der Elemente im Array an. Sie können mit dem Array als Einheit arbeiten, und durch die Möglichkeit, seine Elemente zu durchlaufen, müssen Sie nicht genau wissen, wie viele Elemente es zur Entwurfszeit enthält.

Hier einige Beispiele, bevor wir mit den Erklärungen starten:

```vb
' Declare a single-dimension array of 5 numbers.
Dim numbers(4) As Integer

' Declare a single-dimension array and set its 4 values.
Dim numbers = New Integer() {1, 2, 4, 8}

' Change the size of an existing array to 16 elements and retain the current values.
ReDim Preserve numbers(15)

' Redefine the size of an existing array and reset the values.
ReDim numbers(15)

' Declare a 6 x 6 multidimensional array.
Dim matrix(5, 5) As Double

' Declare a 4 x 3 multidimensional array and set array element values.
Dim matrix = New Integer(3, 2) {{1, 2, 3}, {2, 3, 4}, {3, 4, 5}, {4, 5, 6}}

' Declare a jagged array
Dim sales()() As Double = New Double(11)() {}
```

## <a name="array-elements-in-a-simple-array"></a>Array Elemente in einem einfachen Array

Erstellen Sie ein Array `students` mit dem Namen, um die Anzahl von Schülern in den einzelnen Stufen in einer Grammatikschule zu speichern. Die Indizes der Elemente reichen von 0 bis 6. Die Verwendung dieses Arrays ist einfacher, als sieben Variablen zu deklarieren.

Die folgende Abbildung zeigt das- `students` Array. Für jedes Element des Arrays gilt:

- Der Index des Elements steht für die Jahrgangsstufe (Index 0 (null) steht für die erste Jahrgangsstufe).

- Der im Element enthaltene Wert steht für die Anzahl der Schüler in dieser Jahrgangsstufe.

![Diagramm mit einem Array der Anzahl von Schülern](./media/index/students-array-elements.gif)

Das folgende Beispiel enthält den Visual Basic Code, der das Array erstellt und verwendet:

[!code-vb[simple-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/simple-array.vb)]

Im Beispiel werden drei Dinge ausgeführt:

- Er deklariert ein- `students` Array mit sieben Elementen. Die Zahl `6` in der Array Deklaration gibt den letzten Index im Array an. dieser Wert ist kleiner als die Anzahl der Elemente im Array.
- Jedem Element im Array werden Werte zugewiesen. Der Zugriff auf Array Elemente erfolgt über den Namen des Arrays und einschließlich des Index des einzelnen Elements in Klammern.
- Sie Listet jeden Wert des Arrays auf. Im Beispiel wird eine- [`For`](../../../language-reference/statements/for-next-statement.md) Anweisung verwendet, um auf die einzelnen Elemente des Arrays anhand der Indexnummer zuzugreifen.

Das `students` Array im vorangehenden Beispiel ist ein eindimensionales Array, da es einen Index verwendet. Ein Array, das mehr als einen Index oder Index verwendet, wird mehr *dimensional*genannt. Weitere Informationen finden Sie im restlichen Artikel und [in den Array Dimensionen in Visual Basic](array-dimensions.md).

## <a name="creating-an-array"></a>Erstellen eines Arrays

Sie können die Größe eines Arrays auf verschiedene Arten definieren:

- Sie können die Größe angeben, wenn das Array deklariert wird:

  [!code-vb[creating1](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#1)]

- Mithilfe einer-Klausel können Sie `New` die Größe eines Arrays bei der Erstellung angeben:

  [!code-vb[creating2](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#2)]

Wenn Sie über ein vorhandenes Array verfügen, können Sie seine Größe mit der-Anweisung neu definieren [`ReDim`](../../../language-reference/statements/redim-statement.md) . Sie können angeben, dass die- `ReDim` Anweisung die Werte im Array behält, oder Sie können angeben, dass ein leeres Array erstellt werden soll. Im folgenden Beispiel werden andere Möglichkeiten veranschaulicht, um mit der `ReDim` -Anweisung die Größe eines vorhandenen Arrays zu ändern.

[!code-vb[redimensioning](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#3)]

Weitere Informationen finden Sie in der [ReDim-Anweisung](../../../language-reference/statements/redim-statement.md).

## <a name="storing-values-in-an-array"></a>Speichern von Werten in einem Array

Sie können mit einem Index vom Typ `Integer`auf die einzelnen Positionen in einem Array zugreifen. Die Werte in einem Array können gespeichert und abgerufen werden, indem mit dem entsprechenden in Klammern eingeschlossenen Index auf die einzelnen Arraypositionen verwiesen wird. Indizes für mehrdimensionale Arrays sind durch Kommas (,) getrennt. Sie benötigen einen Index für jede Arraydimension.

Im folgenden Beispiel werden einige Anweisungen gezeigt, die Werte in Arrays speichern und abrufen.

[!code-vb[store-and-retrieve](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/store-and-retrieve.vb)]

## <a name="populating-an-array-with-array-literals"></a>Auffüllen eines Arrays mit Array literalen

Mithilfe eines Arrayliterals können Sie ein Array mit einem anfänglichen Satz von Werten gleichzeitig auffüllen, wenn Sie es erstellen. Ein Arrayliteral besteht aus einer Liste von durch Trennzeichen getrennten Werten, die in geschweifte Klammern (`{}`) eingeschlossen sind.

Beim Erstellen eines Arrays mit einem Arrayliteral können Sie den Arraytyp entweder angeben oder mittels Typrückschluss bestimmen. Im folgenden Beispiel werden beide Optionen gezeigt.

[!code-vb[create-with-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#4)]

Wenn Sie den Typrückschluss verwenden, wird der Typ des Arrays durch den *vorherrschenden Typ* in der Liste der Literalwerte bestimmt. Der vorherrschende Typ ist der Typ, auf den alle anderen Typen im Array ausgedehnt werden können. Wenn dieser eindeutige Typ nicht bestimmt werden kann, ist der bestimmende Typ der eindeutige Typ, auf den alle anderen Typen im Array eingegrenzt werden können. Wenn keiner dieser eindeutigen Typen bestimmt werden kann, ist der bestimmende Typ `Object`. Wenn die für das Arrayliteral angegebene Liste der Werte z. B. Werte vom Typ `Integer`, `Long`und `Double`enthält, weist das erhaltene Array den Typ `Double`auf. Da `Integer` und `Long` nur auf erweitert `Double` , `Double` ist der bestimmende Typ. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).

> [!NOTE]
> Sie können den Typrückschluss nur für Arrays verwenden, die in einem Typmember als lokale Variablen definiert sind. Wenn eine explizite Typdefinition nicht vorhanden ist, sind Arrays, die mit Array literalen auf Klassenebene definiert sind, vom Typ `Object[]` . Weitere Informationen finden Sie unter [lokaler Typrückschluss](../variables/local-type-inference.md).

Beachten Sie, dass das vorherige Beispiel `values` als Array vom Typ definiert, `Double` Obwohl alle Arrayliterale den Typ haben `Integer` . Sie können dieses Array erstellen, da die Werte im Arrayliteralen zu-Werten erweitert werden können `Double` .

Sie können auch ein mehrdimensionales Array erstellen und Auffüllen, indem Sie die *Literale des arrayarrays*verwenden. Die Literale für das arsted Array müssen über eine Reihe von Dimensionen verfügen, die mit dem resultierenden Array konsistent sind. Im folgenden Beispiel wird ein zweidimensionales Array von ganzen Zahlen erstellt, wobei die Literale des arrayarrays verwendet werden.

[!code-vb[nested-array-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#5)]

Wenn Sie zum Erstellen und Auffüllen eines Arrays ein Array verwenden, tritt ein Fehler auf, wenn die Anzahl der Elemente in den nicht übereinten Array literalen nicht entspricht. Ein Fehler tritt auch auf, wenn Sie die Array Variable explizit so deklarieren, dass Sie eine andere Anzahl von Dimensionen als die Array Literale hat.

Ebenso wie bei eindimensionalen Arrays können Sie den Typrückschluss beim Erstellen eines mehrdimensionalen Arrays mit den literalen des masted-Arrays unterstützen. Der abherleitet Typ ist der bestimmende Typ für alle Werte in allen Arrayliteralen für alle Schachtelungs Ebenen. Im folgenden Beispiel wird ein zweidimensionales Array vom Typ `Double[,]` aus Werten erstellt, die vom Typ `Integer` und sind `Double` .

[!code-vb[nested-type-inference](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#6)]

Weitere Beispiele finden Sie unter [How to: Initialize an Array Variable in Visual Basic](how-to-initialize-an-array-variable.md) (Gewusst wie: Initialisieren einer Arrayvariablen in Visual Basic).

## <a name="iterating-through-an-array"></a>Durchlaufen eines Arrays

Wenn Sie ein Array durchlaufen, greifen Sie auf jedes Element im Array vom niedrigsten Index bis zum höchsten oder vom höchsten zum niedrigsten zu. Verwenden Sie in der Regel entweder den [for... Next-Anweisung](../../../language-reference/statements/for-next-statement.md) oder die [for each-Anweisung... Nächste Anweisung](../../../language-reference/statements/for-each-next-statement.md) zum Durchlaufen der Elemente eines Arrays. Wenn Sie die oberen Begrenzungen des Arrays nicht kennen, können Sie die- <xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType> Methode zum Abrufen des höchsten Index Werts abrufen. Obwohl der niedrigste Indexwert fast immer 0 ist, können Sie die- <xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType> Methode zum Abrufen des niedrigsten Index Werts abrufen.

Im folgenden Beispiel wird ein eindimensionales Array mithilfe der-Anweisung durchlaufen [`For...Next`](../../../language-reference/statements/for-next-statement.md) .

[!code-vb[iterate-one-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate1d.vb)]

Im folgenden Beispiel wird ein mehrdimensionales Array mit einer-Anweisung durchlaufen [`For...Next`](../../../language-reference/statements/for-next-statement.md) . Die <xref:System.Array.GetUpperBound%2A> -Methode enthält einen Parameter, der die Dimension angibt. `GetUpperBound(0)`Gibt den höchsten Index der ersten Dimension zurück und `GetUpperBound(1)` gibt den höchsten Index der zweiten Dimension zurück.

[!code-vb[iterate-two-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate2d.vb)]

Im folgenden Beispiel wird ein [for each verwendet... Nächste Anweisung](../../../language-reference/statements/for-each-next-statement.md)zum Durchlaufen eines eindimensionalen Arrays und eines zweidimensionalen Arrays.

[!code-vb[iterate-for-each-next](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate-for-each-next.vb)]

## <a name="array-size"></a>Array Größe

Die Größe eines Arrays ist das Produkt der Längen aller seiner Dimensionen. Sie stellt die Gesamtzahl der Elemente dar, die derzeit im Array enthalten sind.  Im folgenden Beispiel wird z. b. ein zweidimensionales Array mit vier Elementen in jeder Dimension deklariert. Wie die Ausgabe des Beispiels zeigt, ist die Größe des Arrays 16 (oder (3 + 1) * (3 + 1).

[!code-vb[array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size.vb)]

> [!NOTE]
> Diese Erörterung der Array Größe gilt nicht für verzweigte Arrays. Informationen zu verzweigten Arrays und zum Ermitteln der Größe einer Jagged Array finden Sie im Abschnitt verzweigte [Arrays](#jagged-arrays) .

Sie können die Größe eines Arrays mithilfe der <xref:System.Array.Length%2A?displayProperty=nameWithType>-Eigenschaft bestimmen. Sie können die Länge der einzelnen Dimensionen eines mehrdimensionalen Arrays mithilfe der- <xref:System.Array.GetLength%2A?displayProperty=nameWithType> Methode ermitteln.

Sie können die Größe einer Array Variablen ändern, indem Sie Ihr ein neues Array Objekt zuweisen oder indem Sie die [ `ReDim` Anweisung](../../../language-reference/statements/redim-statement.md) Statement verwenden. Im folgenden Beispiel wird die `ReDim` -Anweisung verwendet, um ein 100-Element-Array in ein 51-Element-Array zu ändern.

[!code-vb[resize-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size2.vb)]

Mehrere Faktoren wirken sich auf die Arraygröße aus.

|||
|---|---|
|Dimensionslänge|Der Index jeder Dimension ist 0-basiert, d. h., er reicht von 0 bis zur oberen Grenze. Daher ist die Länge einer bestimmten Dimension eine größer als die deklarierte obere Grenze dieser Dimension.|
|Längenbeschränkungen|Die Länge jeder Dimension eines Arrays ist auf den maximalen Wert des `Integer` Datentyps beschränkt, d. h <xref:System.Int32.MaxValue?displayProperty=nameWithType> . oder (2 ^ 31)-1. Die Gesamtgröße eines Arrays richtet sich nach dem verfügbaren Arbeitsspeicher des Systems und ist damit ebenfalls beschränkt. Wenn Sie versuchen, ein Array zu initialisieren, das die Menge des verfügbaren Arbeitsspeichers überschreitet, löst die Laufzeit eine aus <xref:System.OutOfMemoryException> .|
|Größe und Elementgröße|Die Größe eines Arrays ist vom Datentyp seiner Elemente unabhängig. Die Größe stellt immer die Gesamtzahl der Elemente dar, nicht die Anzahl der Bytes, die Sie im Arbeitsspeicher verbrauchen.|
|Speicherverbrauch|Es gibt keine verbindlichen Angaben darüber, wie ein Array gespeichert wird. Der Speicherverbrauch variiert auf Plattformen mit unterschiedlichen Datenbreiten, d. h. ein und dasselbe Array kann auf einem 64-Bit-System mehr Speicherplatz benötigen als auf einem 32-Bit-System. Abhängig von der Systemkonfiguration beim Initialisieren eines Arrays kann die Common Language Runtime (CLR) Speicher so zuweisen, dass die Elemente auf sehr engem Raum gespeichert werden oder nur die natürlichen Hardwarebeschränkungen gelten. Ein Array benötigt außerdem zusätzlichen Speicher für seine Steuerungsinformationen. Der Bedarf an zusätzlichem Speicher nimmt mit jeder hinzugefügten Dimension zu.|

## <a name="the-array-type"></a>Der Arraytyp.

Jedes Array weist einen Datentyp auf, der vom Datentyp seiner Elemente abweicht. Es gibt keinen universellen Datentyp, der sich für alle Arrays eignet. Stattdessen wird der Datentyp eines Arrays durch die Anzahl der Dimensionen (den *Rang*) des Arrays bestimmt, sowie durch den Datentyp der Elemente im Array. Zwei Array Variablen weisen denselben Datentyp auf, wenn Sie denselben Rang aufweisen und deren Elemente denselben Datentyp aufweisen. Die Längen der Dimensionen eines Arrays beeinflussen den Array Datentyp nicht.

Jedes Array erbt aus der <xref:System.Array?displayProperty=nameWithType>-Klasse. Sie können eine Variable des Typs `Array` deklarieren, ein Array des Typs `Array` können Sie jedoch nicht erstellen. Der folgende Code deklariert z. b., dass die `arr` Variable vom Typ ist, `Array` und ruft die <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> -Methode auf, um das Array zu instanziieren. der Typ des Arrays erweist sich als Object [].

[!code-vb[array-class](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-class.vb)]

Die [ReDim-Anweisung](../../../language-reference/statements/redim-statement.md) kann nicht für eine Variable verwendet werden, die mit dem Typ `Array` deklariert ist. Aus diesen Gründen und aus Gründen der Typsicherheit empfiehlt es sich, jedes Array als bestimmten Typ zu deklarieren.

Sie können den Datentyp eines Arrays oder seiner Elemente auf verschiedene Arten ermitteln.

- Sie können die- <xref:System.Object.GetType%2A> Methode für die Variable zum Abrufen eines- <xref:System.Type> Objekts, das den Lauf Zeittyp der Variablen darstellt, abrufen. Das <xref:System.Type> -Objekt stellt in seinen Eigenschaften und Methoden umfassende Informationen bereit.
- Sie können die-Variable an die- <xref:Microsoft.VisualBasic.Information.TypeName%2A> Funktion übergeben, um eine `String` mit dem Namen des Lauf Zeit Typs zu erhalten.

Im folgenden Beispiel wird die `GetType` -Methode und die- `TypeName` Funktion aufgerufen, um den Typ eines Arrays zu bestimmen. Der Arraytyp ist `Byte(,)` . Beachten Sie, dass die- <xref:System.Type.BaseType%2A?displayProperty=nameWithType> Eigenschaft auch angibt, dass der Basistyp des Bytearrays die- <xref:System.Array> Klasse ist.

[!code-vb[array-type](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-type.vb)]

## <a name="arrays-as-return-values-and-parameters"></a>Arrays als Rückgabewerte und Parameter

Damit eine `Function`-Prozedur ein Array zurückgibt, geben Sie den Arraydatentyp und die Anzahl der Dimensionen als Rückgabetyp für die [Function-Anweisung](../../../language-reference/statements/function-statement.md) an. Deklarieren Sie in der Funktion eine lokale Arrayvariable mit dem gleichen Datentyp und der gleichen Anzahl an Dimensionen. Schließen Sie die lokale Arrayvariable ohne Klammern in die [Return-Anweisung](../../../language-reference/statements/return-statement.md) ein.

Um ein Array als Parameter für eine `Sub` - oder `Function` -Prozedur anzugeben, definieren Sie den Parameter als Array mit einem bestimmten Datentyp und einer bestimmten Anzahl von Dimensionen. Übergeben Sie im aufzurufenden Vorgang eine Array Variable mit dem gleichen Datentyp und der gleichen Anzahl von Dimensionen.

Im folgenden Beispiel gibt die- `GetNumbers` Funktion eine `Integer()` , ein eindimensionales Array vom Typ, zurück `Integer` . Die Prozedur `ShowNumbers` akzeptiert ein Argument `Integer()` .

[!code-vb[return-value-and-params](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params.vb)]

Im folgenden Beispiel gibt die- `GetNumbersMultiDim` Funktion einen-Wert zurück `Integer(,)` , ein zweidimensionales Array vom Typ `Integer` .  Die Prozedur `ShowNumbersMultiDim` akzeptiert ein Argument `Integer(,)` .

[!code-vb[multidimensional-return-value](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params-2d.vb)]

## <a name="jagged-arrays"></a>Verzweigte Arrays

In einigen Fällen ist die Datenstruktur in einer Anwendung zweidimensional, jedoch nicht rechteckig. Beispielsweise können Sie ein Array verwenden, um Daten über die Hochtemperatur der einzelnen Tage des Monats zu speichern. Die erste Dimension des Arrays stellt den Monat dar, die zweite Dimension stellt jedoch die Anzahl von Tagen dar, und die Anzahl von Tagen in einem Monat ist nicht einheitlich. Ein *Jagged Array*, das auch als *Array von Arrays*bezeichnet wird, ist für derartige Szenarios konzipiert. Ein Jagged Array ist ein Array, dessen Elemente ebenfalls Arrays sind. Ein verzweigtes Array und jedes Element in einem verzweigten Array können über eine oder mehrere Dimensionen verfügen.

Im folgenden Beispiel wird ein Array von Monaten verwendet, wobei jedes Element ein Array von Tagen ist. Im Beispiel wird eine Jagged Array verwendet, da für verschiedene Monate eine unterschiedliche Anzahl von Tagen verwendet wird.  Das Beispiel zeigt, wie Sie eine Jagged Array erstellen, Werte zuweisen und ihre Werte abrufen und anzeigen können.

[!code-vb[jagged-arrays](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged.vb)]

Im vorherigen Beispiel werden der Jagged Array auf Element Weise Werte mithilfe einer- `For...Next` Schleife zugewiesen. Sie können auch den Elementen einer Jagged Array Werte zuweisen, indem Sie die in einem Array verwendeten Literale verwenden. Der Versuch der Verwendung von in einem Netz verwendeten Arrayliteralen (z `Dim valuesjagged = {{1, 2}, {2, 3, 4}}` . b.) generiert jedoch den Compilerfehler [BC30568](../../../misc/bc30568.md). Um den Fehler zu beheben, schließen Sie die inneren Array Literale in Klammern ein. Die Klammern erzwingen das Auswerten des Arrayliteralen Ausdrucks, und die resultierenden Werte werden mit dem äußeren Arrayliteralen verwendet, wie im folgenden Beispiel gezeigt.

[!code-vb[jagged-array-initialization](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-assign.vb)]

Ein Jagged Array ist ein eindimensionales Array, dessen Elemente Arrays enthalten. Daher geben die <xref:System.Array.Length%2A?displayProperty=nameWithType> -Eigenschaft und die- `Array.GetLength(0)` Methode die Anzahl der Elemente im eindimensionalen Array zurück und lösen `Array.GetLength(1)` eine <xref:System.IndexOutOfRangeException> aus, da eine Jagged Array nicht mehrdimensional ist. Sie bestimmen die Anzahl der Elemente in jedem Unterarray, indem Sie den Wert der einzelnen Teilarray- <xref:System.Array.Length%2A?displayProperty=nameWithType> Eigenschaft abrufen. Im folgenden Beispiel wird veranschaulicht, wie die Anzahl der Elemente in einer Jagged Array bestimmt wird.

[!code-vb[jagged-array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-length.vb)]

## <a name="zero-length-arrays"></a>Arrays der Länge 0 (null)

Visual Basic unterscheidet zwischen einem nicht initialisierten Array (einem Array, dessen Wert ist `Nothing` ) und einem *Array der Länge 0 (null* ) oder einem leeren Array (ein Array ohne Elemente). Ein nicht initialisiertes Array ist ein Array, das nicht dimensioniert wurde oder dem ein Wert zugewiesen wurde. Beispiel:

```vb
Dim arr() As String
```

Ein Array der Länge 0 (null) wird mit der Dimension-1 deklariert. Beispiel:

```vb
Dim arrZ(-1) As String
```

Unter den folgenden Bedingungen müssen Sie eventuell ein Array der Länge 0 (null) erstellen:

- Ohne eine- <xref:System.NullReferenceException> Ausnahme zu riskieren, muss der Code auf Member der- <xref:System.Array> Klasse zugreifen, z <xref:System.Array.Length%2A> . b <xref:System.Array.Rank%2A> . oder, oder eine Visual Basic Funktion aufrufen, z <xref:Microsoft.VisualBasic.Information.UBound%2A> . b..

- Sie sollten Ihren Code einfach halten, indem Sie nicht nach `Nothing` einem Sonderfall suchen müssen.

- Der Code interagiert mit einer API (Application Programming Interface), die entweder verlangt, dass mindestens einer Prozedur ein Array der Länge Null übergeben wird. Oder er interagiert mit einer API, die ein solches Array von mindestens einer Prozedur zurückgibt.

## <a name="splitting-an-array"></a>Aufteilen eines Arrays

In einigen Fällen müssen Sie möglicherweise ein einzelnes Array in mehrere Arrays aufteilen. Dies umfasst die Identifizierung der Punkte oder Punkte, an denen das Array aufgeteilt werden soll, und das anschließende auslassen des Arrays in zwei oder mehr separate Arrays.

> [!NOTE]
> In diesem Abschnitt wird das Aufteilen einer einzelnen Zeichenfolge in ein Zeichen folgen Array auf der Grundlage eines Trenn Zeichens nicht erläutert. Informationen zum Aufteilen einer Zeichenfolge finden Sie unter der- <xref:System.String.Split%2A?displayProperty=nameWithType> Methode.

Die gängigsten Kriterien für das Aufteilen eines Arrays lauten:

- Die Anzahl der Elemente im Array. Beispielsweise können Sie ein Array mit mehr als einer angegebenen Anzahl von Elementen in eine Anzahl von ungefähr gleichen Teilen aufteilen. Zu diesem Zweck können Sie den Wert verwenden, der von der-Methode oder der-Methode zurückgegeben wird <xref:System.Array.Length%2A?displayProperty=nameWithType> <xref:System.Array.GetLength%2A?displayProperty=nameWithType> .

- Der Wert eines Elements, das als Trennzeichen dient, das angibt, wo das Array aufgeteilt werden soll. Sie können nach einem bestimmten Wert suchen, indem Sie die <xref:System.Array.FindIndex%2A?displayProperty=nameWithType> -Methode und die- <xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType> Methode aufrufen.

Nachdem Sie den Index oder die Indizes festgelegt haben, an dem das Array aufgeteilt werden soll, können Sie die einzelnen Arrays erstellen, indem Sie die- <xref:System.Array.Copy%2A?displayProperty=nameWithType> Methode aufrufen.

Im folgenden Beispiel wird ein Array in zwei Arrays von ungefähr gleicher Größe aufgeteilt. (Wenn die Gesamtzahl der Array Elemente ungerade ist, verfügt das erste Array über ein Element, das größer als das zweite ist.)

[!code-vb[splitting-an-array-by-length](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split1.vb)]

Im folgenden Beispiel wird ein Zeichen folgen Array basierend auf dem vorhanden sein eines Elements, dessen Wert "zzz" ist, in zwei Arrays aufgeteilt, das als Array Trennzeichen fungiert. Die neuen Arrays enthalten kein-Element, das das Trennzeichen enthält.

[!code-vb[splitting-an-array-by-delimiter](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split2.vb)]

## <a name="joining-arrays"></a>Beitreten zu Arrays

Sie können auch eine Reihe von Arrays in einem einzelnen größeren Array kombinieren. Zu diesem Zweck verwenden Sie auch die- <xref:System.Array.Copy%2A?displayProperty=nameWithType> Methode.

> [!NOTE]
> In diesem Abschnitt wird nicht erläutert, wie ein Zeichen folgen Array einer einzelnen Zeichenfolge hinzufügen wird. Weitere Informationen zum beitreten zu einem Zeichen folgen Array finden Sie unter der- <xref:System.String.Join%2A?displayProperty=nameWithType> Methode.

Vor dem Kopieren der Elemente jedes Arrays in das neue Array müssen Sie zunächst sicherstellen, dass Sie das Array initialisiert haben, damit es groß genug ist, um das neue Array aufnehmen zu können. Dazu haben Sie zwei Möglichkeiten:

- Verwenden Sie die- [`ReDim Preserve`](../../../language-reference/statements/redim-statement.md) Anweisung, um das Array dynamisch zu erweitern, bevor Sie neue Elemente hinzufügen. Dies ist die einfachste Methode, kann jedoch zu Leistungseinbußen und übermäßig hohem Speicherverbrauch führen, wenn Sie große Arrays kopieren.
- Berechnen Sie die Gesamtanzahl der Elemente, die für das neue große Array benötigt werden, und fügen Sie dann die Elemente der einzelnen Quell Arrays hinzu.

Im folgenden Beispiel wird der zweite Ansatz verwendet, um vier Arrays mit jeweils zehn Elementen zu einem einzelnen Array hinzuzufügen.

[!code-vb[joining-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join.vb)]

Da in diesem Fall die Quell Arrays klein sind, können wir das Array auch dynamisch erweitern, während wir die Elemente jedes neuen Arrays hinzufügen. In folgendem Beispiel wird dies getan.

[!code-vb[joining-an-array-dynamically](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join2.vb)]

## <a name="collections-as-an-alternative-to-arrays"></a>Sammlungen als Alternative zu Arrays

Arrays eignen sich bestens zum Erstellen und Arbeiten mit einer festen Anzahl von Objekten mit starkem Typ. Auflistungen ermöglichen ein flexibleres Arbeiten mit Objektgruppen. Anders als bei Arrays, bei denen es erforderlich ist, dass Sie die Größe eines Arrays mit der- [ `ReDim` Anweisung](../../../language-reference/statements/redim-statement.md)explizit ändern, werden Auflistungen dynamisch vergrößert und verkleinert, wenn sich die Anforderungen einer Anwendung ändern.

Wenn Sie verwenden, `ReDim` um ein Array neu zu formatieren, erstellt Visual Basic ein neues Array und gibt das vorherige frei. Dies nimmt Ausführungszeit in Anspruch. Wenn sich die Anzahl der Elemente, mit denen Sie arbeiten, häufig ändert oder Sie die maximale Anzahl von Elementen, die Sie benötigen, nicht vorhersagen können, erzielen Sie in der Regel eine bessere Leistung, indem Sie eine Sammlung verwenden.

Bei einigen Auflistungen können Sie jedem Objekt, das Sie in die Auflistung einfügen, einen Schlüssel zuweisen, sodass das Objekt anhand des Schlüssels schnell abgerufen werden kann.

Wenn die Auflistung Elemente eines Datentyps enthält, können Sie eine der Klassen im <xref:System.Collections.Generic?displayProperty=nameWithType>-Namespace verwenden. Eine generische Auflistung erzwingt Typsicherheit, sodass der Auflistung kein anderer Datentyp hinzugefügt werden kann.

Weitere Informationen über Auflistungen finden Sie unter [Auflistungen](../../concepts/collections.md).

## <a name="related-topics"></a>Verwandte Themen

|Begriff|Definition|
|----------|----------------|
|[Array Dimensions in Visual Basic](array-dimensions.md)|Erläutert Rang und Dimensionen in Arrays.|
|[How to: Initialize an Array Variable in Visual Basic](how-to-initialize-an-array-variable.md) (Gewusst wie: Initialisieren einer Arrayvariable in Visual Basic)|Beschreibt das Auffüllen von Arrays mit Anfangswerten.|
|[Gewusst wie: Sortieren eines Arrays in Visual Basic](how-to-sort-an-array.md)|Erläutert, wie die Elemente eines Arrays alphabetisch sortiert werden.|
|[Vorgehensweise: Zuweisen eines Arrays zu einem anderen Array](how-to-assign-one-array-to-another-array.md)|Beschreibt die Regeln und Schritte zum Zuweisen eines Arrays an eine andere Arrayvariable.|
|[Problembehandlung bei Arrays](troubleshooting-arrays.md)|Erörtert einige allgemeine Probleme, die beim Arbeiten mit Arrays auftreten.|

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Array?displayProperty=nameWithType>
- [Dim-Anweisung](../../../language-reference/statements/dim-statement.md)
- [ReDim-Anweisung](../../../language-reference/statements/redim-statement.md)
