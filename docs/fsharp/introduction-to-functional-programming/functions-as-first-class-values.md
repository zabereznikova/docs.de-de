---
title: Funktionen als erstrangige Werte (F#)
description: Erfahren Sie, wie Funktionen als erstrangige in der Programmiersprache f# erhöht werden.
ms.date: 05/16/2016
ms.openlocfilehash: cccff5fcf9de150da26422f80cae032ddf21014c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566664"
---
# <a name="functions-as-first-class-values"></a>Funktionen als erstrangige Werte

Eine wichtige Eigenschaft funktionaler Programmiersprachen ist die Behandlung von Funktionen als erstrangige Werte. Sie sollten mit einer Funktion ohne Mehraufwand alle Vorgänge ausführen können, die Sie auch mit den Werten der anderen integrierten Typen ausführen können.

Zur Feststellung der Erstrangigkeit gehören folgende Kriterien:

- Binden Sie können Funktionen auf Bezeichner? D. h., können Sie ihnen Namen geben?

- Können Sie Funktionen in den Datenstrukturen, z. B. in einer Liste speichern?

- Kann eine Funktion in einem Funktionsaufruf als Argument werden übergeben?

- Können Sie eine Funktion aus einem Funktionsaufruf zurückgeben?

Die letzten beiden Measures definieren, so genannten *Operationen höherer Ordnung* oder *Funktionen höherer Ordnung*. Funktionen höherer Ordnung unterstützen Funktionen als Argumente und geben Funktionen als Werte von Funktionsaufrufen zurück. Diese Operationen bilden die Grundlage für die Hauptstützen der funktionalen Programmierung, wie z. B. Zuordnungsfunktionen und Funktionszusammensetzung.


## <a name="give-the-value-a-name"></a>Zuweisen eines Namens zu einem Wert

Einem erstrangigen Funktionswert muss wie ganzen Zahlen, Zeichenfolgen und anderen integrierten Typen ein Name zugewiesen werden können. Bei der funktionalen Programmierung wird dies als Bindung eines Bezeichners an einen Wert ausgedrückt. F# verwendet [ `let` Bindungen](../language-reference/functions/let-bindings.md) zum Binden von Namen an Werte: `let <identifier> = <value>`. Der folgende Code enthält zwei Beispiele.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

Das Zuweisen eines Namens zu einer Funktion ist ebenso einfach. Das folgende Beispiel definiert eine Funktion namens `squareIt` durch den Bezeichner binden `squareIt` auf die [Lambda-Ausdruck](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`. Die Funktion `squareIt` verfügt über einen Parameter `n` und gibt das Quadrat dieses Parameters zurück.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

Durch die folgende kürzere Syntax in F# erzielen Sie das gleiche Ergebnis mit weniger Aufwand.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

In den folgenden Beispielen wird meist das erste Format (`let <function-name> = <lambda-expression>`) verwendet, um die Ähnlichkeiten zwischen der Deklaration von Funktionen und der Deklaration anderer Werttypen hervorzuheben. Sie können jedoch alle benannten Funktionen mit der kürzeren Syntax schreiben. In einigen Beispielen werden beide Formate verwendet.


## <a name="store-the-value-in-a-data-structure"></a>Speichern des Werts in einer Datenstruktur

Sie können erstrangige Werte in einer Datenstruktur speichern. Der folgende Code enthält Beispiele, in denen Werte in Listen und Tupeln gespeichert werden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

Um zu überprüfen, ob ein in einem Tupel gespeicherter Funktionsname tatsächlich eine Funktion ergibt, werden im folgenden Beispiel mit dem `fst`-Operator und dem `snd`-Operator das erste und das zweite Element des Tupels `funAndArgTuple` extrahiert. Das erste Element im Tupel ist `squareIt`, das zweite Element ist `num`. Der Bezeichner `num` wurde in einem vorangehenden Beispiel an die ganze Zahl 10 gebunden, ein gültiges Argument für die `squareIt`-Funktion. Der zweite Ausdruck wendet das erste Element im Tupel auf das zweite Element im Tupel an: `squareIt num`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

Ebenso wie der Bezeichner `num` und die ganze Zahl 10 sind auch der Bezeichner `squareIt` und der lambda-Ausdruck `fun n -> n * n` austauschbar.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]
    
## <a name="pass-the-value-as-an-argument"></a>Übergeben des Werts als Argument

Werte mit erstrangigem Status in einer Sprache können als Argumente an eine Funktion übergeben werden. So werden z. B. ganze Zahlen und Zeichenfolgen häufig als Argumente übergeben. Im folgenden Code werden ganze Zahlen und Zeichenfolgen in F# als Argumente übergeben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

Funktionen mit erstrangigem Status müssen sich ebenso als Argumente übergeben lassen. Hierbei handelt es sich um die erste Eigenschaft von Funktionen höherer Ordnung.

Die Funktion `applyIt` im folgenden Beispiel verfügt über die beiden Parameter `op` und `arg`. Wenn Sie eine Funktion mit einem Parameter für `op` und ein entsprechendes Funktionsargument für `arg` senden, gibt die Funktion ein Ergebnis zurück, das sich aus der Anwendung von `op` auf `arg` ergibt. Im folgenden Beispiel wird sowohl zum Senden des Funktionsarguments als auch zum Senden des ganzzahligen Arguments der jeweilige Name verwendet.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

Die Fähigkeit, eine Funktion als Argument an eine andere Funktion zu übergeben, unterliegt in funktionalen Programmiersprachen allgemeinen Abstraktionen, wie z. B. Zuordnungs- und Filteroperationen. Um eine Zuordnungsoperation handelt es sich z. B. bei einer Funktion höherer Ordnung, mit der die Berechnung von Funktionen erfasst wird, die eine Liste durchlaufen, eine bestimmte Aktion für jedes Element ausführen und dann eine Liste mit den Ergebnissen zurückgeben. Auf diese Weise können Sie z. B. die einzelnen Element in einer Liste mit ganzen Zahlen um einen bestimmten Wert erhöhen oder quadrieren oder die Elemente in einer Liste mit Zeichenfolgen in Großschreibung ändern. Der fehleranfällige Teil dieser Berechnung ist der rekursive Prozess, mit dem die Liste durchlaufen und eine Liste der zurückzugebenden Ergebnisse erstellt wird. Dieser Teil wird von der Zuordnungsfunktion ausgeführt. Sie müssen für eine bestimmte Anwendung lediglich die Funktion schreiben, die auf jedes einzelne Element in der Liste angewendet werden soll (Addieren, Quadrieren, in Großschreibung ändern). Diese Funktion wird als Argument an die Zuordnungsfunktion gesendet, wie im vorangehenden Beispiel, in dem `squareIt` an `applyIt` gesendet wird.

F# stellt Zuordnungsmethoden für die meisten Auflistungstypen, einschließlich [listet](../language-reference/lists.md), [Arrays](../language-reference/arrays.md), und [Sequenzen](../language-reference/sequences.md). In den folgenden Beispielen werden Listen verwendet. Die Syntax lautet `List.map <the function> <the list>`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

Weitere Informationen finden Sie unter [listet](../language-reference/lists.md).

## <a name="return-the-value-from-a-function-call"></a>Zurückgeben des Werts aus einem Funktionsaufruf

Schließlich müssen sich Funktion mit erstrangigem Status in einer Sprache als Wert aus einem Funktionsaufruf zurückgeben lassen, ebenso wie andere Typen, z. B. ganze Zahlen oder Zeichenfolgen.

Mit den folgenden Funktionsaufrufen werden ganze Zahlen zurückgegeben und angezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

Mit dem folgenden Funktionsaufruf wird eine Zeichenfolge zurückgegeben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

Mit dem folgenden inline deklarierten Funktionsaufruf wird ein boolescher Wert zurückgegeben. Der angezeigte Wert ist `True`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

Die Fähigkeit, eine Funktion als Wert eines Funktionsaufrufs zurückzugeben, ist die zweite Eigenschaft von Funktionen höherer Ordnung. Im folgenden Beispiel wird `checkFor` als Funktion definiert, die ein Argument erfordert (`item`) und eine neue Funktion als Wert zurückgibt. Die zurückgegebene Funktion erfordert eine Liste als Argument (`lst`) und führt in `item` eine Suche nach `lst` aus. Wenn `item` gefunden wird, gibt die Funktion `true` zurück. Wenn `item` nicht vorhanden ist, wird `false` zurückgegeben. Wie im vorherigen Abschnitt, der folgende Code verwendet eine Funktion bereitgestellte Liste [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), um die Liste zu suchen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

Im folgenden Code wird mit `checkFor` eine neue Funktion erstellt, die ein Listenargument erfordert und in der Liste nach der Zahl 7 sucht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

Im folgenden Beispiel wird der erstrangige Funktionsstatus in F# verwendet, um die Funktion `compose` zu deklarieren, die eine Zusammensetzung von zwei Funktionsargumenten zurückgibt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]
    
>[!NOTE]
Eine noch kürzere Version finden Sie im folgenden Abschnitt, "Funktionen mit Currying".


Mit dem folgenden Code werden zwei Funktionen als Argumente an `compose` gesendet, die beide ein einzelnes Argument desselben Typs erfordern. Der Rückgabewert ist eine neue Funktion, bei der es sich um eine Zusammensetzung der beiden Funktionsargumente handelt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]
    
>[!NOTE] 
F# bietet zwei Operatoren zum Zusammensetzen von Funktionen: `<<` und `>>`. `let squareAndDouble2 = doubleIt << squareIt` entspricht im vorangehenden Beispiel `let squareAndDouble = compose doubleIt squareIt`.

Im folgenden Beispiel zur Rückgabe einer Funktion als Wert eines Funktionsaufrufs wird ein einfaches Ratespiel erstellt. Rufen Sie zum Erstellen eines Spiels `makeGame` auf, und senden Sie den Wert, der erraten werden soll, an `target`. Der Rückgabewert der Funktion `makeGame` ist eine Funktion, die ein Argument erfordert (den zu erratenden Wert) und zurückgibt, ob richtig geraten wurde.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

Im folgenden Code wird `makeGame` aufgerufen und der Wert `7` an `target` gesendet. Der Bezeichner `playGame` wird an den zurückgegebenen Lambda-Ausdruck gebunden. Somit ist `playGame` eine Funktion, die den Wert für `guess` als einzelnes Argument erfordert.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]
    
## <a name="curried-functions"></a>Funktionen mit Currying

In vielen der Beispiele im vorherigen Abschnitt geschrieben werden können noch kürzer fassen durch Nutzen der impliziten *currying* in Funktionsdeklarationen in F# erläutert werden. Beim sogenannten Currying wird eine Funktion mit mehreren Parametern in eine Reihe eingebetteter Funktionen mit jeweils einem einzelnen Parameter transformiert. In F# wird Currying grundsätzlich auf Funktionen mit mehreren Parametern angewendet. Beispiel: `compose` aus dem vorherigen Abschnitt kann in dem folgenden kurz gefassten Format mit drei Parametern geschrieben werden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

Das Ergebnis ist eine Funktion mit einem Parameter, die eine Funktion mit einem Parameter zurückgibt, die wiederum eine Funktion mit einem Parameter zurückgibt (siehe `compose4curried`).

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

Für den Zugriff auf diese Funktion haben Sie verschiedene Möglichkeiten. In jedem der folgenden Beispiele wird 18 zurückgegeben und angezeigt. Sie können in jedem der Beispiele `compose4` durch `compose4curried` ersetzen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

Um zu überprüfen, ob die Funktion wie gehabt funktioniert, verwenden Sie die ursprünglichen Testsituationen erneut.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]
    
>[!NOTE] 
Zur Einschränkung von Currying können Sie die Parameter in Tupeln einschließen. Weitere Informationen finden Sie unter "Muster der Parameter" in [Parameter und Argumente](../language-reference/parameters-and-arguments.md).

Im folgenden Beispiel wird mit implizitem Currying eine kürzere Version von `makeGame` geschrieben. Wie `makeGame` die `game`-Funktion erstellt und zurückgibt, ist in diesem Format weniger explizit, Sie können das Ergebnis aber mit den ursprünglichen Testsituationen überprüfen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

Weitere Informationen zu currying finden Sie unter "Partielle Anwendung von Argumenten" in [Funktionen](../language-reference/functions/index.md).


## <a name="identifier-and-function-definition-are-interchangeable"></a>Bezeichner und Funktionsdefinition sind austauschbar
Der Variablenname `num` in den vorherigen Beispielen ergibt die ganze Zahl 10, wenn also `num` gültig ist, hat 10 ebenso Gültigkeit. Dasselbe gilt für Funktionsbezeichner und ihre Werte: Wenn der Name der Funktion verwendet werden kann, kann auch der daran gebundene lambda-Ausdruck verwendet werden.

Im folgenden Beispiel wird eine `Boolean`-Funktion mit dem Namen `isNegative` definiert. Dann werden Funktionsname und Funktionsdefinition beliebig ausgetauscht. In den nächsten drei Beispielen wird immer `False` zurückgegeben und angezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

Gehen Sie noch einen Schritt weiter und ersetzen Sie `applyIt` durch den Wert, an den `applyIt` gebunden ist.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a>Funktionen in F# sind erstrangige Werte #

Die Beispiele in den vorherigen Abschnitten veranschaulichen, dass die Funktionen in F# die Kriterien für erstrangige Werte in F# erfüllen:

- Sie können einen Bezeichner an eine Funktionsdefinition binden.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- Sie können eine Funktion in einer Datenstruktur speichern.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- Sie können eine Funktion als Argument übergeben.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- Sie können eine Funktion als Wert eines Funktionsaufrufs zurückgeben.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

Weitere Informationen zu F# erläutert werden, finden Sie unter der [f#-Sprachreferenz](../language-reference/index.md).

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Der folgende Code enthält alle Beispiele aus diesem Thema.

### <a name="code"></a>Code

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]
    
## <a name="see-also"></a>Siehe auch

[Listen](../language-reference/lists.md)

[Tupel](../language-reference/tuples.md)

[Funktionen](../language-reference/functions/index.md)

[`let` Bindungen](../language-reference/functions/let-bindings.md)

[Lambda-Ausdrücke: Das `fun` Schlüsselwort](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
