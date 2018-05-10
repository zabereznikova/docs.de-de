---
title: Arrays in Visual Basic
ms.date: 12/06/2017
f1_keywords:
- vb.Array
helpviewer_keywords:
- arrays [Visual Basic]
- Visual Basic, arrays
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b6c1db0131f2a150dc1b00dd5e6dafc3a418f05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="arrays-in-visual-basic"></a>Arrays in Visual Basic
Ein Array ist ein Satz von Werten, die nennt man auch sind *Elemente*, die logisch miteinander verknüpft sind. Ein Array kann z. B. die Anzahl der Schüler in jeder Jahrgangsstufe einer Grundschule bestehen; jedes Element des Arrays ist die Anzahl der Schüler in einem einzelnen Jahrgangsstufe. Auf ähnliche Weise kann ein Array eine Student Bewertungen für eine Klasse umfassen; jedes Element des Arrays ist einer einzelnen Jahrgangsstufe.    

Es ist möglich, einzelne Variablen zum Speichern aller unserer Datenelemente. Z. B. wenn unsere Anwendung Student Qualitäten analysiert, wir können eine separate Variable für jeden Student Klasse, wie z. B. `englishGrade1`, `englishGrade2`usw. Dieser Ansatz hat drei wichtige Einschränkungen:
- Wir haben zur Entwurfszeit wissen genau wie viele Qualitäten behandeln müssen.
- Es wird unhandlich, große Zahlen Qualitäten schnell verarbeitet. Dadurch wird wiederum eine Anwendung weitaus höheren Wahrscheinlichkeit auf schwerwiegende Fehler enthalten.
- Es ist schwierig zu verwalten. Jede neue Klasse, die wir hinzufügen erfordert, dass die Anwendung geändert, neu kompiliert und erneut bereitgestellt werden.  
 
 Mithilfe eines Arrays können Sie auf diese verknüpften Werte verweisen, indem Sie den gleichen Namen, und verwenden Sie eine Zahl, die aufgerufen wird, eine *Index* oder *Feldindex* um ein einzelnes Element anhand seiner Position im Array zu identifizieren. Die Indizes eines Arrays Bereichs von 0 bis eins weniger als die Gesamtzahl der Elemente im Array. Wenn Sie Visual Basic-Syntax verwenden, um die Größe eines Arrays zu definieren, geben Sie den höchsten Index, nicht die gesamte Anzahl der Elemente im Array. Sie können mit dem Array als eine Einheit arbeiten und die Möglichkeit, dessen Elemente durchlaufen Sie genau wie viele Elemente wissen sie zur Entwurfszeit enthält nicht freigegeben.
  
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
  
 ## <a name="in-this-article"></a>In diesem Artikel
  
- [Arrayelemente in einem einfachen array](#array-elements-in-a-simple-array)  
  
- [Erstellen eines Arrays](#creating-an-array)  
  
- [Speichern von Werten in einem array](#storing-values-in-an-array)  
  
- [Auffüllen eines Arrays mit Arrayliteralen](#populating-an-array-with-array-literals)  
  
- [Durchlaufen eines Arrays](#iterating-through-an-array)  
  
- [Array-Größe](#BKMK_ArraySize)  

- [Der Arraytyp](#the-array-type)  
  
- [Arrays als Parameter und Rückgabewerte](#arrays-as-return-values-and-parameters)  
- [Verzweigte arrays](#jagged-arrays)  
  
- [Arrays mit der Länge 0 (null)](#zero-length-arrays)  

- [Ein Array Teilen](#splitting-an-array)
  
- [Auflistungen als Alternative zu arrays](#collections-as-an-alternative-to-arrays)  
  
##  <a name="array-elements-in-a-simple-array"></a>Arrayelemente in einem einfachen array  

Erstellen wir ein Array mit dem Namen `students` , speichern die Anzahl der Schüler in jeder Jahrgangsstufe einer Grundschule. Die Indizes der Elemente reichen von 0 bis 6. Verwenden dieses Array ist einfacher als sieben verschiedene Variablen zu deklarieren.

Die folgende Abbildung zeigt die `students` Array. Für jedes Element des Arrays gilt:  
  
-   Der Index des Elements steht für die Jahrgangsstufe (Index 0 (null) steht für die erste Jahrgangsstufe).
  
-   Der im Element enthaltene Wert steht für die Anzahl der Schüler in dieser Jahrgangsstufe.
  
 ![Bild des Arrays mit der Anzahl von Studenten](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexampleschool.gif "ArrayExampleSchool")  
Elemente des "students"-Arrays  
 
Das folgende Beispiel enthält den Visual Basic-Code, der erstellt und verwendet das Array:

 [!code-vb[simple-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/simple-array.vb)]  

Das Beispiel führt drei Aufgaben aus:

- Deklariert eine `students` Array mit sieben Elementen. Die Anzahl `6` im Array Deklaration gibt den letzten Index im Array an; es sich um einen kleiner als die Anzahl der Elemente im Array.
- Es weist Werte auf jedes Element im Array. Arrayelemente erfolgt mithilfe von den Arraynamen und den Index des einzelnen Elements in Klammern einschließen.
- Jeder Wert im Array aufgeführt. Im Beispiel wird eine [ `For` ](../../../language-reference/statements/for-next-statement.md) Anweisung, um jedes Element des Arrays zugreifen, indem dessen Index zurück.
  
 Die `students` Array im vorangehenden Beispiel ist ein eindimensionales Array, da es sich um einen Index verwendet. Ein Array, das mehr als einen Index oder Feldindex verwendet heißt *mehrdimensionale*. Weitere Informationen finden Sie im weiteren Verlauf dieses Artikels und [Arraydimensionen in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
##  <a name="creating-an-array"></a>Erstellen eines Arrays  
 
Sie können die Größe eines Arrays auf verschiedene Arten definieren: 

- Sie können die Größe beim Deklarieren des Arrays angeben:
  
    [!code-vb[creating1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#1)]  
  
 - Sie können eine `New` -Klausel, um die Größe eines Arrays angeben, wenn es erstellt wird:  
  
    [!code-vb[creating2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#2)]  
  
 Wenn Sie ein vorhandenes Array haben, definieren Sie seine Größe mithilfe der [ `Redim` ](../../../../visual-basic/language-reference/statements/redim-statement.md) Anweisung. Sie können angeben, die `Redim` Anweisung behalten Sie die Werte, die im Array sind, oder Sie können angeben, dass es sich um ein leeres Array erstellt. Im folgenden Beispiel werden andere Möglichkeiten veranschaulicht, um mit der `Redim` -Anweisung die Größe eines vorhandenen Arrays zu ändern.  
  
 [!code-vb[redimensioning](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#3)]  
  
 Weitere Informationen finden Sie unter der [ReDim-Anweisung](../../../../visual-basic/language-reference/statements/redim-statement.md).  
  
##  <a name="storing-values-in-an-array"></a>Speichern von Werten in einem Array
 
 Sie können mit einem Index vom Typ `Integer` auf die einzelnen Positionen in einem Array zugreifen. Die Werte in einem Array können gespeichert und abgerufen werden, indem mit dem entsprechenden in Klammern eingeschlossenen Index auf die einzelnen Arraypositionen verwiesen wird. Indizes für mehrdimensionale Arrays werden durch Kommas (,) getrennt. Sie benötigen einen Index für jede Arraydimension. 

Das folgende Beispiel zeigt einige Anweisungen, die Werte in Arrays gespeichert und abgerufen.
  
 [!code-vb[store-and-retrieve](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/store-and-retrieve.vb)]  
  
## <a name="populating-an-array-with-array-literals"></a>Auffüllen eines Arrays mit Arrayliteralen
 Mithilfe von einem Arrayliteral können Sie ein Array mit einem anfänglichen Satz von Werten zur gleichen Zeit auffüllen, die Sie erstellen. Ein Arrayliteral besteht aus einer Liste von durch Trennzeichen getrennten Werten, die in geschweifte Klammern (`{}`) eingeschlossen sind.  
  
 Beim Erstellen eines Arrays mit einem Arrayliteral können Sie den Arraytyp entweder angeben oder mittels Typrückschluss bestimmen. Im folgende Beispiel werden beide Optionen veranschaulicht.  
  
 [!code-vb[create-with-literals](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#4)]  
  
 Bei Verwendung von Typrückschluss wird der Typ des Arrays bestimmt, von der *bestimmende Typ* in der Liste von literalen Werten. Der bestimmende Typ ist der Typ, den alle anderen Typen im Array erweitert werden können. Wenn dieser eindeutige Typ nicht bestimmt werden kann, ist der bestimmende Typ der eindeutige Typ, auf den alle anderen Typen im Array eingegrenzt werden können. Wenn keiner dieser eindeutigen Typen bestimmt werden kann, ist der bestimmende Typ `Object`. Wenn die für das Arrayliteral angegebene Liste der Werte z. B. Werte vom Typ `Integer`, `Long`und `Double`enthält, weist das erhaltene Array den Typ `Double`auf. Da `Integer` und `Long` erweitert werden nur für `Double`, `Double` ist der bestimmende Typ. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md). 
 
> [!NOTE] 
> Sie können nur für Arrays mithilfe des Typrückschlusses, die als lokale Variablen in einen Typmember definiert sind. Wenn die Definition einer expliziten Typ nicht vorhanden ist, sind mit Arrayliteralen auf Klassenebene definierte Arrays vom Typ `Object[]`. Weitere Informationen finden Sie unter [lokaler Typrückschluss](../variables/local-type-inference.md). 

Beachten Sie, die im vorherigen Beispiel definiert `values` als ein Array vom Typ `Double` , obwohl alle Arrayliterale des Typs sind `Integer`. Dieses Array kann erstellt werden, da die Werte im Arrayliteral erweitert, um werden können `Double` Werte. 
  
 Sie können auch erstellen und füllen Sie ein mehrdimensionales Array mit *geschachtelten Arrayliterale*. Geschachtelte Arrayliterale müssen es sich um eine Anzahl von Dimensionen haben, die mit dem erhaltenen Array konsistent ist. Im folgende Beispiel wird ein zweidimensionales Array von ganzen Zahlen mit geschachtelten Arrayliteralen erstellt.  
  
 [!code-vb[nested-array-literals](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#5)]  
  
Mit geschachtelten Arrayliteralen erstellen und füllen Sie ein Array, tritt ein Fehler auf, wenn die Anzahl der Elemente in den geschachtelten Arrayliteralen nicht übereinstimmen. Ein Fehler tritt auch auf, wenn Sie eine andere Anzahl von Dimensionen als die Arrayliterale haben die Arrayvariable explizit deklarieren. 
  
Genauso Sie für eindimensionale Arrays können, können Sie beim Erstellen eines mehrdimensionalen Arrays mit geschachtelten Arrayliteralen Typrückschlusses verlassen. Der abgeleitete Typ ist der bestimmende Typ für alle Werte in allen Arrayliteralen für alle Schachtelungsebene. Das folgende Beispiel erstellt ein zweidimensionales Array vom Typ `Double[,]` aus Werte des Typs `Integer` und `Double`.  
  
 [!code-vb[nested-type-inference](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#6)]  
  
 Weitere Beispiele finden Sie unter [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Gewusst wie: Initialisieren einer Arrayvariablen in Visual Basic).  
  
##  <a name="iterating-through-an-array"></a>Durchlaufen eines Arrays  
 Wenn Sie ein Array durchlaufen, können Sie jedes Element im Array zugreifen, vom niedrigsten Index bis zur höchsten Ebene oder von der höchsten zur niedrigsten Instanz. In der Regel verwenden Sie entweder die [für... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-next-statement.md) oder [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) zum Durchlaufen der Elemente eines Arrays. Wenn Sie die obere Grenze des Arrays nicht kennen, können Sie rufen die <xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType> Methode, um den höchsten Wert des Indexes abzurufen. Obwohl fast niedrigste Indexwert ist immer 0 ist, können Sie Aufrufen der <xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType> Methode zum Abrufen des niedrigsten Wert des Indexes.   
  
 Das folgende Beispiel durchläuft ein eindimensionales Array mithilfe der [ `For...Next` ](../../../../visual-basic/language-reference/statements/for-next-statement.md) Anweisung. 
  
 [!code-vb[iterate-one-dimensional-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate1d.vb)]  
  
 Das folgende Beispiel durchläuft ein mehrdimensionales Array unter Verwendung einer [ `For...Next` ](../../../../visual-basic/language-reference/statements/for-next-statement.md) Anweisung. Die <xref:System.Array.GetUpperBound%2A> -Methode enthält einen Parameter, der die Dimension angibt. `GetUpperBound(0)` Gibt den höchsten Index der ersten Dimension zurück und `GetUpperBound(1)` gibt den höchsten Index der zweiten Dimension zurück.
  
 [!code-vb[iterate-two-dimensional-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate2d.vb)]  
  
 Im folgenden Beispiel wird eine [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)eines eindimensionalen Arrays und ein zweidimensionales Array durchlaufen.  
  
 [!code-vb[iterate-for-each-next](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate-for-each-next.vb)]  
  
## <a name="array-size"></a>Arraygröße  

 Die Größe eines Arrays ist das Produkt der Längen aller seiner Dimensionen. Sie stellt die Gesamtzahl der Elemente dar, die derzeit im Array enthalten sind.  Das folgende Beispiel deklariert z. B. ein 2-dimensionales Array mit vier Elementen in jeder Dimension. Wie die Ausgabe des Beispiels zeigt, wird die Array-Größe ist 16 (oder (3 + 1) * (3 + 1).

 [!code-vb[array-size](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size.vb)]  

> [!NOTE] 
> Die Erläuterung der Arraygröße gilt nicht für verzweigte Arrays. Informationen zu verzweigte Arrays und bestimmen die Größe eines verzweigten Arrays, finden Sie unter der [verzweigte Arrays](#jagged-arrays) Abschnitt.
  
  Sie können die Größe eines Arrays mithilfe der <xref:System.Array.Length%2A?displayProperty=nameWithType>-Eigenschaft bestimmen. Sie finden die Länge der einzelnen Dimensionen eines mehrdimensionalen Arrays mithilfe der <xref:System.Array.GetLength%2A?displayProperty=nameWithType> Methode.  
  
 Sie können Größe einer Arrayvariablen ändern, indem Sie ein neues Arrayobjekt zuweisen oder mithilfe der [ `ReDim` Anweisung](../../../../visual-basic/language-reference/statements/redim-statement.md) Anweisung. Im folgenden Beispiel wird die `ReDim` Anweisung, um ein Array mit 100 Elementen in ein Array mit Elementen 51 zu ändern.

 [!code-vb[resize-an-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size2.vb)]  
  
 Mehrere Faktoren wirken sich auf die Arraygröße aus.  
  
|||  
|---|---|  
|Dimensionslänge|Der Index der einzelnen Dimensionen ist 0-basiert, was bedeutet, dass es Bereich zwischen 0 und dessen obere Grenze. Aus diesem Grund ist die Länge einer bestimmten Dimension um eins größer als die deklarierte Obergrenze dieser Dimension.|  
|Längenbeschränkungen|Die Länge jeder Dimension eines Arrays ist auf den Maximalwert der `Integer` -Datentyp, der ist <xref:System.Int32.MaxValue?displayProperty=nameWithType> oder (2 ^ 31) - 1. Die Gesamtgröße eines Arrays richtet sich nach dem verfügbaren Arbeitsspeicher des Systems und ist damit ebenfalls beschränkt. Wenn Sie versuchen, ein Array zu initialisieren, die Kapazität des verfügbaren Arbeitsspeichers übersteigt, löst die Runtime eine <xref:System.OutOfMemoryException>.|  
|Größe und Elementgröße|Die Größe eines Arrays ist vom Datentyp seiner Elemente unabhängig. Die Größe stellt immer die Gesamtzahl der Elemente, nicht die Anzahl der Bytes, die im Arbeitsspeicher belegen.|  
|Speicherverbrauch|Es gibt keine verbindlichen Angaben darüber, wie ein Array gespeichert wird. Der Speicherverbrauch variiert auf Plattformen mit unterschiedlichen Datenbreiten, d. h. ein und dasselbe Array kann auf einem 64-Bit-System mehr Speicherplatz benötigen als auf einem 32-Bit-System. Abhängig von der Systemkonfiguration beim Initialisieren eines Arrays kann die Common Language Runtime (CLR) Speicher so zuweisen, dass die Elemente auf sehr engem Raum gespeichert werden oder nur die natürlichen Hardwarebeschränkungen gelten. Ein Array benötigt außerdem zusätzlichen Speicher für seine Steuerungsinformationen. Der Bedarf an zusätzlichem Speicher nimmt mit jeder hinzugefügten Dimension zu.|  

## <a name="the-array-type"></a>Der Arraytyp 
 Jedes Array besitzt einen Datentyp, die sich von dem Datentyp seiner Elemente unterscheidet. Es gibt keinen universellen Datentyp, der sich für alle Arrays eignet. Stattdessen wird der Datentyp eines Arrays durch die Anzahl der Dimensionen (den *Rang*) des Arrays bestimmt, sowie durch den Datentyp der Elemente im Array. Datentypen zweier Arrayvariablen werden der gleichen Daten, geben Sie nur, wenn sie den gleichen Rang aufweisen und ihre Elemente den gleichen Datentyp. Die Länge der Dimensionen eines Arrays wirken sich nicht auf den Arraydatentyp aus.  
  
 Jedes Array erbt aus der <xref:System.Array?displayProperty=nameWithType>-Klasse. Sie können eine Variable des Typs `Array` deklarieren, ein Array des Typs `Array` können Sie jedoch nicht erstellen. Beispielsweise, obwohl der folgende Code deklariert die `arr` Variable vom Typ `Array` und ruft die <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> -Methode instanziieren, das Array, das den Typ des Arrays nachgewiesen werden Object [].

 [!code-vb[array-class](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/array-class.vb)] 

Die [ReDim-Anweisung](../../../../visual-basic/language-reference/statements/redim-statement.md) kann nicht für eine Variable verwendet werden, die mit dem Typ `Array` deklariert ist. Aus diesen Gründen und typsicherheit ist es empfehlenswert, jedes Array als bestimmten Typ zu deklarieren.  
  
 Sie können den Datentyp eines Arrays oder seiner Elemente auf verschiedene Arten ermitteln. 
  
-   Sie erreichen die <xref:System.Object.GetType%2A> -Methode für die Variable zum Abrufen einer <xref:System.Type> Objekt, das den Laufzeittyp der Variable darstellt. Das <xref:System.Type> -Objekt stellt in seinen Eigenschaften und Methoden umfassende Informationen bereit.  
  
-   Sie können die Variable übergeben der <xref:Microsoft.VisualBasic.Information.TypeName%2A> Funktion zum Abrufen einer `String` durch den Namen der Laufzeittyp.  
  
 Im folgenden Beispiel wird sowohl die `GetType` Methode und die `TypeName` Funktion, um den Typ eines Arrays zu bestimmen. Der Arraytyp ist `Byte(,)`. Beachten Sie, dass die <xref:System.Type.BaseType%2A?displayProperty=nameWithType> Eigenschaft gibt auch an, dass der Basistyp des Byte-Arrays ist die <xref:System.Array> Klasse.  
  
 [!code-vb[array-type](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/array-type.vb)]  
  
##  <a name="arrays-as-return-values-and-parameters"></a>Arrays als Parameter und Rückgabewerte  
 Damit eine `Function`-Prozedur ein Array zurückgibt, geben Sie den Arraydatentyp und die Anzahl der Dimensionen als Rückgabetyp für die [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md) an. Deklarieren Sie in der Funktion eine lokale Arrayvariable mit dem gleichen Datentyp und der gleichen Anzahl an Dimensionen. Schließen Sie die lokale Arrayvariable ohne Klammern in die [Return-Anweisung](../../../../visual-basic/language-reference/statements/return-statement.md) ein.  
  
 Um ein Array als Parameter für eine `Sub` - oder `Function` -Prozedur anzugeben, definieren Sie den Parameter als Array mit einem bestimmten Datentyp und einer bestimmten Anzahl von Dimensionen. Übergeben Sie im Aufruf an die Prozedur eine Arrayvariable mit dem gleichen Datentyp und die Anzahl von Dimensionen.  
  
 Im folgenden Beispiel die `GetNumbers` -Funktion zurückgegeben wird ein `Integer()`, ein eindimensionales Array vom Typ `Integer`. Die Prozedur `ShowNumbers` akzeptiert ein Argument `Integer()` . 
  
 [!code-vb[return-value-and-params](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params.vb)]  
  
 Im folgenden Beispiel die `GetNumbersMultiDim` -Funktion zurückgegeben wird ein `Integer(,)`, ein zweidimensionales Array vom Typ `Integer`.  Die Prozedur `ShowNumbersMultiDim` akzeptiert ein Argument `Integer(,)` .  
  
 [!code-vb[multidimensional-return-value](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params-2d.vb)]  
  
## <a name="jagged-arrays"></a>Verzweigte Arrays  
 
In einigen Fällen ist die Datenstruktur in einer Anwendung zweidimensional, jedoch nicht rechteckig. Beispielsweise können Sie ein Array verwenden, um Daten zu hoher Temperatur jeden Tag des Monats zu speichern. Die erste Dimension des Arrays darstellt, den Monat, aber die zweite Dimension darstellt, die Anzahl der Tage, und die Anzahl der Tage in einem Monat ist nicht einheitlich. Ein *verzweigtes Array*, was auch genannt wird ein *Array aus Arrays*, eignet sich für solche Szenarien. Ein verzweigtes Array ist ein Array, dessen Elemente auch Arrays sind. Ein verzweigtes Array und jedes Element in einem verzweigten Array können über eine oder mehrere Dimensionen verfügen.  
  
 Im folgenden Beispiel wird ein Array von Monaten, von denen jedes Element ein Array von Tagen ist. Im Beispiel wird ein verzweigtes Array verwendet, da der einzelnen Monate eine unterschiedliche Anzahl von Tagen haben.  Das Beispiel zeigt, wie ein verzweigtes Array erstellen, Zuweisen von Werten, und abgerufen und dessen Werte anzuzeigen.
  
 [!code-vb[jagged-arrays](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged.vb)]  

Im vorherige Beispiel weist Werte auf das verzweigte Array auf Basis von Elementen mit einem `For...Next` Schleife. Sie können auch die Elemente eines verzweigten Arrays Werte zuweisen, mit geschachtelten Arrayliteralen. Der Versuch, verwenden Sie geschachtelte array Literale (z. B. ```Dim valuesjagged = {{1, 2}, {2, 3, 4}}```) verursacht Compilerfehler [BC30568](../../../,,/../misc/bc30568.md). Um den Fehler zu beheben, schließen Sie die inneren Arrayliterale in Klammern ein. Die Klammern erzwingen die Array-literalen Ausdruck ausgewertet werden soll, und die erhaltenen Werte werden mit dem äußeren Arrayliteral, verwendet, wie im folgende Beispiel gezeigt.  
  
 [!code-vb[jagged-array-initialization](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-assign.vb)] 

Ein verzweigtes Array ist ein eindimensionales Array, dessen Elemente Arrays enthält. Aus diesem Grund die <xref:System.Array.Length%2A?displayProperty=nameWithType> Eigenschaft und die `Array.GetLength(0)` Methode die Anzahl von Elementen im eindimensionalen Array zurück und `Array.GetLength(1)` löst ein <xref:System.IndexOutOfRangeException> , da ein verzweigtes Array nicht mehrdimensional ist. Sie bestimmen die Anzahl der Elemente in jedem Unterarray, indem das Abrufen des Werts jedes Teilarray <xref:System.Array.Length%2A?displayProperty=nameWithType> Eigenschaft. Im folgenden Beispiel wird veranschaulicht, wie die Anzahl der Elemente in einem verzweigten Array zu bestimmen.

[!code-vb[jagged-array-size](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-length.vb)] 

## <a name="zero-length-arrays"></a>Arrays mit der Länge 0 (null)  
Visual Basic unterscheidet zwischen ein nicht initialisiertes Array (ein Array, dessen Wert `Nothing`) und ein *Array der Länge null* oder ein leeres Array (ein Array, das über keine Elemente verfügt.) Ein nicht initialisiertes Array ist eine, die nicht dimensioniert wurden, oder hatte wird keine Werte zugewiesen. Zum Beispiel:

```vb
Dim arr() As String
```
Ein Array der Länge 0 (null) wird mit einer Dimension "-1" deklariert. Zum Beispiel:

```vb
Dim arrZ(-1) As String
```
Unter den folgenden Bedingungen müssen Sie eventuell ein Array der Länge 0 (null) erstellen:  
  
-   Ohne Gefahr eines Datenbankausfalls eine <xref:System.NullReferenceException> Ausnahme, der Code muss zugreifen auf Member der <xref:System.Array> Klasse, z. B. <xref:System.Array.Length%2A> oder <xref:System.Array.Rank%2A>, oder rufen Sie eine Visual Basic-Funktion z. B. <xref:Microsoft.VisualBasic.Information.UBound%2A>.  
  
-   Bleiben sollen die Codes nicht überprüfen müssen einfache `Nothing` ein Sonderfall.  
  
-   Der Code interagiert mit einer API (Application Programming Interface), die entweder verlangt, dass mindestens einer Prozedur ein Array der Länge Null übergeben wird. Oder er interagiert mit einer API, die ein solches Array von mindestens einer Prozedur zurückgibt.

## <a name="splitting-an-array"></a>Ein Array Teilen

In einigen Fällen müssen Sie ein einzelnes Array in mehreren Arrays aufgeteilt. Führen Sie dazu den Punkt bzw. die Punkte, an dem das Array aufgeteilt werden, bzw. identifizieren und dann das Array in mindestens zwei separate Arrays Spucken. 

> [!NOTE] 
> Aufteilen einer einzelnen Zeichenfolge in ein Zeichenfolgenarray, das basierend auf einigen Trennzeichen erörtert in diesem Abschnitt nicht. Informationen zum Aufteilen einer Zeichenfolge, finden Sie unter der <xref:System.String.Split%2A?displayProperty=nameWithType> Methode.

Die am häufigsten verwendeten Kriterien für die Aufteilung ein Array sind:

- Die Anzahl der Elemente im Array. Sie möchten z. B. ein Array von mehr als eine angegebene Anzahl von Elementen in eine Anzahl von etwa gleich große Teile aufgeteilt. Zu diesem Zweck können Sie den Rückgabewert von entweder der <xref:System.Array.Length%2A?displayProperty=nameWithType> oder <xref:System.Array.GetLength%2A?displayProperty=nameWithType> Methode.

- Der Wert eines Elements, die als Trennzeichen dient, der angibt, in dem das Array aufgeteilt werden soll. Sie können für einen bestimmten Wert suchen, durch Aufrufen der <xref:System.Array.FindIndex%2A?displayProperty=nameWithType> und <xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType> Methoden.
 
Nachdem Sie ermittelt haben, den Index oder die Indizes, die an dem das Array aufgeteilt werden soll, können Sie die einzelnen Arrays klicken Sie dann erstellen, durch Aufrufen der <xref:System.Array.Copy%2A?displayProperty=nameWithType> Methode. 

Im folgenden Beispiel wird ein Array, in zwei Arrays von ungefähr gleicher Größe. (Wenn die Gesamtanzahl der Arrayelemente ungerade ist, hat das erste Array eine weitere Element als das zweite.) 

[!code-vb[splitting-an-array-by-length](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/split1.vb)] 

Im folgenden Beispiel wird ein Array von Zeichenfolgen in zwei Arrays basierend auf dem Vorhandensein eines Elements, dessen Wert ist "Zzz", die als Arraytrennzeichen dient. Die neuen Arrays enthalten nicht das Element, das als Trennzeichen enthält.

[!code-vb[splitting-an-array-by-delimiter](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/split2.vb)] 

## <a name="joining-arrays"></a>Verknüpfen von arrays

Sie können auch eine Reihe von Arrays in einem einzigen größeren Array kombinieren. Zu diesem Zweck verwenden Sie auch die <xref:System.Array.Copy%2A?displayProperty=nameWithType> Methode. 

> [!NOTE] 
> Verknüpfen ein Array von Zeichenfolgen zu einer einzelnen Zeichenfolge erörtert in diesem Abschnitt nicht. Informationen zum Verknüpfen von einem Array von Zeichenfolgen finden Sie unter der <xref:System.String.Join%2A?displayProperty=nameWithType> Methode.

Bevor Sie die Elemente der einzelnen Arrays in das neue Array kopiert, müssen Sie zunächst sicherstellen, dass Sie das Array initialisiert haben, sodass sie ausreichend Kapazität für Accompodate das neue Array ist. Dazu haben Sie zwei Möglichkeiten:

- Verwenden der [ `ReDim Preserve` ](../../../../visual-basic/language-reference/statements/redim-statement.md) Anweisung, um das Array dynamisch zu erweitern, bevor Sie neue Elemente hinzugefügt. Dies ist das einfachste Verfahren, aber dadurch eine Verringerung der Leistung und eine zu hohe speicherauslastung beim Kopieren von großen Arrays sind.
- Berechnen Sie die Gesamtanzahl der Elemente, die erforderlich sind, für die neue großes Array zu, und fügen Sie die Elemente der einzelnen Quellarray hinzu.

Im folgenden Beispiel wird den zweiten Ansatz vier Arrays mit zehn Elemente in einem Array hinzufügen.  

[!code-vb[joining-an-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/join.vb)] 

Da in diesem Fall die Quellarrays alle klein sind, können wir das Array auch dynamisch erweitern, wenn wir die Elemente eines jeden neuen Array hinzufügen. In folgendem Beispiel wird dies getan.

[!code-vb[joining-an-array-dynamically](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/join2.vb)] 

##  <a name="collections-as-an-alternative-to-arrays"></a>Auflistungen als Alternative zu arrays  
 Arrays eignen sich bestens zum Erstellen und Arbeiten mit einer festen Anzahl von Objekten mit starkem Typ. Auflistungen ermöglichen ein flexibleres Arbeiten mit Objektgruppen. Im Gegensatz zu Arrays, die erfordern, dass Sie explizit ändern, die Größe eines Arrays mit den [ `ReDim` Anweisung](../../../../visual-basic/language-reference/statements/redim-statement.md), Sammlungen dynamisch wachsen oder wenn sich die Anforderungen von einer Anwendung ändern.  
  
 Bei Verwendung von `ReDim` um ein Array zu dimensionieren, Visual Basic erstellt ein neues Array und frei von der vorherigen Abfrage. Dies nimmt Ausführungszeit in Anspruch. Aus diesem Grund, wenn die Anzahl der Elemente, die Arbeit mit häufig ändert oder Sie die maximale Anzahl von Elementen jedoch nicht ist, die Sie benötigen vorhersehbar, müssen Sie in der Regel eine bessere Leistung abrufen mithilfe einer Auflistung.  
  
 Bei einigen Auflistungen können Sie jedem Objekt, das Sie in die Auflistung einfügen, einen Schlüssel zuweisen, sodass das Objekt anhand des Schlüssels schnell abgerufen werden kann.  
  
 Wenn die Auflistung Elemente eines Datentyps enthält, können Sie eine der Klassen im <xref:System.Collections.Generic?displayProperty=nameWithType> -Namespace verwenden. Eine generische Auflistung erzwingt Typsicherheit, sodass der Auflistung kein anderer Datentyp hinzugefügt werden kann.  
  
 Weitere Informationen über Auflistungen finden Sie unter [Auflistungen](../../concepts/collections.md).
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Begriff|Definition|  
|----------|----------------|  
|[Array Dimensions in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)|Erläutert Rang und Dimensionen in Arrays.|  
|[How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Gewusst wie: Initialisieren einer Arrayvariable in Visual Basic)|Beschreibt das Auffüllen von Arrays mit Anfangswerten.|  
|[How to: Sort An Array in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-sort-an-array.md) (Gewusst wie: Sortieren eines Arrays in Visual Basic)|Erläutert, wie die Elemente eines Arrays alphabetisch sortiert werden.|  
|[Gewusst wie: Zuweisen eines Arrays zu einem anderen Array](../../../../visual-basic/programming-guide/language-features/arrays/how-to-assign-one-array-to-another-array.md)|Beschreibt die Regeln und Schritte zum Zuweisen eines Arrays an eine andere Arrayvariable.|  
|[Problembehandlung bei Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)|Erörtert einige allgemeine Probleme, die beim Arbeiten mit Arrays auftreten.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Array?displayProperty=nameWithType>  
 [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [ReDim-Anweisung](../../../../visual-basic/language-reference/statements/redim-statement.md)
