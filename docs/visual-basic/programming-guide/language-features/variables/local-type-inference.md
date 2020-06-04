---
title: Lokaler Typrückschluss
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: 3979396d32aa5d3b853aa087d43f70d5987e510b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410398"
---
# <a name="local-type-inference-visual-basic"></a>Lokaler Typrückschluss (Visual Basic)

Der Visual Basic-Compiler verwendet den *Typrückschluss* , um die Datentypen von lokalen Variablen zu bestimmen, die ohne-Klausel deklariert werden `As` . Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungs Ausdrucks ab. Dadurch können Sie Variablen deklarieren, ohne explizit einen Typ anzugeben, wie im folgenden Beispiel gezeigt. Aufgrund der Deklarationen werden sowohl als `num1` auch `num2` als ganze Zahlen stark typisiert.

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> Wenn Sie `num2` im vorherigen Beispiel nicht als typisieren möchten `Integer` , können Sie einen anderen Typ mithilfe einer Deklaration wie `Dim num3 As Object = 3` oder angeben `Dim num4 As Double = 3` .

> [!NOTE]
> Der Typrückschluss kann nur für nicht statische lokale Variablen verwendet werden. Sie kann nicht verwendet werden, um den Typ der Klassen Felder, Eigenschaften oder Funktionen zu bestimmen.

Der lokale Typrückschluss gilt für die Prozedur Ebene. Sie kann nicht zum Deklarieren von Variablen auf Modulebene verwendet werden (innerhalb einer Klasse, Struktur, eines Moduls oder einer Schnittstelle, aber nicht innerhalb einer Prozedur oder eines Blocks). Wenn `num2` im vorherigen Beispiel ein Feld einer Klasse statt einer lokalen Variablen in einer Prozedur wäre, würde die Deklaration einen Fehler mit `Option Strict` on verursachen und `num2` als `Object` mit Off klassifiziert werden `Option Strict` . Ebenso gilt der lokale Typrückschluss nicht für Variablen auf Prozedur Ebene, die als deklariert wurden `Static` .

## <a name="type-inference-vs-late-binding"></a>Typrückschluss und späte Bindung

Code, der den Typrückschluss verwendet, ähnelt dem Code, der die späte Bindung verwendet. Der Typrückschluss gibt jedoch die Variable stark ein, anstatt Sie als zu belassen `Object` . Der Compiler verwendet den Initialisierer einer Variablen, um den Typ der Variable zur Kompilierzeit zu bestimmen, um früh gebundenen Code zu erstellen. Im vorherigen Beispiel wird, `num2` wie, `num1` als typisiert `Integer` .

Das Verhalten früh gebundener Variablen unterscheidet sich von der von spät gebundenen Variablen, für die der Typ nur zur Laufzeit bekannt ist. Wenn Sie den Typ früh wissen, kann der Compiler Probleme vor der Ausführung erkennen, Speicher exakt zuordnen und andere Optimierungen durchführen. Die frühe Bindung ermöglicht außerdem der Visual Basic integrierten Entwicklungsumgebung (Integrated Development Environment, IDE), IntelliSense-Hilfe zu den Membern eines Objekts bereitzustellen. Die frühe Bindung wird auch für die Leistung bevorzugt. Dies liegt daran, dass alle in einer spät gebundenen Variablen gespeicherten Daten als Typ umschließt werden müssen `Object` und der Zugriff auf Member des Typs zur Laufzeit das Programm verlangsamt.

## <a name="examples"></a>Beispiele

Der Typrückschluss tritt auf, wenn eine lokale Variable ohne eine `As` -Klausel deklariert und initialisiert wird. Der Compiler verwendet den Typ des zugewiesenen anfangs Werts als Typ der Variablen. Jede der folgenden Codezeilen deklariert z. b. eine Variable vom Typ `String` .

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

Der folgende Code veranschaulicht zwei äquivalente Möglichkeiten, ein Array von ganzen Zahlen zu erstellen.

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

Es ist praktisch, mit dem Typrückschluss den Typ einer Schleifen Steuerungsvariablen zu bestimmen. Im folgenden Code geht der Compiler davon aus, dass `number` ein ist, `Integer` da `someNumbers2` aus dem vorherigen Beispiel ein Array aus ganzen Zahlen ist.

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

Der lokale Typrückschluss kann in-Anweisungen verwendet werden `Using` , um den Typ des Ressourcen namensfest zulegen, wie im folgenden Beispiel veranschaulicht.

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

Der Typ einer Variablen kann auch von den Rückgabe Werten von Functions abgeleitet werden, wie im folgenden Beispiel veranschaulicht. `pList1`Und `pList2` sind Arrays von-Prozessen, da `Process.GetProcesses` ein Array von-Prozessen zurückgibt.

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a>Option Infer

`Option Infer`ermöglicht Ihnen, anzugeben, ob der lokale Typrückschluss in einer bestimmten Datei zulässig ist. Wenn Sie oder zum Blockieren der Option aktivieren möchten, geben Sie eine der folgenden Anweisungen am Anfang der Datei ein.

`Option Infer On`

`Option Infer Off`

Wenn Sie im Code keinen Wert für angeben `Option Infer` , ist der Compilerstandardwert `Option Infer On` .

Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.

Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../language-reference/statements/option-infer-statement.md) und [Kompilierungs Seite, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).

## <a name="see-also"></a>Weitere Informationen

- [Anonyme Typen](../objects-and-classes/anonymous-types.md)
- [Frühe und späte Bindung](../early-late-binding/index.md)
- [For Each...Next-Anweisung](../../../language-reference/statements/for-each-next-statement.md)
- [For...Next-Anweisung](../../../language-reference/statements/for-next-statement.md)
- [Option Infer-Anweisung](../../../language-reference/statements/option-infer-statement.md)
- [-optioninfer](../../../reference/command-line-compiler/optioninfer.md)
- [Einführung in LINQ in Visual Basic](../linq/introduction-to-linq.md)
