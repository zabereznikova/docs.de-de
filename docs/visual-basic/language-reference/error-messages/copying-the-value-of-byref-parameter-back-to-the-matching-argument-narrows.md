---
title: Kopieren den Wert der &#39;ByRef&#39; Parameter &#39; &lt;Parametername&gt; &#39; schränkt Sie zurück in das entsprechende Argument vom Typ &#39; &lt;Typname1&gt; &#39; Typ &#39; &lt;Typname2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: 1d35d7abc6f65dd2e09a54e3e4b817741043ae6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591806"
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a>Kopieren den Wert der &#39;ByRef&#39; Parameter &#39; &lt;Parametername&gt; &#39; schränkt Sie zurück in das entsprechende Argument vom Typ &#39; &lt;Typname1&gt; &#39; Typ &#39; &lt;Typname2&gt;&#39;
Eine Prozedur wird aufgerufen, mit der ein Argument, das auf den entsprechenden Parametertyp erweitert, und die Konvertierung aus dem Parameter an das Argument einschränkend.  
  
 Wenn Sie eine Klasse oder Struktur definieren, können Sie einen oder mehrere Konvertierungsoperatoren zum Konvertieren dieses Klassen- oder Strukturtyps in andere Typen definieren. Sie können auch Operatoren für die umgekehrte Konvertierung definieren, um dieser anderen Typen zurück in den Klassen- oder Strukturtyp zu konvertieren. Wenn Sie den Klasse oder Struktur in einem Prozeduraufruf verwenden, können Visual Basic dieser Konvertierungsoperatoren den Typ eines Arguments in den Typ des entsprechenden Parameters konvertieren.  
  
 Wenn das Argument zu übergeben [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), kopiert Visual Basic zuweilen den Argumentwert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben. In diesem Fall müssen Visual Basic klicken Sie dann, wenn die Prozedur zurückgibt, den Wert den lokalen Variablen zurück in das Argument im aufrufenden Code kopieren.  
  
 Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich. Aber wenn die Typen unterschiedlich sind, müssen in beide Richtungen Visual Basic konvertieren. Wenn einer der Typen der Klasse oder Struktur-Typ ist, muss Visual Basic es sowohl aus dem anderen Typ konvertieren. Wenn einer dieser Konvertierungen eine erweiternde Konvertierung handelt, kann die umgekehrte Konvertierung einschränkend.  
  
 **Fehler-ID:** BC32053  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie nach Möglichkeit ein aufrufendes Argument desselben Typs wie der Prozedurparameter ein, damit Visual Basic nicht Konvertierung ausführen muss.  
  
-   Wenn Sie die Prozedur mit einem Argument aufrufen müssen, Typ sich vom Parametertyp unterscheidet, jedoch müssen nicht in das aufrufende Argument einen Wert zurückgeben, definieren Sie den Parameter als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anstelle von `ByRef`.  
  
-   Wenn einen Wert in das aufrufende Argument zurückgegeben werden müssen, definieren Sie den Operator für die umgekehrte Konvertierung als [Widening](../../../visual-basic/language-reference/modifiers/widening.md), sofern dies möglich.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Parameter und Argumente von Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Übergeben von Argumenten als Wert und als Verweis](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Gewusst wie: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Konvertierungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
