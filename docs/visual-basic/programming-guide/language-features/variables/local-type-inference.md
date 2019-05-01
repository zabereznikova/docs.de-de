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
ms.openlocfilehash: e6214938262b987a1bae4a9ca1d5c945f8b7fe6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052585"
---
# <a name="local-type-inference-visual-basic"></a>Lokaler Typrückschluss (Visual Basic)
Visual Basic-Compiler verwendet *Typrückschluss* um zu bestimmen, die die Datentypen für lokale Variablen deklariert, ohne eine `As` Klausel. Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungsausdrucks ab. Dadurch können Sie Variablen zu deklarieren, ohne explizit einen Typ, wie im folgenden Beispiel gezeigt. Als Ergebnis die Deklarationen sowohl `num1` und `num2` sind stark typisiert, als ganze Zahlen.  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
 
> [!NOTE]
>  Wenn Sie nicht möchten `num2` im vorherigen Beispiel als typisiert wird ein `Integer`, Sie können einen anderen Typ angeben, indem Sie mit einer Deklaration wie `Dim num3 As Object = 3` oder `Dim num4 As Double = 3`.  

> [!NOTE]
>  Typrückschluss kann nur für nicht statische lokale Variablen verwendet werden. Es kann nicht verwendet werden, um den Typ der Klassenfelder, Eigenschaften oder Funktionen zu bestimmen.
 
 Lokaler Typrückschluss gilt auf Prozedurebene. Es kann nicht zum Deklarieren von Variablen auf Modulebene (innerhalb einer Klasse, Struktur, Modul oder Schnittstelle jedoch nicht innerhalb einer Prozedur oder einem Block) verwendet werden. Wenn `num2` im vorherigen Beispiel wurden ein Feld einer Klasse anstelle der lokalen Variablen in einer Prozedur, die Deklaration würde einen Fehler mit `Option Strict` , und klassifizieren `num2` als ein `Object` mit `Option Strict` deaktiviert. Auf ähnliche Weise lokaler Typrückschluss gilt nicht für Ebene Prozedur-Variablen, die als `Static`.  
  
## <a name="type-inference-vs-late-binding"></a>Typrückschluss und Späte Bindung  
 Code, der Typrückschluss verwendet ähnelt, Code, der auf die späte Bindung verwendet wird. Typrückschluss Typen jedoch stark der Variablen statt als bleiben `Object`. Der Compiler verwendet eine Variable des Initialisierers um den Wert der Variablen zum Zeitpunkt der Kompilierung zum Erzeugen von Code mit früher Bindung zu ermitteln. Im vorherigen Beispiel `num2`, z. B. `num1`, typisiert ist, als ein `Integer`.  
  
 Das Verhalten der früh gebundene Variablen unterscheidet sich von spät gebundenen Variablen, für die der Typ nur zur Laufzeit bekannt ist. Die den Typ einem frühen Zeitpunkt kann der Compiler Probleme vor der Ausführung zu identifizieren, Speicher genau zuordnen und Durchführen weiterer Optimierungen. Früher Bindung ermöglicht auch die integrierte Entwicklungsumgebung (IDE) zum Bereitstellen von IntelliSense-Hilfe zu den Elementen eines Objekts von Visual Basic. Früher Bindung wird auch bevorzugt, für die Leistung. Dies ist, da alle Daten in eine spät gebundene Variable müssen, als Typ eingebunden sein `Object`, und das Zugreifen auf Member des Typs zur Laufzeit wird das Programm, die langsamer.  
  
## <a name="examples"></a>Beispiele  
 Typrückschluss tritt auf, wenn eine lokale Variable, ohne deklariert wird eine `As` Klausel und initialisiert. Der Compiler verwendet den Typ des ersten zugewiesenen Werts als Typ der Variablen an. Die folgenden Zeilen des Codes deklariert beispielsweise eine Variable vom Typ `String`.  
  
 [!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]  
  
 Der folgende Code veranschaulicht zwei gleichwertige Möglichkeiten zum Erstellen eines Arrays von ganzen Zahlen.  
  
 [!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]  
  
 Es ist sinnvoll, den Typrückschluss verwenden, um den Typ des eine Schleifensteuerungsvariable zu bestimmen. In den folgenden Code, der Compiler leitet ab, die `number` ist ein `Integer` da `someNumbers2` aus dem vorherigen Beispiel wird ein Array von ganzen Zahlen.  
  
 [!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]  
  
 Lokaler Typrückschluss verwendet werden kann, `Using` Anweisungen zu, um den Typ des Ressourcennamens, herzustellen, wie das folgende Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]  
  
 Der Typ einer Variablen kann auch von die Rückgabewerte von Funktionen, die abgeleitet werden, wie das folgende Beispiel veranschaulicht. Beide `pList1` und `pList2` werden Arrays von Prozessen, da `Process.GetProcesses` gibt ein Array von Prozessen.  
  
 [!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]  
  
## <a name="option-infer"></a>Option Infer-  
 `Option Infer` ermöglicht, die Sie angeben, ob der lokale Typrückschluss in einer bestimmten Datei zulässig ist. Aktivieren oder blockieren die Option, geben Sie einen der folgenden Anweisungen am Anfang der Datei ein.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 Wenn Sie einen Wert für nicht angeben `Option Infer` in Ihrem Code ist die Standardeinstellung des Compilers `Option Infer On`. Für Projekte von aktualisierten [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] oder früher, die Standardeinstellung des Compilers ist `Option Infer Off`.  
  
 Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.  
  
 Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Seite "Kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Siehe auch

- [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [For Each...Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [For...Next-Anweisung](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
