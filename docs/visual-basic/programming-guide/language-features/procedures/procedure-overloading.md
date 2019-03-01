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
ms.openlocfilehash: 4d90b81049197fbbf4a767b17399d3e9c80be0f7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975471"
---
# <a name="procedure-overloading-visual-basic"></a>Prozedurüberladung (Visual Basic)
*Überladen von* eine Prozedur bedeutet, dass es in mehreren Versionen, die mit dem gleichen Namen, aber unterschiedlichen Parameterlisten definiert. Der Zweck des Überladens werden mehrere eng verwandte Versionen einer Prozedur zu definieren, ohne dass sie anhand des Namens zu unterscheiden. Dazu müssen Sie die Parameterliste variieren.  
  
## <a name="overloading-rules"></a>Überladen von Regeln  
 Wenn Sie eine Prozedur zu überladen, gelten die folgenden Regeln:  
  
-   **Gleichnamigen**. Jede überladene Version, muss die Namen der gleichen Prozedur verwenden.  
  
-   **Andere Signatur**. Jede überladene Version muss alle anderen überladenen Versionen in mindestens einem der folgenden Aspekte unterscheiden:  
  
    -   Anzahl von Parametern  
  
    -   Reihenfolge der Parameter  
  
    -   Die Datentypen der Parameter  
  
    -   Anzahl der Typparameter (für eine generische Prozedur)  
  
    -   Der Rückgabetyp (nur für eines Konvertierungsoperators)  
  
     Zusammen mit den Namen der Prozedur, die vorherigen Elemente werden als bezeichnet die *Signatur* der Prozedur. Wenn Sie eine überladene Prozedur aufrufen, verwendet der Compiler die Signatur zu um überprüfen, ob der Aufruf mit der Definition übereinstimmt.  
  
-   **Elemente, die nicht Teil der Signatur**. Sie können sich keine Prozedur überladen, ohne die Signatur variieren. Sie können insbesondere Prozedur durch die Änderung nur eine oder mehrere der folgenden Elemente nicht überladen:  
  
    -   Schlüsselwörter für Prozedurmodifizierer, z. B. `Public`, `Shared`, und `Static`  
  
    -   Parameternamen für Parameter oder Typ  
  
    -   Einschränkungen für Typparameter (für eine generische Prozedur)  
  
    -   Parametermodifiziererschlüsselwörter, z. B. `ByRef` und `Optional`  
  
    -   Gibt an, ob es sich um einen Wert zurückgibt  
  
    -   Der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungsoperators)  
  
     Die Elemente in der vorherigen Liste sind nicht Teil der Signatur. Obwohl Sie sie verwenden können, um zwischen überladenen Versionen zu unterscheiden, können Sie sie zwischen überladenen Versionen variieren, die ordnungsgemäß durch ihre Signaturen unterscheiden.  
  
-   **Spät gebundene Argumente**. Wenn Sie eine spät gebundenen Objektvariable an eine überladene Version übergeben möchten, müssen Sie die entsprechende Parameter als deklarieren <xref:System.Object>.  
  
## <a name="multiple-versions-of-a-procedure"></a>Mehrere Versionen einer Prozedur  
 Angenommen, Sie schreiben eine `Sub` Verfahren zum Veröffentlichen einer Transaktions anhand eines Kunden, und Sie möchten, entweder nach Name oder Nummer eines Kontos für den Kunden zu verweisen. Um dies zu berücksichtigen, können Sie definieren zwei verschiedene `Sub` Prozeduren, wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]  
  
### <a name="overloaded-versions"></a>Überladene Versionen  
 Eine Alternative ist, einen Namen für die einzelnen Prozedur zu überladen. Sie können die [Überladungen](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort, um eine Version der Prozedur für jede Parameterliste wie folgt definieren:  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
#### <a name="additional-overloads"></a>Zusätzliche Überladungen  
 Wenn Sie auch Transaktionsbetrags entweder akzeptieren möchten `Decimal` oder `Single`, überladen Sie weitere `post` um diese Variante zu ermöglichen. In diesem Fall auf jede der Überladungen im vorherigen Beispiel, würden Sie haben vier `Sub` -Prozeduren mit dem gleichen Namen mit vier unterschiedlichen Signaturen.  
  
## <a name="advantages-of-overloading"></a>Vorteile des Überladens  
 Der Vorteil der überladen einer Prozedur ist die Flexibilität des Aufrufs. Verwenden der `post` Prozedur deklariert, im vorherigen Beispiel der aufrufende Code erhalten die Kunden-ID als ein `String` oder `Integer`, und rufen Sie dann in beiden Fällen das gleiche Verfahren. Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
 [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>Siehe auch
- [Verfahren](./index.md)
- [Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Vorgehensweise: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)
- [Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)
- [Überladungsauflösung](./overload-resolution.md)
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
