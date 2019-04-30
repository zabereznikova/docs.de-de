---
title: Arrays in Visual Basic
ms.date: 12/06/2017
f1_keywords:
- vb.Array
helpviewer_keywords:
- arrays [Visual Basic]
- Visual Basic, arrays
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
ms.openlocfilehash: 6b131d073e10f99feaf770fe5fd3c393551fa5a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907171"
---
# <a name="arrays-in-visual-basic"></a>Arrays in Visual Basic

Ein Array ist ein Satz von Werten, die bezeichnet *Elemente*, die logisch miteinander verknüpft sind. Ein Array kann z. B. die Anzahl der Schüler/Studenten in jeder Jahrgangsstufe einer Grundschule bestehen; jedes Element des Arrays ist die Anzahl der Schüler/Studenten in eine einzelne Grade-Eigenschaft. Auf ähnliche Weise kann ein Array aus einem Noten für eine Klasse bestehen; jedes Element des Arrays ist eine einzelne Grade-Eigenschaft.

Es ist möglich, einzelne Variablen zum Speichern aller Datenelemente. Z. B. wenn die Anwendung den Noten von Studierenden analysiert, wir können eine separate Variable des einzelnen Studenten-Klasse, wie z. B. `englishGrade1`, `englishGrade2`usw. Dieser Ansatz hat drei wesentliche Einschränkungen:

- Wir haben zur Entwurfszeit wissen, genau wie viele Noten wir behandeln müssen.
- Umgang mit großen Anzahl von Noten schnell wird unhandlich. Dadurch wird wiederum eine Anwendung, die eher auf schwerwiegende Fehler enthalten.
- Es ist schwierig zu verwalten. Jede neue auf Unternehmensniveau, die wir hinzufügen erfordert, dass die Anwendung geändert, erneut kompiliert und bereitgestellt werden.

Unter Verwendung eines Arrays, Sie können auf diese verknüpften Werte verweisen, mit dem gleichen Namen und eine Zahl, die aufgerufen wird, eine *Index* oder *Feldindex* um ein einzelnes Element basierend auf seiner Position im Array zu identifizieren. Die Indizes der Arrayelemente reichen von 0 bis eins weniger als die Gesamtzahl der Elemente im Array. Wenn Sie Visual Basic-Syntax verwenden, um die Größe eines Arrays zu definieren, geben Sie die höchsten Index, nicht die gesamte Anzahl der Elemente im Array. Sie können mit dem Array als eine Einheit arbeiten, und die Möglichkeit, die Elemente durchlaufen werden nicht mehr genau wie viele Elemente wissen muss es zur Entwurfszeit enthält.

Hier einige Beispiele, bevor wir mit den Erklärungen starten:

```vb
' Declare a single-dimension array of 5 numbers.
Dim numbers(4) As Integer

'Declare a single-dimension array and set its 4 values.
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

## <a name="array-elements-in-a-simple-array"></a>Arrayelemente in einem einfachen array

Erstellen wir ein Array mit dem Namen `students` um die Anzahl der Schüler in jeder Jahrgangsstufe einer Grundschule zu speichern. Die Indizes der Elemente reichen von 0 bis 6. Mit diesem Array ist einfacher als die sieben verschiedene Variablen zu deklarieren.

Die folgende Abbildung zeigt die `students` Array. Für jedes Element des Arrays gilt:

- Der Index des Elements steht für die Jahrgangsstufe (Index 0 (null) steht für die erste Jahrgangsstufe).

- Der im Element enthaltene Wert steht für die Anzahl der Schüler in dieser Jahrgangsstufe.

![Das Diagramm zeigt ein Array von der Anzahl von Schülern](./media/index/students-array-elements.gif)

Das folgende Beispiel enthält die Visual Basic-Code, der erstellt und verwendet das Array:

[!code-vb[simple-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/simple-array.vb)]

Im Beispiel führt drei Aufgaben aus:

- Deklariert eine `students` Array mit sieben Elementen. Die Anzahl `6` im Array Deklaration gibt den letzten Index im Array an; es ist eine weniger als die Anzahl der Elemente im Array.
- Es weist Werte auf jedes Element im Array. Elemente des Arrays wird mit dem Arraynamen und den Index des einzelnen Elements in Klammern einschließlich zugegriffen.
- Jeder Wert des Arrays aufgeführt. Im Beispiel wird eine [ `For` ](../../../language-reference/statements/for-next-statement.md) Anweisung, um jedes Element des Arrays anhand seiner Fehlernummer Index zugreifen.

Die `students` Array im vorhergehenden Beispiel ist ein eindimensionales Array aus, da es sich um einen Index verwendet. Ein Array, das mehr als einen Index oder Feldindex verwendet heißt *mehrdimensionale*. Weitere Informationen finden Sie im weiteren Verlauf dieses Artikels und [Arraydimensionen in Visual Basic](../../language-features/arrays/array-dimensions.md).

## <a name="creating-an-array"></a>Erstellen eines Arrays

Sie können die Größe eines Arrays auf verschiedene Arten definieren:

- Sie können die Größe angeben, wenn das Array deklariert wird:

  [!code-vb[creating1](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#1)]

- Sie können eine `New` -Klausel, um die Größe eines Arrays angeben, wenn es erstellt wird:

  [!code-vb[creating2](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#2)]

Wenn Sie ein vorhandenes Array verfügen, können Sie seine Größe umdefinieren, mit der [ `ReDim` ](../../../language-reference/statements/redim-statement.md) Anweisung. Sie können angeben, die `ReDim` Anweisung behalten Sie die Werte, die im Array sind, oder Sie können angeben, dass es sich um ein leeres Array erstellt. Im folgenden Beispiel werden andere Möglichkeiten veranschaulicht, um mit der `ReDim` -Anweisung die Größe eines vorhandenen Arrays zu ändern.

[!code-vb[redimensioning](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#3)]

Weitere Informationen finden Sie unter den [ReDim-Anweisung](../../../language-reference/statements/redim-statement.md).

## <a name="storing-values-in-an-array"></a>Speichern von Werten in einem array

Sie können mit einem Index vom Typ `Integer`auf die einzelnen Positionen in einem Array zugreifen. Die Werte in einem Array können gespeichert und abgerufen werden, indem mit dem entsprechenden in Klammern eingeschlossenen Index auf die einzelnen Arraypositionen verwiesen wird. Indizes für mehrdimensionale Arrays werden durch Kommas (,) getrennt. Sie benötigen einen Index für jede Arraydimension.

Das folgende Beispiel zeigt einige Anweisungen, die Werte in Arrays gespeichert und abgerufen.

[!code-vb[store-and-retrieve](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/store-and-retrieve.vb)]

## <a name="populating-an-array-with-array-literals"></a>Auffüllen eines Arrays mit Array-Literale

Mit einem Arrayliteral können können Sie zur gleichen Zeit ein Array mit einem anfänglichen Satz von Werten auffüllen, die Sie erstellen. Ein Arrayliteral besteht aus einer Liste von durch Trennzeichen getrennten Werten, die in geschweifte Klammern (`{}`) eingeschlossen sind.

Beim Erstellen eines Arrays mit einem Arrayliteral können Sie den Arraytyp entweder angeben oder mittels Typrückschluss bestimmen. Im folgende Beispiel werden beide Optionen veranschaulicht.

[!code-vb[create-with-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#4)]

Wenn Sie den Typrückschluss verwenden, wird der Typ des Arrays von bestimmt die *bestimmende Typ* in der Liste von literalen Werten. Der bestimmende Typ ist der Typ, den alle anderen Typen im Array erweitert werden können. Wenn dieser eindeutige Typ nicht bestimmt werden kann, ist der bestimmende Typ der eindeutige Typ, auf den alle anderen Typen im Array eingegrenzt werden können. Wenn keiner dieser eindeutigen Typen bestimmt werden kann, ist der bestimmende Typ `Object`. Wenn die für das Arrayliteral angegebene Liste der Werte z. B. Werte vom Typ `Integer`, `Long`und `Double`enthält, weist das erhaltene Array den Typ `Double`auf. Da `Integer` und `Long` nur zu verbreitern `Double`, `Double` ist der bestimmende Typ. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../language-features/data-types/widening-and-narrowing-conversions.md).

> [!NOTE]
> Sie können den Typrückschluss nur für Arrays verwenden, die als lokale Variablen in einem Typmember definiert sind. Wenn eine explizite Typdefinition nicht vorhanden ist, sind mit Array-Literale auf Klassenebene definierte Arrays vom Typ `Object[]`. Weitere Informationen finden Sie unter [lokaler Typrückschluss](../variables/local-type-inference.md).

Beachten Sie, die im vorherige Beispiel definiert `values` als ein Array vom Typ `Double` , obwohl die Array-Literale des Typs sind `Integer`. Sie können dieses Array erstellen, da die Werte im Arrayliteral erweitert werden können `Double` Werte.

Sie können auch erstellen und Auffüllen ein mehrdimensionales Arrays mithilfe von *geschachtelten Arrayliterale*. Geschachtelte Arrayliterale müssen eine Anzahl von Dimensionen, die mit dem erhaltenen Array konsistent ist. Das folgende Beispiel erstellt ein zweidimensionales Array von ganzen Zahlen mit geschachtelten Arrayliteralen.

[!code-vb[nested-array-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#5)]

Mit geschachtelten Arrayliteralen erstellen und füllen Sie ein Array, tritt ein Fehler auf, wenn die Anzahl der Elemente in den geschachtelten Arrayliteralen nicht übereinstimmen. Ein Fehler tritt auch auf, wenn Sie die Array-Variable, damit eine andere Anzahl von Dimensionen als die Arrayliterale explizit deklarieren.

Ebenso wie für eindimensionale Arrays, können Sie auf den Typrückschluss verlassen, wenn Sie ein mehrdimensionales Array mit geschachtelten Arrayliteralen erstellen. Der abgeleitete Typ ist der bestimmende Typ für alle Werte in allen Arrayliteralen für alle Schachtelungsebene an. Das folgende Beispiel erstellt ein zweidimensionales Array vom Typ `Double[,]` von Werten, die vom Typ `Integer` und `Double`.

[!code-vb[nested-type-inference](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#6)]

Weitere Beispiele finden Sie unter [Vorgehensweise: Initialisieren einer Arrayvariablen in Visual Basic](../../language-features/arrays/how-to-initialize-an-array-variable.md).

## <a name="iterating-through-an-array"></a>Durchlaufen eines Arrays

Wenn Sie ein Array durchlaufen, können Sie jedes Element im Array zugreifen, aus dem niedrigsten Index bis zur höchsten oder von der höchsten zur niedrigsten Instanz. In der Regel verwenden Sie entweder die [für... Nächste Anweisung](../../../language-reference/statements/for-next-statement.md) oder [für jede... Nächste Anweisung](../../../language-reference/statements/for-each-next-statement.md) zum Durchlaufen der Elemente eines Arrays. Wenn Sie nicht, dass die obere Grenze des Arrays wissen, können Sie rufen die <xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType> -Methode zum Abrufen des Indexes des höchsten Wert. Obwohl der niedrigste Indexwert ist immer 0 ist, rufen Sie die <xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType> -Methode zum Abrufen von des niedrigsten Wert des Indexes.

Im folgenden Beispiel wird durch ein eindimensionales Array mithilfe der [ `For...Next` ](../../../language-reference/statements/for-next-statement.md) Anweisung.

[!code-vb[iterate-one-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate1d.vb)]

Das folgende Beispiel durchläuft ein mehrdimensionales Array unter Verwendung einer [ `For...Next` ](../../../language-reference/statements/for-next-statement.md) Anweisung. Die <xref:System.Array.GetUpperBound%2A> -Methode enthält einen Parameter, der die Dimension angibt. `GetUpperBound(0)` Gibt den höchsten Index der ersten Dimension, und `GetUpperBound(1)` gibt den höchsten Index der zweiten Dimension zurück.

[!code-vb[iterate-two-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate2d.vb)]

Im folgenden Beispiel wird eine [für jede... Nächste Anweisung](../../../language-reference/statements/for-each-next-statement.md)eines eindimensionalen Arrays und ein zweidimensionales Array durchlaufen.

[!code-vb[iterate-for-each-next](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate-for-each-next.vb)]

## <a name="array-size"></a>Array-Größe

Die Größe eines Arrays ist das Produkt der Längen aller seiner Dimensionen. Sie stellt die Gesamtzahl der Elemente dar, die derzeit im Array enthalten sind.  Das folgende Beispiel deklariert beispielsweise ein 2-dimensionales Array mit vier Elementen in jeder Dimension. Wie die Ausgabe des Beispiels zeigt, ist die Arraygröße 16 (oder (3 + 1) * (3 + 1).

[!code-vb[array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size.vb)]

> [!NOTE]
> Diese Diskussion der Größe des Arrays gilt nicht für verzweigte Arrays. Weitere Informationen zu verzweigte Arrays und das Festlegen der Größe eines verzweigten Arrays, finden Sie unter den [verzweigte Arrays](#jagged-arrays) Abschnitt.

Sie können die Größe eines Arrays mithilfe der <xref:System.Array.Length%2A?displayProperty=nameWithType>-Eigenschaft bestimmen. Sie finden die Länge der einzelnen Dimensionen eines mehrdimensionalen Arrays mithilfe der <xref:System.Array.GetLength%2A?displayProperty=nameWithType> Methode.

Sie können eine Arrayvariablen ändern, durch ein neues Arrayobjekt zuweisen oder mithilfe der [ `ReDim` Anweisung](../../../language-reference/statements/redim-statement.md) Anweisung. Im folgenden Beispiel wird die `ReDim` Anweisung, um ein Array mit 100 Elementen in ein Array mit Elementen 51 zu ändern.

[!code-vb[resize-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size2.vb)]

Mehrere Faktoren wirken sich auf die Arraygröße aus.

|||
|---|---|
|Dimensionslänge|Der Index der einzelnen Dimensionen ist 0-basiert, dies bedeutet, dass es zwischen 0 und zur Obergrenze liegt. Daher ist die Länge einer bestimmten Dimension eins größer ist als die deklarierte Obergrenze dieser Dimension.|
|Längenbeschränkungen|Die Länge jeder Dimension eines Arrays ist der maximale Wert, der auf die `Integer` -Datentyp, der ist <xref:System.Int32.MaxValue?displayProperty=nameWithType> oder (2 ^ 31) – 1. Die Gesamtgröße eines Arrays richtet sich nach dem verfügbaren Arbeitsspeicher des Systems und ist damit ebenfalls beschränkt. Wenn Sie versuchen, ein Array zu initialisieren, die die Menge des verfügbaren Arbeitsspeichers überschreitet, löst die Laufzeit eine <xref:System.OutOfMemoryException>.|
|Größe und Elementgröße|Die Größe eines Arrays ist vom Datentyp seiner Elemente unabhängig. Die Größe stellt immer die Gesamtzahl der Elemente, nicht die Anzahl der Bytes, die im Arbeitsspeicher belegen.|
|Speicherverbrauch|Es gibt keine verbindlichen Angaben darüber, wie ein Array gespeichert wird. Der Speicherverbrauch variiert auf Plattformen mit unterschiedlichen Datenbreiten, d. h. ein und dasselbe Array kann auf einem 64-Bit-System mehr Speicherplatz benötigen als auf einem 32-Bit-System. Abhängig von der Systemkonfiguration beim Initialisieren eines Arrays kann die Common Language Runtime (CLR) Speicher so zuweisen, dass die Elemente auf sehr engem Raum gespeichert werden oder nur die natürlichen Hardwarebeschränkungen gelten. Ein Array benötigt außerdem zusätzlichen Speicher für seine Steuerungsinformationen. Der Bedarf an zusätzlichem Speicher nimmt mit jeder hinzugefügten Dimension zu.|

## <a name="the-array-type"></a>Der Arraytyp

Jedes Array besitzt einen Datentyp, die sich von dem Datentyp seiner Elemente unterscheidet. Es gibt keinen universellen Datentyp, der sich für alle Arrays eignet. Stattdessen wird der Datentyp eines Arrays durch die Anzahl der Dimensionen (den *Rang*) des Arrays bestimmt, sowie durch den Datentyp der Elemente im Array. Datentypen zweier Arrayvariablen werden die gleichen Daten, geben Sie nur, wenn sie den gleichen Rang aufweisen und ihre Elemente den gleichen Datentyp. Die Länge der Dimensionen eines Arrays wirken sich nicht auf den Arraydatentyp aus.

Jedes Array erbt aus der <xref:System.Array?displayProperty=nameWithType>-Klasse. Sie können eine Variable des Typs `Array` deklarieren, ein Array des Typs `Array` können Sie jedoch nicht erstellen. Beispielsweise, obwohl der folgende Code deklariert die `arr` Variable vom Typ `Array` und ruft die <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> -Methode instanziieren, das Array, das den Typ des Arrays zu belegen, Object [] sein.

[!code-vb[array-class](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-class.vb)]

Die [ReDim-Anweisung](../../../language-reference/statements/redim-statement.md) kann nicht für eine Variable verwendet werden, die mit dem Typ `Array` deklariert ist. Aus diesen Gründen und typsicherheit ist es ratsam, jedes Array als bestimmten Typ zu deklarieren.

Sie können den Datentyp eines Arrays oder seiner Elemente auf verschiedene Arten ermitteln.

- Rufen Sie die <xref:System.Object.GetType%2A> Methode für die Variable zum Abrufen einer <xref:System.Type> Objekt, das den Laufzeittyp der Variable darstellt. Das <xref:System.Type> -Objekt stellt in seinen Eigenschaften und Methoden umfassende Informationen bereit.
- Sie können die Variable übergeben die <xref:Microsoft.VisualBasic.Information.TypeName%2A> Funktion zum Abrufen einer `String` durch den Namen des Laufzeittyps.

Im folgenden Beispiel wird sowohl die `GetType` Methode und die `TypeName` Funktion, die den Typ eines Arrays zu bestimmen. Der Arraytyp ist `Byte(,)`. Beachten Sie, dass die <xref:System.Type.BaseType%2A?displayProperty=nameWithType> Eigenschaft wird angegeben, dass der Basistyp des Byte-Arrays ist der <xref:System.Array> Klasse.

[!code-vb[array-type](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-type.vb)]

## <a name="arrays-as-return-values-and-parameters"></a>Arrays als Parameter und Rückgabewerte

Damit eine `Function`-Prozedur ein Array zurückgibt, geben Sie den Arraydatentyp und die Anzahl der Dimensionen als Rückgabetyp für die [Function-Anweisung](../../../language-reference/statements/function-statement.md) an. Deklarieren Sie in der Funktion eine lokale Arrayvariable mit dem gleichen Datentyp und der gleichen Anzahl an Dimensionen. Schließen Sie die lokale Arrayvariable ohne Klammern in die [Return-Anweisung](../../../language-reference/statements/return-statement.md) ein.

Um ein Array als Parameter für eine `Sub` - oder `Function` -Prozedur anzugeben, definieren Sie den Parameter als Array mit einem bestimmten Datentyp und einer bestimmten Anzahl von Dimensionen. Übergeben Sie im Aufruf an die Prozedur eine Arrayvariable mit dem gleichen Datentyp und die Anzahl von Dimensionen.

Im folgenden Beispiel die `GetNumbers` -Funktion zurückgegeben wird ein `Integer()`, ein eindimensionales Array vom Typ `Integer`. Die Prozedur `ShowNumbers` akzeptiert ein Argument `Integer()` .

[!code-vb[return-value-and-params](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params.vb)]

Im folgenden Beispiel die `GetNumbersMultiDim` -Funktion zurückgegeben wird ein `Integer(,)`, ein zweidimensionales Array vom Typ `Integer`.  Die Prozedur `ShowNumbersMultiDim` akzeptiert ein Argument `Integer(,)` .

[!code-vb[multidimensional-return-value](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params-2d.vb)]

## <a name="jagged-arrays"></a>Verzweigte Arrays

In einigen Fällen ist die Datenstruktur in einer Anwendung zweidimensional, jedoch nicht rechteckig. Beispielsweise können Sie ein Array zum Speichern von Daten über die Höchsttemperatur, der jeden Tag des Monats aus. Die erste Dimension des Arrays darstellt, den Monat, aber die zweite Dimension darstellt, die Anzahl der Tage, und die Anzahl der Tage im Monat ist nicht einheitlich. Ein *verzweigtes Array*, die auch aufgerufen wird, eine *Arrays von Arrays*, ist für solche Szenarien konzipiert. Ein verzweigtes Array ist ein Array, dessen Elemente auch Arrays sind. Ein verzweigtes Array und jedes Element in einem verzweigten Array können über eine oder mehrere Dimensionen verfügen.

Im folgenden Beispiel wird ein Array von Monaten, von denen jedes Element ein Array von Tagen ist. Im Beispiel wird ein verzweigtes Array verwendet, da verschiedene Monate unterschiedliche Anzahl von Tagen haben.  Das Beispiel zeigt, wie Sie ein verzweigtes Array erstellen, Zuweisen von Werten, und Werte abrufen und Anzeigen der.

[!code-vb[jagged-arrays](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged.vb)]

Im vorherige Beispiel weist die Werte in das verzweigte Array auf Basis von Elementen mit einem `For...Next` Schleife. Sie können auch die Elemente eines verzweigten Arrays Werte zuweisen, mit geschachtelten Arrayliteralen. Der Versuch, verwenden jedoch geschachtelte array-Literale (z. B. `Dim valuesjagged = {{1, 2}, {2, 3, 4}}`) generiert den Compilerfehler [BC30568](../../../,,/../misc/bc30568.md). Schließen Sie die inneren Arrayliterale in Klammern, um den Fehler zu beheben. Die Klammern Erzwingen der Array-literale-Ausdruck ausgewertet werden soll, und die resultierenden Werte werden mit dem äußeren Arrayliteral verwendet, wie im folgende Beispiel gezeigt.

[!code-vb[jagged-array-initialization](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-assign.vb)]

Ein verzweigtes Array ist ein eindimensionales Array, dessen Elemente Arrays enthält. Aus diesem Grund die <xref:System.Array.Length%2A?displayProperty=nameWithType> Eigenschaft und die `Array.GetLength(0)` Methodenrückgabewert die Anzahl von Elementen im eindimensionalen Array und `Array.GetLength(1)` löst eine <xref:System.IndexOutOfRangeException> da ein verzweigtes Array nicht mehrdimensional ist. Sie bestimmen die Anzahl der Elemente in dem jedes Teilarray durch Abrufen des Werts jedes Teilarray des <xref:System.Array.Length%2A?displayProperty=nameWithType> Eigenschaft. Das folgende Beispiel veranschaulicht, wie Sie die Anzahl der Elemente in einem verzweigten Array zu bestimmen.

[!code-vb[jagged-array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-length.vb)]

## <a name="zero-length-arrays"></a>Arrays mit der Länge 0 (null)

Visual Basic unterscheidet zwischen einem nicht initialisierten Array (ein Array, dessen Wert `Nothing`) und ein *Array der Länge 0 (null)* oder ein leeres Array (ein Array, das keine Elemente verfügbar sind.) Ein nicht initialisiertes Array ist eine, die nicht dimensioniert wurden hat oder hatte Werte zugewiesen, es. Zum Beispiel:

```vb
Dim arr() As String
```

Ein Array der Länge 0 (null) wird mit einer Dimension-1 deklariert. Zum Beispiel:

```vb
Dim arrZ(-1) As String
```

Unter den folgenden Bedingungen müssen Sie eventuell ein Array der Länge 0 (null) erstellen:

- Ohne zu riskieren eine <xref:System.NullReferenceException> Ausnahme, der Code muss zugreifen auf Member der <xref:System.Array> Klasse, z. B. <xref:System.Array.Length%2A> oder <xref:System.Array.Rank%2A>, oder rufen Sie eine Visual Basic-Funktion z. B. <xref:Microsoft.VisualBasic.Information.UBound%2A>.

- Sie möchten, Ihren Code einfach zu halten, indem zu prüfen, ohne `Nothing` als Sonderfall.

- Der Code interagiert mit einer API (Application Programming Interface), die entweder verlangt, dass mindestens einer Prozedur ein Array der Länge Null übergeben wird. Oder er interagiert mit einer API, die ein solches Array von mindestens einer Prozedur zurückgibt.

## <a name="splitting-an-array"></a>Ein Array Teilen

In einigen Fällen müssen Sie ein einzelnes Array in mehrere Arrays aufgeteilt. Dies umfasst, identifiziert der Punkt oder ein Punkt, an denen das Array ist, aufgeteilt werden, und klicken Sie dann das Array in mindestens zwei separate Arrays Spucken.

> [!NOTE]
> Aufteilen einer einzelnen Zeichenfolge in ein Zeichenfolgenarray, das anhand eines Trennzeichens erörtert in diesem Abschnitt nicht. Weitere Informationen zum Aufteilen einer Zeichenfolge, finden Sie unter den <xref:System.String.Split%2A?displayProperty=nameWithType> Methode.

Die am häufigsten verwendeten Kriterien für das Aufteilen der ein Array sind:

- Die Anzahl der Elemente im Array. Beispielsweise empfiehlt es sich um ein Array von mehr als eine angegebene Anzahl von Elementen in eine Anzahl von etwa gleich große Teile aufgeteilt. Zu diesem Zweck können Sie den Rückgabewert von entweder die <xref:System.Array.Length%2A?displayProperty=nameWithType> oder <xref:System.Array.GetLength%2A?displayProperty=nameWithType> Methode.

- Der Wert eines Elements, das als Trennzeichen dient, der angibt, in dem das Array aufgeteilt werden soll. Sie können für einen bestimmten Wert suchen, durch den Aufruf der <xref:System.Array.FindIndex%2A?displayProperty=nameWithType> und <xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType> Methoden.

Wenn Sie festgelegt haben, den Index oder die Indizes, die an dem das Array aufgeteilt werden soll, können Sie klicken Sie dann die einzelnen Arrays erstellen, durch Aufrufen der <xref:System.Array.Copy%2A?displayProperty=nameWithType> Methode.

Im folgende Beispiel teilt ein Array, in zwei Arrays von ungefähr gleicher Größe. (Wenn die Gesamtzahl der Elemente des Arrays eine ungerade ist, hat das erste Array ein weiteres Element als das zweite.)

[!code-vb[splitting-an-array-by-length](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split1.vb)]

Im folgenden Beispiel wird ein Array von Zeichenfolgen in zwei Arrays, die basierend auf dem Vorhandensein eines Elements, dessen Wert ist "Zzz", die als Arraytrennzeichen dient. Die neuen Arrays enthalten nicht das Element, das das Trennzeichen enthält.

[!code-vb[splitting-an-array-by-delimiter](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split2.vb)]

## <a name="joining-arrays"></a>Verknüpfen von arrays

Sie können auch eine Reihe von Arrays in einem einzigen größeren Array kombinieren. Zu diesem Zweck verwenden Sie auch die <xref:System.Array.Copy%2A?displayProperty=nameWithType> Methode.

> [!NOTE]
> Verknüpfen ein Array von Zeichenfolgen in einer einzelnen Zeichenfolge erörtert in diesem Abschnitt nicht. Informationen zum Verknüpfen mit einem Array von Zeichenfolgen finden Sie in der <xref:System.String.Join%2A?displayProperty=nameWithType> Methode.

Bevor Sie die Elemente der einzelnen Arrays in das neue Array kopieren, müssen Sie zunächst sicherstellen, dass Sie das Array initialisiert haben, sodass sie groß genug für das neue Array ist. Dazu haben Sie zwei Möglichkeiten:

- Verwenden der [ `ReDim Preserve` ](../../../language-reference/statements/redim-statement.md) Anweisung, um das Array dynamisch zu erweitern, bevor Sie neue Elemente hinzugefügt wird. Dies ist das einfachste Verfahren, aber es kann in eine Verringerung der Leistung und eine zu hohe speicherauslastung führen, wenn Sie beim Kopieren großer Arrays.
- Berechnen Sie die Gesamtanzahl der Elemente, die erforderlich sind, für das neue große Array zu, und fügen Sie die Elemente von jeder Quellarray hinzu.

Im folgenden Beispiel wird den zweiten Ansatz ein einzelnes Array vier Arrays mit zehn Elementen hinzu.

[!code-vb[joining-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join.vb)]

Da in diesem Fall die Source-Arrays alle klein sind, können wir das Array auch dynamisch erweitern, wie wir jedes Arrays neue Elemente hinzufügen. In folgendem Beispiel wird dies getan.

[!code-vb[joining-an-array-dynamically](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join2.vb)]

## <a name="collections-as-an-alternative-to-arrays"></a>Auflistungen als Alternative zu arrays

Arrays eignen sich bestens zum Erstellen und Arbeiten mit einer festen Anzahl von Objekten mit starkem Typ. Auflistungen ermöglichen ein flexibleres Arbeiten mit Objektgruppen. Im Gegensatz zu Arrays, die erfordern, dass Sie explizit die Größe eines Arrays ändern der [ `ReDim` Anweisung](../../../language-reference/statements/redim-statement.md), Sammlungen vergrößern und Verkleinern von dynamisch verändernden Anforderungen einer Anwendung ändern.

Bei Verwendung von `ReDim` um ein Array zu dimensionieren, Visual Basic erstellt ein neues Array und gibt das vorherige Beispiel. Dies nimmt Ausführungszeit in Anspruch. Aus diesem Grund, wenn die Anzahl der Elemente, mit denen, die Sie häufig ändern, oder Sie arbeiten werden, die maximale Anzahl der Elemente nicht vorhersehen kann, Sie müssen, werden Sie in der Regel eine bessere Leistung abrufen mithilfe einer Sammlung.

Bei einigen Auflistungen können Sie jedem Objekt, das Sie in die Auflistung einfügen, einen Schlüssel zuweisen, sodass das Objekt anhand des Schlüssels schnell abgerufen werden kann.

Wenn die Auflistung Elemente eines Datentyps enthält, können Sie eine der Klassen im <xref:System.Collections.Generic?displayProperty=nameWithType> -Namespace verwenden. Eine generische Auflistung erzwingt Typsicherheit, sodass der Auflistung kein anderer Datentyp hinzugefügt werden kann.

Weitere Informationen über Auflistungen finden Sie unter [Auflistungen](../../concepts/collections.md).

## <a name="related-topics"></a>Verwandte Themen

|Begriff|Definition|
|----------|----------------|
|[Array Dimensions in Visual Basic](../../language-features/arrays/array-dimensions.md)|Erläutert Rang und Dimensionen in Arrays.|
|[Vorgehensweise: Initialisieren einer Arrayvariablen in Visual Basic](../../language-features/arrays/how-to-initialize-an-array-variable.md)|Beschreibt das Auffüllen von Arrays mit Anfangswerten.|
|[Vorgehensweise: Sortieren eines Arrays in Visual Basic](../../language-features/arrays/how-to-sort-an-array.md)|Erläutert, wie die Elemente eines Arrays alphabetisch sortiert werden.|
|[Vorgehensweise: Zuweisen eines Arrays zu einem anderen Array](../../language-features/arrays/how-to-assign-one-array-to-another-array.md)|Beschreibt die Regeln und Schritte zum Zuweisen eines Arrays an eine andere Arrayvariable.|
|[Problembehandlung bei Arrays](../../language-features/arrays/troubleshooting-arrays.md)|Erörtert einige allgemeine Probleme, die beim Arbeiten mit Arrays auftreten.|

## <a name="see-also"></a>Siehe auch

- <xref:System.Array?displayProperty=nameWithType>
- [Dim-Anweisung](../../../language-reference/statements/dim-statement.md)
- [ReDim-Anweisung](../../../language-reference/statements/redim-statement.md)
