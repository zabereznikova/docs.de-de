---
title: Funktionen erster Klasse
description: 'Erfahren Sie mehr über erstklassige Funktionen und deren Bedeutung für die funktionale Programmierung in F #.'
ms.date: 10/29/2018
ms.openlocfilehash: 1dc8eae1655187282f05bf4e9501ecc8a17deba8
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810910"
---
# <a name="first-class-functions"></a>Funktionen erster Klasse

Eine wichtige Eigenschaft funktionaler Programmiersprachen ist die Behandlung von Funktionen als erstrangige Werte. Sie sollten mit einer Funktion ohne Mehraufwand alle Vorgänge ausführen können, die Sie auch mit den Werten der anderen integrierten Typen ausführen können.

Zur Feststellung der Erstrangigkeit gehören folgende Kriterien:

- Können Sie Funktionen an Bezeichner binden? Das heißt, Sie können Namen nennen?

- Können Funktionen in Datenstrukturen, z. b. in einer Liste, gespeichert werden?

- Können Sie eine Funktion als Argument in einem Funktions aufzurufen übergeben?

- Können Sie eine Funktion von einem Funktions Aufrufwert zurückgeben?

Die letzten beiden Measures definieren, was als *Vorgänge höherer Ordnung* oder *Funktionen höherer Ordnung*bezeichnet werden. Funktionen höherer Ordnung unterstützen Funktionen als Argumente und geben Funktionen als Werte von Funktionsaufrufen zurück. Diese Operationen bilden die Grundlage für die Hauptstützen der funktionalen Programmierung, wie z. B. Zuordnungsfunktionen und Funktionszusammensetzung.

## <a name="give-the-value-a-name"></a>Zuweisen eines Namens zu einem Wert

Einem erstrangigen Funktionswert muss wie ganzen Zahlen, Zeichenfolgen und anderen integrierten Typen ein Name zugewiesen werden können. Bei der funktionalen Programmierung wird dies als Bindung eines Bezeichners an einen Wert ausgedrückt. F # verwendet [ `let` Bindungen](../language-reference/functions/let-bindings.md) zum Binden von Namen an Werte: `let <identifier> = <value>` . Der folgende Code enthält zwei Beispiele.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet20.fs)]

Das Zuweisen eines Namens zu einer Funktion ist ebenso einfach. Im folgenden Beispiel wird eine Funktion mit dem Namen definiert `squareIt` , indem der Bezeichner `squareIt` an den [Lambda-Ausdruck](../language-reference/functions/lambda-expressions-the-fun-keyword.md) gebunden wird `fun n -> n * n` . Die Funktion `squareIt` verfügt über einen Parameter `n` und gibt das Quadrat dieses Parameters zurück.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

Durch die folgende kürzere Syntax in F# erzielen Sie das gleiche Ergebnis mit weniger Aufwand.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet22.fs)]

In den folgenden Beispielen wird meist das erste Format (`let <function-name> = <lambda-expression>`) verwendet, um die Ähnlichkeiten zwischen der Deklaration von Funktionen und der Deklaration anderer Werttypen hervorzuheben. Sie können jedoch alle benannten Funktionen mit der kürzeren Syntax schreiben. In einigen Beispielen werden beide Formate verwendet.

## <a name="store-the-value-in-a-data-structure"></a>Speichern des Werts in einer Datenstruktur

Sie können erstrangige Werte in einer Datenstruktur speichern. Der folgende Code enthält Beispiele, in denen Werte in Listen und Tupeln gespeichert werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet23.fs)]

Um zu überprüfen, ob ein in einem Tupel gespeicherter Funktionsname tatsächlich eine Funktion ergibt, werden im folgenden Beispiel mit dem `fst`-Operator und dem `snd`-Operator das erste und das zweite Element des Tupels `funAndArgTuple` extrahiert. Das erste Element im Tupel ist `squareIt`, das zweite Element ist `num`. Der Bezeichner `num` wurde in einem vorangehenden Beispiel an die ganze Zahl 10 gebunden, ein gültiges Argument für die `squareIt`-Funktion. Der zweite Ausdruck wendet das erste Element im Tupel auf das zweite Element im Tupel an: `squareIt num`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet24.fs)]

Ebenso wie der Bezeichner `num` und die ganze Zahl 10 sind auch der Bezeichner `squareIt` und der lambda-Ausdruck `fun n -> n * n` austauschbar.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet25.fs)]

## <a name="pass-the-value-as-an-argument"></a>Übergeben des Werts als Argument

Werte mit erstrangigem Status in einer Sprache können als Argumente an eine Funktion übergeben werden. So werden z. B. ganze Zahlen und Zeichenfolgen häufig als Argumente übergeben. Im folgenden Code werden ganze Zahlen und Zeichenfolgen in F# als Argumente übergeben.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet26.fs)]

Funktionen mit erstrangigem Status müssen sich ebenso als Argumente übergeben lassen. Hierbei handelt es sich um die erste Eigenschaft von Funktionen höherer Ordnung.

Die Funktion `applyIt` im folgenden Beispiel verfügt über die beiden Parameter `op` und `arg`. Wenn Sie eine Funktion mit einem Parameter für `op` und ein entsprechendes Funktionsargument für `arg` senden, gibt die Funktion ein Ergebnis zurück, das sich aus der Anwendung von `op` auf `arg` ergibt. Im folgenden Beispiel wird sowohl zum Senden des Funktionsarguments als auch zum Senden des ganzzahligen Arguments der jeweilige Name verwendet.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet27.fs)]

Die Fähigkeit, eine Funktion als Argument an eine andere Funktion zu übergeben, unterliegt in funktionalen Programmiersprachen allgemeinen Abstraktionen, wie z. B. Zuordnungs- und Filteroperationen. Um eine Zuordnungsoperation handelt es sich z. B. bei einer Funktion höherer Ordnung, mit der die Berechnung von Funktionen erfasst wird, die eine Liste durchlaufen, eine bestimmte Aktion für jedes Element ausführen und dann eine Liste mit den Ergebnissen zurückgeben. Auf diese Weise können Sie z. B. die einzelnen Element in einer Liste mit ganzen Zahlen um einen bestimmten Wert erhöhen oder quadrieren oder die Elemente in einer Liste mit Zeichenfolgen in Großschreibung ändern. Der fehleranfällige Teil dieser Berechnung ist der rekursive Prozess, mit dem die Liste durchlaufen und eine Liste der zurückzugebenden Ergebnisse erstellt wird. Dieser Teil wird von der Zuordnungsfunktion ausgeführt. Sie müssen für eine bestimmte Anwendung lediglich die Funktion schreiben, die auf jedes einzelne Element in der Liste angewendet werden soll (Addieren, Quadrieren, in Großschreibung ändern). Diese Funktion wird als Argument an die Zuordnungsfunktion gesendet, wie im vorangehenden Beispiel, in dem `squareIt` an `applyIt` gesendet wird.

F # stellt Zuordnungs Methoden für die meisten [Auflistungs](../language-reference/lists.md)Typen bereit, einschließlich Listen, [Arrays](../language-reference/arrays.md)und [Sequenzen](../language-reference/sequences.md). In den folgenden Beispielen werden Listen verwendet. Die Syntax ist `List.map <the function> <the list>`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet28.fs)]

Weitere Informationen finden Sie unter [Listen](../language-reference/lists.md).

## <a name="return-the-value-from-a-function-call"></a>Zurückgeben des Werts aus einem Funktionsaufruf

Schließlich müssen sich Funktion mit erstrangigem Status in einer Sprache als Wert aus einem Funktionsaufruf zurückgeben lassen, ebenso wie andere Typen, z. B. ganze Zahlen oder Zeichenfolgen.

Mit den folgenden Funktionsaufrufen werden ganze Zahlen zurückgegeben und angezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet29.fs)]

Mit dem folgenden Funktionsaufruf wird eine Zeichenfolge zurückgegeben.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet30.fs)]

Mit dem folgenden inline deklarierten Funktionsaufruf wird ein boolescher Wert zurückgegeben. Der angezeigte Wert ist `True`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet31.fs)]

Die Fähigkeit, eine Funktion als Wert eines Funktionsaufrufs zurückzugeben, ist die zweite Eigenschaft von Funktionen höherer Ordnung. Im folgenden Beispiel wird `checkFor` als Funktion definiert, die ein Argument erfordert (`item`) und eine neue Funktion als Wert zurückgibt. Die zurückgegebene Funktion erfordert eine Liste als Argument (`lst`) und führt in `item` eine Suche nach `lst` aus. Wenn `item` gefunden wird, gibt die Funktion `true` zurück. Wenn `item` nicht vorhanden ist, wird `false` zurückgegeben. Wie im vorherigen Abschnitt wird im folgenden Code eine bereitgestellte Listenfunktion, [List. vorhanden](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists), verwendet, um die Liste zu durchsuchen.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

Im folgenden Code wird mit `checkFor` eine neue Funktion erstellt, die ein Listenargument erfordert und in der Liste nach der Zahl 7 sucht.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet33.fs)]

Im folgenden Beispiel wird der erstrangige Funktionsstatus in F# verwendet, um die Funktion `compose` zu deklarieren, die eine Zusammensetzung von zwei Funktionsargumenten zurückgibt.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet34.fs)]

> [!NOTE]
> Eine noch kürzere Version finden Sie im folgenden Abschnitt, "Funktionen mit Currying".

Mit dem folgenden Code werden zwei Funktionen als Argumente an `compose` gesendet, die beide ein einzelnes Argument desselben Typs erfordern. Der Rückgabewert ist eine neue Funktion, bei der es sich um eine Zusammensetzung der beiden Funktionsargumente handelt.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet35.fs)]

> [!NOTE]
> F# bietet zwei Operatoren zum Zusammensetzen von Funktionen: `<<` und `>>`. `let squareAndDouble2 = doubleIt << squareIt` entspricht im vorangehenden Beispiel `let squareAndDouble = compose doubleIt squareIt`.

Im folgenden Beispiel zur Rückgabe einer Funktion als Wert eines Funktionsaufrufs wird ein einfaches Ratespiel erstellt. Rufen Sie zum Erstellen eines Spiels `makeGame` auf, und senden Sie den Wert, der erraten werden soll, an `target`. Der Rückgabewert der Funktion `makeGame` ist eine Funktion, die ein Argument erfordert (den zu erratenden Wert) und zurückgibt, ob richtig geraten wurde.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet36.fs)]

Im folgenden Code wird `makeGame` aufgerufen und der Wert `7` an `target` gesendet. Der Bezeichner `playGame` wird an den zurückgegebenen Lambdaausdruck gebunden. Somit ist `playGame` eine Funktion, die den Wert für `guess` als einzelnes Argument erfordert.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet37.fs)]

## <a name="curried-functions"></a>Funktionen mit Currying

Viele der Beispiele im vorherigen Abschnitt können ausführlicher geschrieben werden, indem die impliziten *Currying* in F #-Funktions Deklarationen genutzt werden. Beim sogenannten Currying wird eine Funktion mit mehreren Parametern in eine Reihe eingebetteter Funktionen mit jeweils einem einzelnen Parameter umgewandelt. In F# wird Currying grundsätzlich auf Funktionen mit mehreren Parametern angewendet. Beispiel: `compose` aus dem vorherigen Abschnitt kann in dem folgenden kurz gefassten Format mit drei Parametern geschrieben werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet38.fs)]

Das Ergebnis ist eine Funktion mit einem Parameter, die eine Funktion mit einem Parameter zurückgibt, die wiederum eine Funktion mit einem Parameter zurückgibt (siehe `compose4curried`).

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet39.fs)]

Für den Zugriff auf diese Funktion haben Sie verschiedene Möglichkeiten. In jedem der folgenden Beispiele wird 18 zurückgegeben und angezeigt. Sie können in jedem der Beispiele `compose4` durch `compose4curried` ersetzen.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet40.fs)]

Um zu überprüfen, ob die Funktion wie gehabt funktioniert, verwenden Sie die ursprünglichen Testsituationen erneut.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet41.fs)]

> [!NOTE]
> Zur Einschränkung von Currying können Sie die Parameter in Tupeln einschließen. Weitere Informationen finden Sie unter "Parameter Muster" in [Parametern und Argumenten](../language-reference/parameters-and-arguments.md).

Im folgenden Beispiel wird mit implizitem Currying eine kürzere Version von `makeGame` geschrieben. Wie `makeGame` die `game`-Funktion erstellt und zurückgibt, ist in diesem Format weniger explizit, Sie können das Ergebnis aber mit den ursprünglichen Testsituationen überprüfen.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet42.fs)]

Weitere Informationen zur Currying finden Sie unter "partielle Anwendung von Argumenten" in [Functions](../language-reference/functions/index.md).

## <a name="identifier-and-function-definition-are-interchangeable"></a>Bezeichner und Funktionsdefinition sind austauschbar

Der Variablenname `num` in den vorherigen Beispielen ergibt die ganze Zahl 10, wenn also `num` gültig ist, hat 10 ebenso Gültigkeit. Dasselbe gilt für Funktionsbezeichner und ihre Werte: Wenn der Name der Funktion verwendet werden kann, kann auch der daran gebundene Lambdaausdruck verwendet werden.

Im folgenden Beispiel wird eine `Boolean`-Funktion mit dem Namen `isNegative` definiert. Dann werden Funktionsname und Funktionsdefinition beliebig ausgetauscht. In den nächsten drei Beispielen wird immer `False` zurückgegeben und angezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet43.fs)]

Gehen Sie noch einen Schritt weiter und ersetzen Sie `applyIt` durch den Wert, an den `applyIt` gebunden ist.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a>Funktionen sind erstklassige Werte in F\#

Die Beispiele in den vorherigen Abschnitten veranschaulichen, dass die Funktionen in F# die Kriterien für erstrangige Werte in F# erfüllen:

- Sie können einen Bezeichner an eine Funktionsdefinition binden.
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

- Sie können eine Funktion in einer Datenstruktur speichern.
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet45.fs)]

- Sie können eine Funktion als Argument übergeben.
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet46.fs)]

- Sie können eine Funktion als Wert eines Funktionsaufrufs zurückgeben.
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

Weitere Informationen zu f # finden Sie in der [f #-Sprachreferenz](../language-reference/index.md).

## <a name="example"></a>Beispiel

### <a name="description"></a>BESCHREIBUNG

Der folgende Code enthält alle Beispiele aus diesem Thema.

### <a name="code"></a>Code

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet47.fs)]

## <a name="see-also"></a>Siehe auch

- [Listen](../language-reference/lists.md)
- [Tupel](../language-reference/tuples.md)
- [Funktionen](../language-reference/functions/index.md)
- [`let` Land](../language-reference/functions/let-bindings.md)
- [Lambda-Ausdrücke: das- `fun` Schlüsselwort](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
