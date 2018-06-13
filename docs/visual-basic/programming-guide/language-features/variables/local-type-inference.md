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
ms.openlocfilehash: b33b8b2d17c240e380377528d4f5d2f511381a7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655322"
---
# <a name="local-type-inference-visual-basic"></a>Lokaler Typrückschluss (Visual Basic)
Visual Basic-Compiler verwendet *typableitung* um zu bestimmen, die die Datentypen für lokale Variablen deklariert, ohne eine `As` Klausel. Der Compiler leitet den Datentyp der Variablen vom Typ des Initialisierungsausdrucks ab. Dadurch können Sie Variablen zu deklarieren, ohne explizit einen Typ anzugeben, wie im folgenden Beispiel gezeigt. Als Ergebnis die Deklarationen sowohl `num1` und `num2` sind stark typisiert als ganze Zahlen.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]  
 
> [!NOTE]
>  Wenn Sie nicht wünschen `num2` im vorherigen Beispiel als typisiertes ein `Integer`, Sie können einen anderen Typ angeben, indem Sie mit einer Deklaration wie `Dim num3 As Object = 3` oder `Dim num4 As Double = 3`.  

> [!NOTE]
>  Typrückschluss kann nur für nicht statische lokale Variablen verwendet werden. Es kann nicht verwendet werden, um den Typ der Klassenfelder, Eigenschaften oder Funktionen zu ermitteln.
 
 Lokaler Typrückschluss ist auf Prozedurebene gültig. Es kann nicht zum Deklarieren von Variablen auf Modulebene (innerhalb einer Klasse, Struktur, Modul oder Schnittstelle jedoch nicht innerhalb einer Prozedur oder Block) verwendet werden. Wenn `num2` im vorherigen Beispiel wurden ein Feld einer Klasse statt einer lokalen Variablen in einer Prozedur, die Deklaration würde dazu führen, dass einen Fehler mit `Option Strict` auf, und klassifizieren `num2` als ein `Object` mit `Option Strict` deaktiviert. Auf ähnliche Weise, lokaler Typrückschluss gilt nicht für Ebene Prozedur-Variablen, die als `Static`.  
  
## <a name="type-inference-vs-late-binding"></a>Typrückschluss und Späte Bindung  
 Code, der Typrückschluss verwendet ähnelt Code, der auf die späte Bindung basiert. Typrückschluss Typen jedoch stark Variablen statt als verlassen `Object`. Der Compiler verwendet eine Variable Initialisierer bestimmt den Typ der Variablen zum Zeitpunkt der Kompilierung zu früh gebundene Code zu erzeugen. Im vorherigen Beispiel `num2`, z. B. `num1`, als typisiert ist, eine `Integer`.  
  
 Das Verhalten von früh gebundene Variablen unterscheidet sich von dem von spät gebundenen Variablen, für die der Typ nur zur Laufzeit bekannt ist. Frühes der Typ den Compiler Probleme vor der Ausführung zu identifizieren, Speicher genau und Durchführen weiterer Optimierungen. Frühes Binden kann auch die integrierte Visual Basic-Entwicklungsumgebung (IDE), um IntelliSense-Hilfe zu den Elementen eines Objekts bereitzustellen. Frühe Bindung wird auch für Leistung bevorzugt. Dies ist, da alle in einer spät gebundenen Variablen gespeicherte Daten als Typ eingebunden sein müssen `Object`, und Zugreifen auf Member des Typs zur Laufzeit stellt das Programm langsamer.  
  
## <a name="examples"></a>Beispiele  
 Typrückschluss tritt auf, wenn eine lokale Variable, ohne deklariert wird eine `As` Klausel und initialisiert. Der Compiler verwendet den Typ des zugewiesenen Anfangswerts als Typ der Variablen an. Jede der folgenden Codezeilen deklariert z. B. eine Variable vom Typ `String`.  
  
 [!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]  
  
 Der folgende Code zeigt zwei äquivalente Verfahren, um ein Array von ganzen Zahlen zu erstellen.  
  
 [!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]  
  
 Es ist sinnvoll, den Typrückschluss um den Typ des eine Schleifensteuerungsvariable zu bestimmen. Im folgenden Code leitet der Compiler, die `number` ist ein `Integer` da `someNumbers2` aus dem vorherigen Beispiel wird ein Array von Ganzzahlen.  
  
 [!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]  
  
 Lokaler Typrückschluss in verwendet werden kann `Using` Anweisungen den Typ des Ressourcennamens, herstellen, wie im folgende Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]  
  
 Der Typ einer Variablen kann auch von die Rückgabewerte von Funktionen, abgeleitet werden, wie im folgende Beispiel veranschaulicht. Beide `pList1` und `pList2` werden Arrays von Prozessen, da `Process.GetProcesses` gibt ein Array von Prozessen.  
  
 [!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]  
  
## <a name="option-infer"></a>Option Infer  
 `Option Infer` ermöglicht, die Sie angeben, ob der lokale Typrückschluss in einer bestimmten Datei zulässig ist. Aktivieren oder die Option zu blockieren, geben Sie einen der folgenden Anweisungen am Anfang der Datei ein.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 Wenn Sie einen Wert für nicht angeben `Option Infer` in Ihrem Code ist die Standardeinstellung des Compilers `Option Infer On`. Für ein Upgrade von Projekten von [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] oder früher, die Standardeinstellung des Compilers ist `Option Infer Off`.  
  
 Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.  
  
 Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Siehe auch  
 [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [For Each...Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next-Anweisung](../../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
