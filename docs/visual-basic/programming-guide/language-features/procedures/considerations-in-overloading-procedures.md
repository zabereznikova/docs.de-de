---
title: Überlegungen zur Prozedurüberladung (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: e1768d0ac03cb6730c4337d7476ae163e75adfd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654329"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Überlegungen zur Prozedurüberladung (Visual Basic)
Wenn Sie eine Prozedur zu überladen, müssen Sie ein anderes verwenden *Signatur* für jede überladene Version. Dies bedeutet normalerweise, dass jede Version eine andere Parameterliste angeben muss. Weitere Informationen finden Sie unter "Andere Signatur" in [Prozedurüberladung](./procedure-overloading.md).  
  
 Sie können überladen eine `Function` Prozedur mit einer `Sub` Prozedur, und umgekehrt, sofern sie über andere Signaturen verfügen. Zwei Überladungen können nicht unterscheiden sich nur darin, dass eine über einen Rückgabewert verfügt, und die andere nicht aber.  
  
 Sie können die gleiche Weise, die Sie überladen eine Prozedur, eine Eigenschaft überladen und mit den gleichen Einschränkungen. Sie können keine jedoch Überladen einer Prozedur mit einer Eigenschaft (oder umgekehrt).  
  
## <a name="alternatives-to-overloaded-versions"></a>Alternativen zu überladenen Versionen  
 Alternativen zu überladenen Versionen haben manchmal insbesondere dann, wenn das Vorhandensein von Argumenten ist eine optionale oder deren Anzahl ist die Variable ein.  
  
 Bedenken Sie, dass optionale Argumente werden nicht unbedingt von allen Sprachen unterstützt, und Parameterarrays Visual Basic beschränkt sind. Wenn Sie eine Prozedur schreiben, die wahrscheinlich in einem der anderen Sprachen geschriebenen Code aufgerufen werden, überladene bieten Versionen die größte Flexibilität.  
  
### <a name="overloads-and-optional-arguments"></a>Überladungen und optionale Argumente  
 Wenn der aufrufende Code kann optional angeben oder ein oder mehrere Argumente auslassen, können Sie mehrere überladene Versionen definieren oder optionale Parameter verwenden.  
  
#### <a name="when-to-use-overloaded-versions"></a>Überladene Versionen verwenden  
 Sie können in Betracht ziehen, definieren eine Reihe von überladenen Versionen in den folgenden Fällen:  
  
-   Die Logik im Code Prozedur ist erheblich variieren, je nachdem, ob der aufrufende Code ein optionales Argument bereitstellt.  
  
-   Der Code die Prozedur kann nicht zuverlässig testen Sie, ob der aufrufende Code ein optionale Argument bereitgestellt hat. Dies ist die Groß-/Kleinschreibung, z. B. liegt keine möglichen Kandidaten für einen Standardwert an, die der aufrufende Code konnte nicht zu erwarten.  
  
#### <a name="when-to-use-optional-parameters"></a>Optionale Parameter verwenden.  
 Möglicherweise bevorzugen Sie einen oder mehrere optionale Parameter in den folgenden Fällen:  
  
-   Die einzige erforderliche Aktion, wenn der aufrufende Code ein optionale Argument nicht angegeben wird ist, der Parameter auf den Standardwert festgelegt. In diesem Fall der Code kann weniger kompliziert, wenn Sie eine einzelne Version mit einem oder mehreren definieren `Optional` Parameter.  
  
 Weitere Informationen finden Sie unter [optionale Parameter](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Überladungen und ParamArrays  
 Wenn der aufrufende Code eine Variable Anzahl von Argumenten übergeben kann, können Sie mehrere überladene Versionen definieren oder ein Parameterarray verwenden.  
  
#### <a name="when-to-use-overloaded-versions"></a>Überladene Versionen verwenden  
 Sie können in Betracht ziehen, definieren eine Reihe von überladenen Versionen in den folgenden Fällen:  
  
-   Sie wissen, dass der aufrufende Code nie mehr als eine geringe Anzahl von an das Parameterarray übergeben wird.  
  
-   Die Logik im Code Prozedur ist erheblich variieren, je nachdem wie viele Werte, die der aufrufende Code übergibt.  
  
-   Der aufrufende Code kann Werte mit unterschiedlichen Datentypen übergeben werden.  
  
#### <a name="when-to-use-a-parameter-array"></a>Ein Parameterarray verwenden.  
 Sie werden von besser bedient ein `ParamArray` Parameter in den folgenden Fällen:  
  
-   Sie sind nicht wie viele Werte prognostizieren der aufrufende Code an das Parameterarray übergeben kann, und es ist möglicherweise eine große Anzahl.  
  
-   Logik der Prozedur eignet sich für alle Werte, die der aufrufende Code übergibt die im Wesentlichen die gleichen Vorgänge für jeden Wert durchführen, durchlaufen.  
  
 Weitere Informationen finden Sie unter [Parameterarrays](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Implizite Überladungen für optionale Parameter  
 Eine Prozedur mit einem [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) entspricht zwei überladenen Prozeduren, mit dem optionalen Parameter und eine ohne Parameter. Eine solche Prozedur kann nicht mit einer Parameterliste, die einer der folgenden entspricht überladen werden. Die folgenden Deklarationen veranschaulicht.  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 Für eine Prozedur mit mehr als ein optionaler Parameter ist es eine Reihe von implizite Überladungen, eingetroffen von Logik, die im vorherigen Beispiel ähnelt.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Implizite Überladungen für ParamArray-Parameter  
 Der Compiler betrachtet eine Prozedur mit einem [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Parameter haben eine unendliche Anzahl von Überladungen, die in der aufrufende Code wie folgt an das Parameterarray übergibt sich dadurch voneinander unterscheiden:  
  
-   Eine Überladung für, wenn der aufrufende Code nicht Argument bereitgestellt der `ParamArray`  
  
-   Eine Überladung für, wenn der aufrufende Code ein eindimensionales Array vom liefert die `ParamArray` Elementtyp.  
  
-   Für jede positive ganze Zahl, eine Überladung für, wenn der aufrufende Code die Anzahl der Argumente, aller liefert die `ParamArray` Elementtyp.  
  
 Die folgenden Deklarationen veranschaulichen diese implizite Überladungen.  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 Sie können sich nicht auf eine solche Prozedur mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert. Allerdings können Sie die Signaturen der implizite Überladungen verwenden. Die folgenden Deklarationen veranschaulicht.  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Programmierung ohne Datentypen als Alternative zum Überladen  
 Wenn den aufrufenden Code auf einen Parameter unterschiedliche Datentypen übergeben werden sollen, ist ein alternativer Ansatz Programmierung ohne Datentypen. Sie können festlegen, dass der Switch die typüberprüfung `Off` entweder mit der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) oder [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) -Compileroption. Dann müssen Sie keinen Datentyp für den Parameter zu deklarieren. Dieser Ansatz hat jedoch die folgenden Nachteile im Vergleich zum Überladen:  
  
-   Programmierung ohne Datentypen erzeugt der Ausführungscode für weniger effizient.  
  
-   Die Prozedur muss für jeden Datentyp testen, dessen Übergabe.  
  
-   Der Compiler kann nicht auf einen Fehler signalisieren, wenn der aufrufende Code einen Datentyp übergibt, den die Prozedur nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)  
 [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)  
 [Gewusst wie: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Überladungsauflösung](./overload-resolution.md)  
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
