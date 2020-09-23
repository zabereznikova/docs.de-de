---
title: Überlegungen zur Prozedurüberladung
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
ms.openlocfilehash: 6197fa4041a22944542b2657e35bc293a6e5c244
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075056"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Überlegungen zur Prozedurüberladung (Visual Basic)

Wenn Sie eine Prozedur überladen, müssen Sie für jede überladene Version eine andere *Signatur* verwenden. Dies bedeutet in der Regel, dass jede Version eine andere Parameterliste angeben muss. Weitere Informationen finden Sie unter "andere Signatur" in [Prozedur Überladung](./procedure-overloading.md).  
  
 Sie können eine `Function` Prozedur mit einer Prozedur überladen `Sub` und umgekehrt, wenn Sie über unterschiedliche Signaturen verfügen. Zwei über Ladungen können sich nur dadurch unterscheiden, dass ein Wert einen Rückgabewert aufweist und der andere nicht.  
  
 Sie können eine Eigenschaft auf die gleiche Weise überladen wie eine Prozedur und mit denselben Einschränkungen. Es ist jedoch nicht möglich, eine Prozedur mit einer-Eigenschaft zu überladen, oder umgekehrt.  
  
## <a name="alternatives-to-overloaded-versions"></a>Alternativen zu überladenen Versionen  

 Manchmal gibt es Alternativen zu überladenen Versionen, insbesondere dann, wenn das vorhanden sein von Argumenten optional ist oder die Zahl variabel ist.  
  
 Beachten Sie, dass optionale Argumente nicht notwendigerweise von allen Sprachen unterstützt werden und Parameter Arrays auf Visual Basic beschränkt sind. Wenn Sie eine Prozedur schreiben, die wahrscheinlich aus Code aufgerufen wird, der in einer von mehreren Sprachen geschrieben wurde, bieten überladene Versionen die größte Flexibilität.  
  
### <a name="overloads-and-optional-arguments"></a>Über Ladungen und optionale Argumente  

 Wenn der Aufruf Code ein oder mehrere Argumente optional angeben oder weglassen kann, können Sie mehrere überladene Versionen definieren oder optionale Parameter verwenden.  
  
#### <a name="when-to-use-overloaded-versions"></a>Verwendung von überladenen Versionen  

 In den folgenden Fällen können Sie eine Reihe von überladenen Versionen definieren:  
  
- Die Logik im Prozedur Code unterscheidet sich erheblich, je nachdem, ob der aufrufende Code ein optionales Argument bereitstellt.  
  
- Der Prozedur Code kann nicht zuverlässig überprüfen, ob der aufrufende Code ein optionales Argument bereitgestellt hat. Dies ist z. b. der Fall, wenn es keinen möglichen Kandidaten für einen Standardwert gibt, den der aufrufende Code nicht bereitstellen konnte.  
  
#### <a name="when-to-use-optional-parameters"></a>Verwendung optionaler Parameter  

 In den folgenden Fällen bevorzugen Sie möglicherweise einen oder mehrere optionale Parameter:  
  
- Die einzige erforderliche Aktion, wenn der aufrufende Code kein optionales Argument bereitstellt, besteht darin, den-Parameter auf einen Standardwert festzulegen. In einem solchen Fall kann der Prozedur Code weniger kompliziert sein, wenn Sie eine einzelne Version mit einem oder mehreren `Optional` Parametern definieren.  
  
 Weitere Informationen finden Sie unter [optionale Parameter](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Über Ladungen und Parametern  

 Wenn der Aufruf Code eine Variable Anzahl von Argumenten übergeben kann, können Sie mehrere überladene Versionen definieren oder ein Parameter Array verwenden.  
  
#### <a name="when-to-use-overloaded-versions"></a>Verwendung von überladenen Versionen  

 In den folgenden Fällen können Sie eine Reihe von überladenen Versionen definieren:  
  
- Sie wissen, dass der aufrufenden Code niemals mehr als eine kleine Anzahl von Werten an das Parameter Array übergibt.  
  
- Die Logik im Prozedur Code unterscheidet sich deutlich von der Anzahl der Werte, die der Aufruf Code übergibt.  
  
- Der Aufruf Code kann Werte verschiedener Datentypen übergeben.  
  
#### <a name="when-to-use-a-parameter-array"></a>Verwendung eines Parameter Arrays  

 In den folgenden Fällen ist es besser, einen `ParamArray` Parameter zu übertragen:  
  
- Sie können nicht vorhersagen, wie viele Werte der aufrufende Code an das Parameter Array übergeben kann, und es kann eine große Zahl sein.  
  
- Die Prozedur Logik eignet sich zum Durchlaufen aller Werte, die der aufrufende Code übergibt, und führt im Wesentlichen die gleichen Vorgänge für jeden Wert aus.  
  
 Weitere Informationen finden Sie unter [Parameter Arrays](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Implizite über Ladungen für optionale Parameter  

 Eine Prozedur mit einem [optionalen](../../../language-reference/modifiers/optional.md) Parameter entspricht zwei überladenen Prozeduren, eine mit dem optionalen Parameter und eine ohne Sie. Eine solche Prozedur kann nicht mit einer Parameterliste überladen werden, die einer dieser beiden entspricht. Dies wird in den folgenden Deklarationen veranschaulicht.  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 Für eine Prozedur mit mehr als einem optionalen Parameter gibt es eine Reihe impliziter über Ladungen, die mit der Logik erreicht werden, die im vorherigen Beispiel ähnlich ist.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Implizite über Ladungen für einen ParamArray-Parameter  

 Der Compiler betrachtet eine Prozedur mit einem [ParamArray](../../../language-reference/modifiers/paramarray.md) -Parameter so, dass eine unendliche Anzahl von über Ladungen vorhanden ist, die sich voneinander unterscheiden, wenn der aufrufende Code wie folgt an das Parameter Array übergeben wird:  
  
- Eine Überladung für den Fall, dass der aufrufende Code kein Argument für den `ParamArray`  
  
- Eine Überladung für den Fall, dass der aufrufenden Code ein eindimensionales Array vom Elementtyp bereitstellt. `ParamArray`  
  
- Für jede positive ganze Zahl eine Überladung für den Fall, dass der aufrufenden Code diese Anzahl von Argumenten bereitstellt, jeweils der `ParamArray` Elementtyp.  
  
 Die folgenden Deklarationen veranschaulichen diese impliziten über Ladungen.  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 Eine solche Prozedur kann nicht mit einer Parameterliste überladen werden, die ein eindimensionales Array für das Parameter Array annimmt. Allerdings können Sie die Signaturen der anderen impliziten über Ladungen verwenden. Dies wird in den folgenden Deklarationen veranschaulicht.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Typlose Programmierung als Alternative zum Überladen  

 Wenn Sie zulassen möchten, dass der aufrufende Code verschiedene Datentypen an einen Parameter übergibt, ist eine alternative Methode die typlose Programmierung. Sie können den Schalter für die Typüberprüfung auf festlegen, indem Sie `Off` entweder die [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md) oder die [-optionstrict-](../../../reference/command-line-compiler/optionstrict.md) Compileroption festlegen. Dann müssen Sie den Datentyp des Parameters nicht deklarieren. Allerdings hat dieser Ansatz im Vergleich zum Überladen folgende Nachteile:  
  
- Die typlose Programmierung erzeugt weniger effizienten Ausführungs Code.  
  
- Die Prozedur muss auf jeden Datentyp testen, der für die Übergabe erwartet wird.  
  
- Der Compiler kann keinen Fehler signalisieren, wenn der aufrufende Code einen Datentyp übergibt, den die Prozedur nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweisen](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Vorgehensweise: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Vorgehensweise: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)
- [Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Overload Resolution](./overload-resolution.md)
- [Überladungen](../../../language-reference/modifiers/overloads.md)
