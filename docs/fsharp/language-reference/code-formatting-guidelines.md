---
title: Richtlinien für das Formatieren von Code (F#)
description: Erfahren Sie, Richtlinien für Fehlercodes Einzug Formatierung für die Programmiersprache für die Lesbarkeit, Ästhetik, Standardisierung und Kompilierung f#.
ms.date: 05/16/2016
ms.openlocfilehash: 5bb1f9958a21beb795f9174e44f24c7194453fc3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564829"
---
# <a name="code-formatting-guidelines"></a>Richtlinien für das Formatieren von Code

In diesem Thema werden Richtlinien für Fehlercodes für Einzüge für f# zusammengefasst. Da die Programmiersprache f# empfindlich gegenüber Zeilenumbrüche und Einzüge ist, ist es nicht nur ein Problem Lesbarkeit, Layoutgründen Problem oder Standardisierung Codierungsproblem zur ordnungsgemäßen Formatierung von Code. Sie müssen den Code für die er ordnungsgemäß kompiliert formatieren.


## <a name="general-rules-for-indentation"></a>Allgemeine Regeln für den Einzug
Wenn Einzug erforderlich ist, müssen Sie Leerzeichen, nicht-Registerkarten verwenden. Mindestens eine Leerstelle ist erforderlich. Ihre Organisation kann Codierungsstandards zum Angeben der Anzahl von Leerzeichen zum einrücken verwendet erstellen; drei oder vier Speicherplätzen Einzugsebene an jede Einzugsebene entspricht den Erwartungen. Können Sie entsprechend Ihrer Organisation Einzugsstandards durch Ändern der Optionen in Visual Studio Konfigurieren der `Options` (Dialogfeld), in der `Tools` Menü. In der `Text Editor` Knoten erweitern `F#` , und klicken Sie dann auf `Tabs`. Eine Beschreibung der verfügbaren Optionen finden Sie in [Optionen, Text-Editor, alle Sprachen, Registerkarten](https://msdn.microsoft.com/library/7sffa753.aspx).

Wenn der Compiler Code analysiert wird, behält es im Allgemeinen einen internen Stapel, der die aktuelle Ebene der Schachtelung angibt. Wenn Code eingezogen wird, wird keine neue Ebene der Schachtelung erstellt oder auf dem internen Stapel abgelegt. Wenn ein Konstrukt beendet wird, wird die Ebene per pop ausgelesen. Der Einzug ist eine Möglichkeit, signalisiert das Ende einer Ebene und im internen Stapel pop, bestimmte Token verursacht jedoch auch die Ebene, z. B. per pop ausgelesen werden die `end` -Schlüsselwort, oder eine schließende geschweifte Klammer oder Klammer.

Code in einem mehrzeiligen Konstrukt, z. B. eine Typdefinition Funktionsdefinition `try...with` -Konstrukt und Schleifenkonstrukte, relativ zur ersten Zeile des Konstrukts eingezogen werden müssen. Die erste Zeile eingezogene stellt eine Spaltenposition für nachfolgenden Code in dasselbe Konstrukt her. Die Einzugsebene wird aufgerufen, eine *Kontext*. Die Spaltenposition legt eine minimale Spalte als bezeichnet ein *Einrückungsgrenze*, für nachfolgende Codezeilen, die sich in demselben Kontext befinden. Beim Auftreten einer Codezeile, die kleiner als die festgelegte Spaltenposition eingezogen wird, nimmt der Compiler an, dass der Kontext beendet wurde und jetzt auf der Ebene, in den vorherigen Kontext Codierung. Der Begriff *Einrückungsende* wird verwendet, um die Bedingung zu beschreiben, in der eine Codezeile löst das Ende eines Konstrukts, da sie nicht weit genug eingezogen ist. Anders ausgedrückt, ist Code auf der linken Seite des Einrückungsgrenze Einrückungsende. Im ordnungsgemäß eingezogen Code nutzen Sie das Einrückungsende um das Ende von Konstrukten skizziert. Wenn Sie den Einzug nicht ordnungsgemäß verwenden, kann Einrückungsende kann bewirken, dass der Compiler eine Warnung ausgeben oder zu einem falschen Interpretationen des Codes.

Einrückungsgrenzen werden wie folgt bestimmt.


- Ein `=` zugeordnete Sperrtoken eine `let` eine Einrückungsgrenze in der Spalte der ersten Token nach der `=` anmelden.


- In einer `if...then...else` Ausdruck, der die Spaltenposition des ersten Tokens nach der `then` Schlüsselwort oder der `else` Schlüsselwort eine Einrückungsgrenze.


- In einem `try...with` Ausdruck, der das erste Token nach `try` eine Einrückungsgrenze.


- In einem `match` Ausdruck, der das erste Token nach `with` und dem ersten Token nach jedem `->` Einrückungsgrenzen.


- Das erste Token nach `with` in einem Typ Erweiterung eine Einrückungsgrenze.


- Das erste Token nach einer öffnenden geschweiften Klammer oder Klammer oder nach dem `begin` Schlüsselwort eine Einrückungsgrenze.


- Das erste Zeichen in den Schlüsselwörtern `let`, `if`, und `module` Einrückungsgrenzen.


Die folgenden Codebeispiele veranschaulichen die Einzugsregeln. Die print-Anweisungen abhängig hier Einzug, um sie mit den entsprechenden Kontext zuzuordnen. Jedes Mal, wenn der Einzug geändert wird, wird der Kontext per pop ausgelesen wird und in den vorherigen Kontext zurück. Aus diesem Grund wird ein Leerzeichen am Ende jeder Iteration ausgegeben. "Fertig"! einmal wird nur ausgegeben werden, da die Einrückungsendes, dass er nicht Teil der Schleife ist. Das Drucken der Zeichenfolge "Der obersten Ebene Kontext" ist nicht Teil der Funktion. Aus diesem Grund ist es zunächst während der statischen Initialisierung gedruckt, bevor die Funktion aufgerufen wird.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet1.fs)]

Die Ausgabe lautet wie folgt.

```
Top-level context

(Negative number) Zero 1 2 3 Done!
```

Wenn Sie lange Zeilen aufheben, muss die Fortsetzung der Zeile weiter das einschließende Konstrukt eingezogen werden. Beispielsweise müssen Funktionsargumente weiter das erste Zeichen des Funktionsnamens, eingezogen werden, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet2.fs)]

Es sind Ausnahmen von diesen Regeln, wie im nächsten Abschnitt beschrieben.


## <a name="indentation-in-modules"></a>Einzug in Modulen
Code in einem lokalen Modul muss relativ zum Modul eingezogen werden, Code in einem Modul der obersten Ebene weist jedoch keine eingezogen werden. Namespace-Elemente müssen nicht mit Einzug dargestellt werden.

Die folgenden Codebeispiele veranschaulichen dies.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet3.fs)]
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet4.fs)]

Weitere Informationen finden Sie unter [Module](modules.md).


## <a name="exceptions-to-the-basic-indentation-rules"></a>Ausnahmen von den Einzugsregeln für die grundlegende
Als allgemeine Regel, ist wie im vorherigen Abschnitt beschrieben Code in mehrzeiligen Konstrukten relativ zu den Einzug der ersten Zeile des Konstrukts eingezogen werden muss, dass das Ende des Konstrukts tritt das erste Einrückungsgrenze bestimmt wird. Eine Ausnahme von der Regel Informationen zu den beim Kontexten-End-Konstrukte, wie z. B. die `try...with` Ausdruck, der `if...then...else` Ausdruck und die Verwendung von `and` Syntax zum Deklarieren von wechselseitig rekursive Funktionen oder Typen, bestehen aus mehreren Teilen. Die weiter unten befindlichen Teile, z. B. Einzug `then` und `else` in ein `if...then...else` Ausdruck, auf der gleichen Ebene wie das Token, der den Ausdruck beginnt, aber statt, der angibt, eine End-to-Kontext, den nächsten Teil desselben Kontexts dar. Aus diesem Grund eine `if...then...else` Ausdruck geschrieben werden kann, wie im folgenden Codebeispiel dargestellt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet5.fs)]

Die Ausnahme das Einrückungsende gilt nur für die `then` und `else` Schlüsselwörter. Aus diesem Grund zwar kein Fehler für den Einzug der `then` und `else` darüber hinaus nicht Einzug von Codezeilen in eine `then` Block wird eine Warnung erzeugt. Dies wird in den folgenden Codezeilen veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet6.fs)]
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet7.fs)]

Für Code in eine `else` Block, eine zusätzliche spezielle Regel gilt. Die Warnung im vorherigen Beispiel tritt nur für den Code in der `then` Block nicht auf den Code in der `else` Block. Dadurch können Sie Code schreiben, der für verschiedene Bedingungen am Anfang einer Funktion überprüft werden, ohne dass der Rest des Codes für die Funktion, die möglicherweise in einem `else` Block, um mit Einzug dargestellt werden. Daher können Sie Folgendes schreiben, ohne dass eine Warnung erstellt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet8.fs)]

Eine andere Ausnahme zur Regel, die Kontexte enden, wenn eine Zeile nicht eingezogen wird, soweit Infixoperatoren, z. B. keiner vorherige Zeile ist `+` und `|>`. Zeilen, die mit Infixoperatoren beginnen sind zulässig, um zu beginnen `(1 + oplength)` Spalten vor der normalen Position, ohne dass ein Ende an den Kontext, in dem `oplength` ist die Anzahl der Zeichen, die der Operator bilden. Dies bewirkt, dass das erste Token nach dem Operator an der vorherigen Zeile aus.

Im folgenden Code wird z. B. die `+` Symbol eingezogen zwei Spalten, die kleiner als die vorherige Zeile werden darf.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet9.fs)]

Obwohl Einzug in der Regel erhöht wird, wenn der Schachtelungsebene höher ist, stehen verschiedene Konstrukte in denen der Compiler Sie den Einzug auf eine niedrigere Spaltenposition zurücksetzen kann.

Die Konstrukte, mit denen ein Zurücksetzen der Spaltenposition lauten wie folgt:


- Die Texte der anonyme Funktionen. Im folgenden Code startet der print-Ausdruck an einer Position der Spalte, die auf der linken Seite als desto ist die `fun` Schlüsselwort. Die Zeile muss jedoch nicht gestartet, in eine Spalte auf der linken Seite des Beginns des vorherigen Einzugs (d. h. links neben der `L` in `List`).
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet10.fs)]

- Konstrukte eingeschlossen, durch Klammern oder durch `begin` und `end` in einem `then` oder `else` -Block ein `if...then...else` Ausdruck, sofern der Einzug nicht kleiner als die Spaltenposition des der `if` Schlüsselwort. Diese Ausnahme ermöglicht es, einen Codierungsstil, in dem eine öffnende Klammer oder `begin` wird am Ende einer Zeile nach verwendet `then` oder `else`.


- Texte der Module, Klassen, Schnittstellen und Strukturen, getrennt durch `begin...end`, `{...}`, `class...end`, oder `interface...end`. Dies ermöglicht eine Formatvorlage, die in der das Schlüsselwort Öffnen einer Typdefinition auf derselben Zeile wie der Typname werden kann, ohne das Erzwingen des gesamten Text mehr als das öffnende Schlüsselwort eingezogen werden.
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet13.fs)]


## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)
