---
title: "Kopieren des Wertes des ByRef-Parameters &quot;&lt;Parametername&gt;&quot;wieder in das entsprechende Argument führt zu einer Einschränkung vom Typ&quot;&lt;&quot;Typname1&quot;&gt;&quot; in Typ&quot;&lt;typename2&gt;&quot; | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
dev_langs:
- VB
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 84574006b2e2ccc669fdd83ebfb6eec06b00f041
ms.lasthandoff: 03/13/2017

---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a>Kopieren des Wertes des ByRef-Parameters '&lt;Parametername&gt;'wieder in das entsprechende Argument führt zu einer Einschränkung vom Typ'&lt;"Typname1"&gt;' in Typ'&lt;typename2&gt;'
Eine Prozedur wird mit einem Argument, das in den entsprechenden Parametertyp erweitert wird aufgerufen, und die Konvertierung vom Parameter in das Argument führt zu einer Einschränkung.  
  
 Wenn Sie eine Klasse oder Struktur definieren, können Sie einen oder mehrere Konvertierungsoperatoren zum Konvertieren dieses Klassen- oder Strukturtyps in andere Typen definieren. Sie können auch Operatoren für die umgekehrte Konvertierung definieren, um dieser anderen Typen zurück in den Klassen- oder Strukturtyp zu konvertieren. Wenn Sie die Klasse oder Struktur in einem Prozeduraufruf verwenden [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] können mithilfe dieser Konvertierungsoperatoren den Typ eines Arguments in den Typ des entsprechenden Parameters konvertieren.  
  
 Wenn Sie das Argument übergeben [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] kopiert zuweilen den Argumentwert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben. In diesem Fall gibt die Prozedur [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen den Wert der lokalen Variablen in das Argument im aufrufenden Code kopieren.  
  
 Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich. Wenn die Typen unterschiedlich sind, aber [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen in beide Richtungen konvertieren. Wenn der Typ den Typ Klasse oder Struktur ist [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen sie umwandeln, um sowohl vom anderen Typ. Wenn eine dieser Konvertierungen erweiternde ist, kann die umgekehrte Konvertierung einschränken.  
  
 **Fehler-ID:** BC32053  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie nach Möglichkeit ein aufrufendes Argument vom gleichen Typ wie der Prozedurparameter also [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] muss nicht Konvertierung ausführen.  
  
-   Wenn Sie die Prozedur mit einem Argument aufrufen müssen anderen vom Parametertyp müssen jedoch nicht in das aufrufende Argument kein Wert zurückgegeben, definieren Sie den Parameter als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anstelle von `ByRef`.  
  
-   Wenn in das aufrufende Argument ein Wert zurückgegeben werden sollen, definieren Sie den Operator für die umgekehrte Konvertierung als [Widening](../../../visual-basic/language-reference/modifiers/widening.md), sofern dies möglich.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Prozedurparameter und Argumente](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Übergeben von Argumenten als Wert und als Verweis](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Gewusst wie: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Typumwandlungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
