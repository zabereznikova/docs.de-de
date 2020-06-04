---
title: Das Zurückkopieren des ByRef-Parameters "<parametername>" in das entsprechende Argument führt zu einer Einschränkung von Typ "<typename1>" auf Typ "<typename2>".
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: bac5f9a88df719bc64a8b0541f65e5912275866e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409750"
---
# <a name="copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a>Das Zurückkopieren des ByRef-Parameters "\<parametername>" in das entsprechende Argument führt zu einer Einschränkung von Typ "\<typename1>" auf Typ "\<typename2>".
Eine Prozedur wird mit einem Argument aufgerufen, das zum entsprechenden Parametertyp erweitert wird, und die Konvertierung des-Parameters in das-Argument wird einschränkend.  
  
 Wenn Sie eine Klasse oder Struktur definieren, können Sie einen oder mehrere Konvertierungsoperatoren zum Konvertieren dieses Klassen- oder Strukturtyps in andere Typen definieren. Sie können auch Operatoren für die umgekehrte Konvertierung definieren, um dieser anderen Typen zurück in den Klassen- oder Strukturtyp zu konvertieren. Wenn Sie den Klassen-oder Strukturtyp in einem Prozedur aufrufstyp verwenden, können Visual Basic Diese Konvertierungs Operatoren verwenden, um den Typ eines Arguments in den Typ des entsprechenden Parameters zu konvertieren.  
  
 Wenn Sie das [ByRef](../modifiers/byref.md)-Argument übergeben, kopiert Visual Basic manchmal den Argument Wert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben. In diesem Fall muss Visual Basic den Wert der lokalen Variablen zurück in das Argument im aufrufenden Code kopieren, wenn die Prozedur zurückgibt.  
  
 Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich. Wenn die Typen jedoch unterschiedlich sind, müssen Visual Basic in beide Richtungen konvertieren. Wenn einer der Typen Ihr Klassen-oder Strukturtyp ist, muss Visual Basic ihn sowohl in den als auch aus dem anderen Typ konvertieren. Wenn eine dieser Konvertierungen erweitert wird, kann die umgekehrte Konvertierung einschränkend sein.  
  
 **Fehler-ID:** BC32053  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden Sie nach Möglichkeit ein Aufruf Endes Argument desselben Typs wie der Prozedur Parameter, sodass Visual Basic keine Konvertierung durchführen muss.  
  
- Wenn Sie die Prozedur mit einem Argument aufrufen müssen, dessen Typ sich vom Parametertyp unterscheidet, jedoch kein Wert in das aufrufende Argument zurückgegeben werden muss, definieren Sie den Parameter als [ByVal](../modifiers/byval.md) anstelle von `ByRef`.  
  
- Wenn ein Wert in das aufrufende Argument zurückgegeben werden muss, definieren Sie den Operator für die umgekehrte Konvertierung als [Erweiterung](../modifiers/widening.md), wenn möglich.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweisen](../../programming-guide/language-features/procedures/index.md)
- [Parameter und Argumente von Prozeduren](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Übergeben von Argumenten als Wert und als Verweis](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Operatorprozeduren](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Operator Statement](../statements/operator-statement.md)
- [Vorgehensweise: Definieren eines Operators](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Typkonvertierung in Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
