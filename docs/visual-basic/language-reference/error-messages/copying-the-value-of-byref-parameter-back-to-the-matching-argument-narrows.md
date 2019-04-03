---
title: Das Zurückkopieren des ByRef-Parameters "<parametername>" in das entsprechende Argument führt zu einer Einschränkung von Typ "<typename1>" auf Typ "<typename2>".
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: fa8607bf72dfb344048ec82514182dcb6810274d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817161"
---
# <a name="copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a>Zurückkopieren des ByRef-Parameters '\<Parametername >' zurück in das entsprechende Argument führt zu einer Einschränkung vom Typ "\<Typname1 >' in den Typ"\<Typname2 >'
Eine Prozedur wird aufgerufen, mit der ein Argument, das den entsprechenden Typ erweitert werden kann, und die Konvertierung aus dem Parameter mit dem Argument einschränkend.  
  
 Wenn Sie eine Klasse oder Struktur definieren, können Sie einen oder mehrere Konvertierungsoperatoren zum Konvertieren dieses Klassen- oder Strukturtyps in andere Typen definieren. Sie können auch Operatoren für die umgekehrte Konvertierung definieren, um dieser anderen Typen zurück in den Klassen- oder Strukturtyp zu konvertieren. Wenn Sie den Typ Klasse oder Struktur in einem Prozeduraufruf verwenden, kann Visual Basic diese Konvertierungsoperatoren verwenden, um den Typ eines Arguments in den Typ des entsprechenden Parameters konvertieren.  
  
 Wenn Sie das Argument übergeben [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), kopiert Visual Basic zuweilen den Argumentwert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben. In diesem Fall müssen Visual Basic klicken Sie dann die Prozedur gibt den Wert den lokalen Variablen zurück in das Argument im aufrufenden Code kopieren.  
  
 Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich. Aber wenn die Typen unterschiedlich sind, müssen in beide Richtungen Visual Basic konvertieren. Wenn einer der Typen der Klasse oder Struktur-Typ ist, muss Visual Basic es sowohl vom anderen Typ konvertieren. Wenn eine dieser Konvertierungen eine erweiternde Konvertierung handelt, kann die umgekehrte Konvertierung einschränken.  
  
 **Fehler-ID:** BC32053  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie möglichst ein aufrufendes Argument desselben Typs wie der Prozedurparameter ein, damit Visual Basic nicht Konvertierung vornehmen muss.  
  
-   Wenn Sie die Prozedur mit einem Argument aufrufen müssen, dessen Typ sich vom Parametertyp unterscheidet, jedoch kein Wert in das aufrufende Argument zurückgegeben werden muss, definieren Sie den Parameter als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anstelle von `ByRef`.  
  
-   Wenn ein Wert in das aufrufende Argument zurückgegeben werden sollen, definieren Sie den Operator für die umgekehrte Konvertierung als [Widening](../../../visual-basic/language-reference/modifiers/widening.md), sofern möglich.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Parameter und Argumente von Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Übergeben von Argumenten als Wert und als Verweis](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Vorgehensweise: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Typkonvertierung in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
