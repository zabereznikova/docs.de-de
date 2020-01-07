---
title: 'Gewusst wie: Definieren mehrerer Versionen einer Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: e8ed9a6356b7177b2c029a9280d0790a93676653
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347599"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Gewusst wie: Definieren mehrerer Versionen einer Prozedur (Visual Basic)
Sie können eine Prozedur in mehreren Versionen definieren, indem Sie Sie *über* Lasten, indem Sie den gleichen Namen, aber eine andere Parameterliste für jede Version verwenden. Der Zweck der Überladung besteht darin, mehrere eng verwandte Versionen einer Prozedur zu definieren, ohne Sie nach Namen zu unterscheiden.  
  
 Weitere Informationen finden Sie unter [Procedure Overloading](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>So definieren Sie mehrere Versionen einer Prozedur  
  
1. Schreiben Sie für jede Version der Prozedur, die Sie definieren möchten, eine `Sub`-oder `Function` Deklarations Anweisung. Verwenden Sie den gleichen Prozedur Namen in jeder Deklaration.  
  
2. Vor dem `Sub` oder `Function`-Schlüsselwort in jeder Deklaration mit dem Schlüsselwort [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) . Optional können Sie `Overloads` in den Deklarationen weglassen, wenn Sie es jedoch in eine der Deklarationen einschließen, müssen Sie es in jede Deklaration einschließen.  
  
3. Schreiben Sie im Anschluss an jede Deklarations Anweisung den Prozedur Code, um den spezifischen Fall zu behandeln, in dem der aufrufende Code Argumente bereitstellt, die mit der Parameterliste Sie müssen nicht prüfen, welche Parameter der aufrufende Code bereitgestellt hat. Visual Basic übergibt die Steuerung an die entsprechende Version ihrer Prozedur.  
  
4. Beenden Sie jede Version der Prozedur mit der `End Sub`-oder `End Function`-Anweisung nach Bedarf.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Sub` Prozedur definiert, um eine Transaktion für den Saldo eines Kunden zu veröffentlichen. Er verwendet das `Overloads`-Schlüsselwort, um zwei Versionen der Prozedur zu definieren, die den Kunden nach dem Namen und den anderen nach Kontonummer akzeptiert.  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 Der aufrufende Code kann die Kunden Identifizierung entweder als `String` oder `Integer`abrufen und dann in beiden Fällen dieselbe aufrufende Anweisung verwenden.  
  
 Informationen dazu, wie Sie diese Versionen der `post` Prozedur aufzurufen, finden Sie unter Gewusst [wie: aufzurufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  
 Stellen Sie sicher, dass jede der überladenen Versionen denselben Prozedur Namen, aber eine andere Parameterliste hat.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Gewusst wie: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)
- [Überladungsauflösung](./overload-resolution.md)
