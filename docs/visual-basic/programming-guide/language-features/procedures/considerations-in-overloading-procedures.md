---
title: "Überlegungen zur prozedurüberladung (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- signatures, ParamArray arguments
- ParamArray keyword, parameter arrays
- ParamArray keyword, arguments and signatures
- function overloading, implicit overloads for ParamArray
- ParamArray keyword, signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures, overloading
- parameters, lists
- function overloading, typeless programming
- typeless programming
- function overloading, restrictions
- arguments [Visual Basic], optional
- optional arguments, overloading
- signatures, procedure
- parameter lists
- parameter arrays, overloading arguments
- Visual Basic code, parameter lists
- procedure overloading, considerations
- Option Explicit statement
- restrictions, overloading procedures
- procedures, parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: 26
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
ms.openlocfilehash: aa20cf367fba157f88afd861a4799540dcdecde1
ms.lasthandoff: 03/13/2017

---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Überlegungen zur Prozedurüberladung (Visual Basic)
Wenn Sie eine Prozedur überladen, müssen Sie ein anderes verwenden *Signatur* für jede überladene Version. Dies bedeutet normalerweise, dass jede Version eine andere Parameterliste angeben muss. Weitere Informationen finden Sie unter "Andere Signatur" in [Prozedurüberladung](./procedure-overloading.md).  
  
 Sie können überladen eine `Function` Prozedur mit einem `Sub` Verfahren und umgekehrt, sofern sie unterschiedliche Signaturen besitzen. Zwei Überladungen können nicht unterscheiden sich nur darin, dass eine verfügt über einen Rückgabewert und die andere nicht.  
  
 Sie können die gleiche Weise, die Sie überladen eine Prozedur, eine Eigenschaft überladen und mit den gleichen Einschränkungen. Aber Sie können nicht überladen einer Prozedur mit einer Eigenschaft (oder umgekehrt).  
  
## <a name="alternatives-to-overloaded-versions"></a>Alternativen zu überladenen Versionen  
 Sie müssen manchmal Alternativen zu überladenen Versionen, insbesondere wenn das Vorhandensein von Argumenten optional ist oder deren Anzahl Variable ist.  
  
 Denken Sie daran, die optionale Argumente nicht unbedingt von allen Sprachen unterstützt werden und Parameterarrays sind beschränkt auf [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Wenn Sie eine Prozedur schreiben, die wahrscheinlich in einem der anderen Sprachen geschriebenen Code aufgerufen werden, überladene bieten Versionen die größte Flexibilität.  
  
### <a name="overloads-and-optional-arguments"></a>Overloads und optionale Argumente  
 Wenn der aufrufende Code kann optional angeben oder ein oder mehrere Argumente auslassen, können Sie mehrere überladene Versionen definieren oder optionale Parameter verwenden.  
  
#### <a name="when-to-use-overloaded-versions"></a>Verwendung von überladenen Versionen  
 Sie können in Betracht ziehen, definieren eine Reihe von überladenen Versionen in den folgenden Fällen:  
  
-   Die Logik im Code Prozedur ist erheblich variieren, je nachdem, ob der aufrufende Code ein optionales Argument bereitstellt.  
  
-   Prozedurcode kann nicht zuverlässig testen Sie, ob der aufrufende Code ein optionales Argument angegeben wurde. Dies ist der Fall, z. B. ist es keinen möglichen Kandidaten für einen Standardwert, der der Aufrufcode nicht zu erwarten angeben.  
  
#### <a name="when-to-use-optional-parameters"></a>Optionale Parameter verwenden.  
 Sie können eine oder mehrere optionale Parameter in den folgenden Fällen bevorzugen:  
  
-   Die einzige erforderliche Aktion, wenn der aufrufende Code ein optionale Argument nicht angegeben wird, ist den Parameter einen Standardwert festlegen. In diesem Fall der Code weniger kompliziert sein, wenn Sie eine einzelne Version mit einem oder mehreren definieren `Optional` Parameter.  
  
 Weitere Informationen finden Sie unter [optionale Parameter](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Overloads und ParamArrays  
 Wenn der aufrufende Code eine Variable Anzahl von Argumenten übergeben kann, können Sie mehrere überladene Versionen definieren oder ein Parameterarray verwenden.  
  
#### <a name="when-to-use-overloaded-versions"></a>Verwendung von überladenen Versionen  
 Sie können in Betracht ziehen, definieren eine Reihe von überladenen Versionen in den folgenden Fällen:  
  
-   Sie wissen, dass der aufrufende Code mehr als eine kleine Anzahl von Werten nie an den Parameterarray übergibt.  
  
-   Die Logik im Code Prozedur ist erheblich variieren, je nachdem wie viele Werte, die der aufrufende Code übergeben.  
  
-   Der aufrufende Code kann es sich um Werte mit unterschiedlichen Datentypen übergeben.  
  
#### <a name="when-to-use-a-parameter-array"></a>Verwenden Sie ein Parameterarray  
 Werden Sie besser von bedient ein `ParamArray` Parameter in den folgenden Fällen:  
  
-   Sie können nicht für die Vorhersage wie viele Werte der Aufrufcode an den Parameterarray übergeben kann, und dies möglicherweise eine große Anzahl.  
  
-   Logik der Prozedur bietet sich für alle Werte, die der aufrufende Code im Wesentlichen die gleichen Vorgänge für jeden Wert ausführen übergibt, durchlaufen.  
  
 Weitere Informationen finden Sie unter [Parameterarrays](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Implizite Überladungen für optionale Parameter  
 Eine Prozedur mit einem [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) Parameter entspricht zwei überladenen Prozeduren, einer mit dem optionalen Parameter und einer ohne. Diese Prozedur kann nicht mit einer Liste von Parametern für eine der folgenden überladen werden. Die folgenden Deklarationen verdeutlichen dies.  
  
 [!code-vb[VbVbcnProcedures&#58;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&60;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures&#61;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 Eine Prozedur mit mehreren optionalen Parameter ist es eine Gruppe implizite Überladungen, die Logik, die im vorherigen Beispiel ähnelt angekommen.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Implizite Überladungen für ParamArray-Parameter  
 Der Compiler betrachtet eine Prozedur mit einem [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Parameter haben eine unendliche Anzahl von Überladungen, unterscheiden sich voneinander in der aufrufende Code wie folgt an den Parameterarray übergibt:  
  
-   Eine Überladung für den Fall der aufrufende Code kein Argument übergibt die`ParamArray`  
  
-   Eine Überladung für Wenn der aufrufende Code ein eindimensionales Array von stellt die `ParamArray` Elementtyp  
  
-   Für jede positive ganze Zahl eine Überladung für der aufrufende Code diese Anzahl von Argumenten, die jeweils von liefert die `ParamArray` Elementtyp  
  
 Die folgenden Deklarationen veranschaulichen diese implizite Überladungen.  
  
 [!code-vb[VbVbcnProcedures&#68;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures&#70;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 Sie können nicht eine solche Prozedur mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert. Sie können jedoch die Signaturen von anderen implizite Überladungen. Die folgenden Deklarationen verdeutlichen dies.  
  
 [!code-vb[VbVbcnProcedures&#71;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Programmierung ohne Datentypen als Alternative zur Überladung  
 Wenn den aufrufenden Code unterschiedliche Datentypen an einen Parameter übergeben werden soll, ist eine alternative Methode Programmierung ohne Datentypen. Lassen sich die Schalter für die Typprüfung `Off` entweder mit der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) oder [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) (Compileroption). Dann müssen Sie keinen Datentyp des Parameters zu deklarieren. Dieser Ansatz hat jedoch die folgenden Nachteile im Vergleich zum Überladen:  
  
-   Programmierung ohne Datentypen ergibt weniger effizienten Ausführungscode.  
  
-   Die Prozedur muss für jeden Datentyp testen, dessen Übergabe.  
  
-   Der Compiler kann nicht auf einen Fehler signalisieren, wenn der aufrufende Code einen Datentyp übergibt, den die Prozedur nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)   
 [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)   
 [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)   
 [Gewusst wie: überladen eine Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Gewusst wie: überladen eine Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Überladungsauflösung](./overload-resolution.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
