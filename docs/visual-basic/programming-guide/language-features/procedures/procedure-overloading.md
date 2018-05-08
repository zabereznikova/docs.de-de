---
title: Prozedurüberladung (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 0d1f2c4d8c88922659b3d91ed41d5e760e6e5233
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="procedure-overloading-visual-basic"></a>Prozedurüberladung (Visual Basic)
*Überladen von* eine Prozedur bedeutet, dass es in mehreren Versionen, die mit dem gleichen Namen, aber unterschiedlichen Parameterlisten definiert. Der Zweck des Überladens werden mehrere eng verwandte Versionen einer Prozedur definieren, ohne sie anhand des Namens zu unterscheiden. Dazu müssen Sie die Parameterliste variabler.  
  
## <a name="overloading-rules"></a>Überladen von Regeln  
 Wenn Sie eine Prozedur zu überladen, gelten die folgenden Regeln:  
  
-   **Gleichnamigen**. Jede überladene Version muss den gleichen Prozedurnamen verwenden.  
  
-   **Andere Signatur**. Jede überladene Version muss sich von anderen überladenen Versionen in mindestens einer der folgenden Punkte unterscheiden:  
  
    -   Anzahl von Parametern  
  
    -   Reihenfolge der Parameter  
  
    -   Die Datentypen der Parameter  
  
    -   Anzahl der Typparameter (für eine generische Prozedur)  
  
    -   Rückgabetyp (nur für einen Konvertierungsoperator)  
  
     Die vorherigen Elemente werden zusammen mit den Namen der Prozedur als bezeichnet den *Signatur* der Prozedur. Wenn Sie eine überladene Prozedur aufrufen, verwendet der Compiler die Signatur überprüfen, ob der Aufruf der Definition übereinstimmt.  
  
-   **Elemente, die nicht Teil der Signatur**. Eine Prozedur kann nicht überladen werden, ohne die Signatur variieren. Insbesondere können Sie Prozedur durch Variierung der nur eine oder mehrere der folgenden Elemente nicht überladen:  
  
    -   Schlüsselwörter für Prozedurmodifizierer, z. B. `Public`, `Shared`, und `Static`  
  
    -   Parameter oder Typ Parameternamen  
  
    -   Einschränkungen für Typparameter (für eine generische Prozedur)  
  
    -   Parametermodifiziererschlüsselwörter, wie z. B. `ByRef` und `Optional`  
  
    -   Gibt an, ob es sich um einen Wert zurückgibt  
  
    -   Der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungsoperators)  
  
     Die Elemente in der vorangehenden Liste aufgeführt sind nicht Teil der Signatur. Obwohl Sie sie verwenden können, um zwischen überladenen Versionen zu unterscheiden, können Sie diese überladenen Versionen variieren, die ordnungsgemäß durch ihre Signaturen unterscheiden.  
  
-   **Spät gebundene Argumente**. Wenn Sie beabsichtigen, eine spät gebundenen Objektvariable an eine überladene Version zu übergeben, müssen Sie die entsprechende Parameter als deklarieren <xref:System.Object>.  
  
## <a name="multiple-versions-of-a-procedure"></a>Mehrere Versionen einer Prozedur  
 Angenommen, Sie schreiben eine `Sub` Verfahren zum Bereitstellen einer Transaktions für ein Kunde Balance, und Sie sollten an den Kunden nach Name oder der Kontonummer verweisen können. Um dies zu berücksichtigen, können Sie definieren zwei verschiedene `Sub` Prozeduren, wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbVbcnProcedures#73](./codesnippet/VisualBasic/procedure-overloading_1.vb)]  
  
### <a name="overloaded-versions"></a>Überladene Versionen  
 Eine Alternative besteht, einen Namen für die einzelnen Prozedur zu überladen. Sie können die [überlädt](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort, um eine Version der Prozedur für jede Parameterliste wie folgt definieren:  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/procedure-overloading_2.vb)]  
  
#### <a name="additional-overloads"></a>Zusätzliche Überladungen  
 Wenn Sie zudem soll demonstriert werden eine Transaktion Menge entweder akzeptiert `Decimal` oder `Single`, überladen Sie weitere `post` um diese Variante zu ermöglichen. Wenn Sie dies auf jede der Überladungen im vorherigen Beispiel, würden Sie haben vier `Sub` -Prozeduren mit dem gleichen Namen mit vier unterschiedlichen Signaturen möglich.  
  
## <a name="advantages-of-overloading"></a>Vorteile des Überladens  
 Der Vorteil der überladen einer Prozedur ist die Flexibilität des Aufrufs. Verwenden der `post` Prozedur deklariert, im vorherigen Beispiel der aufrufende Code erhalten die Kunden-ID als ein `String` oder ein `Integer`, und rufen Sie anschließend in beiden Fällen das gleiche Verfahren. Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/procedure-overloading_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)  
 [Gewusst wie: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)  
 [Überladungsauflösung](./overload-resolution.md)  
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
