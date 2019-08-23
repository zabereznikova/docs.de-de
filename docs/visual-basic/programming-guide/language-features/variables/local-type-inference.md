---
title: Lokaler Typrückschluss (Visual Basic)
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
ms.openlocfilehash: 59559f8775a5fd66a567897b009272df1727b1e8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69953332"
---
# <a name="local-type-inference-visual-basic"></a>Lokaler Typrückschluss (Visual Basic)
Der Visual Basic-Compiler verwendet den Typrückschluss, um die Datentypen von lokalen Variablen `As` zu bestimmen, die ohne-Klausel deklariert werden. Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungs Ausdrucks ab. Dadurch können Sie Variablen deklarieren, ohne explizit einen Typ anzugeben, wie im folgenden Beispiel gezeigt. Aufgrund der Deklarationen werden sowohl `num1` als auch `num2` als ganze Zahlen stark typisiert.  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
 
> [!NOTE]
> Wenn Sie im vorherigen Beispiel `num2` nicht `Integer`als typisieren möchten, können Sie einen anderen Typ mithilfe einer Deklaration wie `Dim num3 As Object = 3` oder `Dim num4 As Double = 3`angeben.  

> [!NOTE]
> Der Typrückschluss kann nur für nicht statische lokale Variablen verwendet werden. Sie kann nicht verwendet werden, um den Typ der Klassen Felder, Eigenschaften oder Funktionen zu bestimmen.
 
 Der lokale Typrückschluss gilt für die Prozedur Ebene. Sie kann nicht zum Deklarieren von Variablen auf Modulebene verwendet werden (innerhalb einer Klasse, Struktur, eines Moduls oder einer Schnittstelle, aber nicht innerhalb einer Prozedur oder eines Blocks). Wenn `num2` im vorherigen Beispiel ein Feld einer Klasse statt einer lokalen Variablen in einer Prozedur wäre, würde die Deklaration einen Fehler mit `Option Strict` on verursachen `Object` und als mit `Option Strict` off klassifiziert `num2` werden. Ebenso gilt der lokale Typrückschluss nicht für Variablen auf Prozedur Ebene, `Static`die als deklariert wurden.  
  
## <a name="type-inference-vs-late-binding"></a>Typrückschluss im Vergleich zu Späte Bindung  
 Code, der den Typrückschluss verwendet, ähnelt dem Code, der die späte Bindung verwendet. Der Typrückschluss gibt jedoch die Variable stark ein, anstatt Sie `Object`als zu belassen. Der Compiler verwendet den Initialisierer einer Variablen, um den Typ der Variable zur Kompilierzeit zu bestimmen, um früh gebundenen Code zu erstellen. Im vorherigen Beispiel `num2`wird, wie `num1`, als `Integer`typisiert.  
  
 Das Verhalten früh gebundener Variablen unterscheidet sich von der von spät gebundenen Variablen, für die der Typ nur zur Laufzeit bekannt ist. Wenn Sie den Typ früh wissen, kann der Compiler Probleme vor der Ausführung erkennen, Speicher exakt zuordnen und andere Optimierungen durchführen. Die frühe Bindung ermöglicht außerdem der Visual Basic integrierten Entwicklungsumgebung (Integrated Development Environment, IDE), IntelliSense-Hilfe zu den Membern eines Objekts bereitzustellen. Die frühe Bindung wird auch für die Leistung bevorzugt. Dies liegt daran, dass alle in einer spät gebundenen Variablen gespeicherten Daten als Typ `Object`umschließt werden müssen und der Zugriff auf Member des Typs zur Laufzeit das Programm verlangsamt.  
  
## <a name="examples"></a>Beispiele  
 Der Typrückschluss tritt auf, wenn eine lokale Variable `As` ohne eine-Klausel deklariert und initialisiert wird. Der Compiler verwendet den Typ des zugewiesenen anfangs Werts als Typ der Variablen. Jede der folgenden Codezeilen deklariert z. b. eine Variable vom Typ `String`.  
  
 [!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]  
  
 Der folgende Code veranschaulicht zwei äquivalente Möglichkeiten, ein Array von ganzen Zahlen zu erstellen.  
  
 [!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]  
  
 Es ist praktisch, mit dem Typrückschluss den Typ einer Schleifen Steuerungsvariablen zu bestimmen. Im folgenden Code geht der Compiler davon aus, dass `number` ein `Integer` ist, `someNumbers2` da aus dem vorherigen Beispiel ein Array aus ganzen Zahlen ist.  
  
 [!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]  
  
 Der lokale Typrückschluss kann in `Using` -Anweisungen verwendet werden, um den Typ des Ressourcen namensfest zulegen, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]  
  
 Der Typ einer Variablen kann auch von den Rückgabe Werten von Functions abgeleitet werden, wie im folgenden Beispiel veranschaulicht. Und sind `pList2` Arrays von-Prozessen, `Process.GetProcesses` da ein Array von-Prozessen zurückgibt. `pList1`  
  
 [!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]  
  
## <a name="option-infer"></a>Option Infer  
 `Option Infer`ermöglicht Ihnen, anzugeben, ob der lokale Typrückschluss in einer bestimmten Datei zulässig ist. Wenn Sie oder zum Blockieren der Option aktivieren möchten, geben Sie eine der folgenden Anweisungen am Anfang der Datei ein.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 Wenn Sie im Code keinen Wert für `Option Infer` angeben, ist `Option Infer On`der Compilerstandardwert. 
  
 Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.  
  
 Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Kompilierungs Seite, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Siehe auch

- [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [For Each...Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [For...Next-Anweisung](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
