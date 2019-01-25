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
ms.openlocfilehash: 234cd23c487f92cfa1e2761dd7a6caadf8820704
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685801"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Überlegungen zur Prozedurüberladung (Visual Basic)
Wenn Sie eine Prozedur zu überladen, müssen Sie einen anderen verwenden *Signatur* für jede überladene Version. Dies bedeutet normalerweise, dass jede Version eine anderen Parameterliste angeben muss. Weitere Informationen finden Sie unter "Andere Signatur" in [Prozedurüberladung](./procedure-overloading.md).  
  
 Überladen Sie eine `Function` Prozedur mit einer `Sub` Verfahren und umgekehrt, sofern sie verschiedene Signaturen aufweisen. Zwei Überladungen dürfen sich nicht nur darin, dass eine einen Rückgabewert hat und die andere nicht aber unterscheiden.  
  
 Sie können die gleiche Weise, die Sie überladen eine Prozedur, eine Eigenschaft überladen und mit denselben Einschränkungen. Aber Sie können nicht überladen einer Prozedur mit einer Eigenschaft (oder umgekehrt).  
  
## <a name="alternatives-to-overloaded-versions"></a>Alternativen zu überladenen Versionen  
 Sie müssen manchmal Alternativen für die überladene Versionen, insbesondere dann, wenn das Vorhandensein von Argumenten optional ist, oder deren Anzahl ist die Variable.  
  
 Bedenken Sie, dass optionale Argumente werden nicht unbedingt von allen Sprachen unterstützt, und Parameterarrays in Visual Basic beschränkt sind. Wenn Sie eine Prozedur, die wahrscheinlich Schreiben für den Aufruf aus Code in einer von mehreren verschiedenen Sprachen geschrieben wurden, überladene bieten Versionen die größte Flexibilität.  
  
### <a name="overloads-and-optional-arguments"></a>Überladungen und optionale Argumente  
 Wenn der aufrufende Code kann optional angeben oder ein oder mehrere Argumente auslassen, können Sie mehrere überladene Versionen definieren oder optionale Parameter verwenden.  
  
#### <a name="when-to-use-overloaded-versions"></a>Überladene Versionen verwenden.  
 Sie können in Betracht ziehen, eine Reihe von überladenen Versionen definiert, in den folgenden Fällen:  
  
-   Die Logik im Code Prozedur unterscheidet sich erheblich abhängig davon, ob der aufrufende Code ein optionales Argument bereitstellt.  
  
-   Code der Prozedur kann nicht zuverlässig zu testen, ob der aufrufende Code ein optionales Argument angegeben hat. Dies ist der Fall, z. B. liegt keine möglichen Kandidaten für einen Standardwert an, die der aufrufende Code konnte nicht zu erwarten.  
  
#### <a name="when-to-use-optional-parameters"></a>Optionale Parameter verwenden.  
 Möglicherweise bevorzugen Sie einen oder mehrere optionale Parameter in den folgenden Fällen:  
  
-   Die einzige erforderliche Aktion, wenn der aufrufende Code ein optionale Argument nicht angegeben wird, ist den Parameter auf einen Standardwert festlegen. In diesem Fall der Code der Prozedur kann weniger kompliziert sein, wenn Sie eine einzelne Version mit einem oder mehreren definieren `Optional` Parameter.  
  
 Weitere Informationen finden Sie unter [optionale Parameter](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Überladungen und ParamArrays  
 Wenn der aufrufende Code eine Variable Anzahl von Argumenten übergeben kann, können Sie mehrere überladene Versionen definieren oder ein Parameterarray verwenden.  
  
#### <a name="when-to-use-overloaded-versions"></a>Überladene Versionen verwenden.  
 Sie können in Betracht ziehen, eine Reihe von überladenen Versionen definiert, in den folgenden Fällen:  
  
-   Sie wissen, dass der aufrufende Code nie mehr als eine kleine Anzahl von Werten für das Parameterarray erfolgreich war.  
  
-   Die Logik im Code Prozedur ist erheblich variieren, je nachdem wie viele Werte, die der aufrufende Code übergeben.  
  
-   Der aufrufende Code kann es sich um die Werte mit unterschiedlichen Datentypen übergeben.  
  
#### <a name="when-to-use-a-parameter-array"></a>Ein Parameterarray verwenden.  
 Sie sind besser geeignet, indem eine `ParamArray` Parameter in den folgenden Fällen:  
  
-   Sie können nicht vorhersagen, wie viele Werte der aufrufende Code für das Parameterarray übergeben kann, und möglicherweise eine große Anzahl.  
  
-   Logik der Prozedur eignet sich für alle Werte, die der aufrufende Code im Wesentlichen die gleichen Vorgänge für jeden Wert ausführen besteht, durchlaufen.  
  
 Weitere Informationen finden Sie unter [Parameterarrays](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Implizite Überladungen für optionale Parameter  
 Eine Prozedur mit einem [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) entspricht zwei überladenen Prozeduren, mit dem optionalen Parameter und eine ohne Parameter. Sie können keine solche Prozedur mit einer Parameterliste entspricht, die an einen der beiden überladen. Die folgenden Deklarationen veranschaulicht.  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 Für eine Prozedur mit mehr als einen optionalen Parameter ist es ein Satz von implizite Überladungen, jeweils aussagekräftige Testabfragen Durchführen von Logik, die im vorherigen Beispiel ähnelt.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Implizite Überladungen für ParamArray-Parameter  
 Der Compiler betrachtet eine Prozedur mit einem [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Parameter, um eine unbegrenzte Anzahl von Überladungen, die in der aufrufende Code wie folgt auf das Parameterarray übergibt sich dadurch voneinander unterscheiden zu erhalten:  
  
-   Eine Überladung für Wenn der aufrufende Code kein Argument übergibt die `ParamArray`  
  
-   Eine Überladung für, wenn der aufrufende Code ein eindimensionales Array stellt die `ParamArray` Elementtyp  
  
-   Für jede positive ganze Zahl, eine Überladung für, wenn der aufrufende Code diese Anzahl von Argumenten, die jeweils der stellt der `ParamArray` Elementtyp  
  
 Die folgenden Deklarationen veranschaulichen diese implizite Überladungen.  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 Sie können sich nicht auf eine solche Prozedur mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert. Allerdings können Sie die Signaturen der anderen implizite Überladungen. Die folgenden Deklarationen veranschaulicht.  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Programmierung ohne Datentypen als Alternative zum Überladen  
 Wenn den aufrufenden Code unterschiedliche Datentypen auf einen Parameter übergeben werden sollen, ist ein alternativer Ansatz Programmierung ohne Datentypen. Sie können festlegen, der Switch die typüberprüfung `Off` entweder mit der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) oder [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) -Compileroption. Dann müssen Sie keinen Datentyp des Parameters zu deklarieren. Dieser Ansatz weist jedoch die folgenden Nachteile im Vergleich zum Überladen:  
  
-   Programmierung ohne Datentypen erzeugt Ausführungscode weniger effizient.  
  
-   Die Prozedur muss für jeden Datentyp testen dessen Übergabe.  
  
-   Der Compiler kann nicht auf einen Fehler signalisieren, wenn der aufrufende Code einen Datentyp übergibt, den die Prozedur nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch
- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Vorgehensweise: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)
- [Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Überladungsauflösung](./overload-resolution.md)
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
