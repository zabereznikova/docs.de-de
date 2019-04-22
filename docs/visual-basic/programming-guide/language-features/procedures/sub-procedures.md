---
title: Sub-Prozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: b70594e002bbf08f0890586e78df901ccb26c7ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843109"
---
# <a name="sub-procedures-visual-basic"></a>Sub-Prozeduren (Visual Basic)
Ein `Sub` Prozedur ist eine Reihe von Visual Basic Anweisungen durch die `Sub` und `End Sub` Anweisungen. Die `Sub` Prozedur, eine Aufgabe ausführt, und klicken Sie dann die steuerelementrückgabe an den aufrufenden Code, aber es gibt einen Wert nicht an den aufrufenden Code zurück.  
  
 Jedes Mal, die die Prozedur aufgerufen wird, die Anweisungen ausgeführt wird, beginnend mit der ersten ausführbaren Anweisung nach der `Sub` -Anweisung und beendet mit dem ersten `End Sub`, `Exit Sub`, oder `Return` Anweisung wurde gefunden.  
  
 Sie können definieren, eine `Sub` Verfahren in Module, Klassen und Strukturen. Es wird standardmäßig `Public`, das bedeutet, dass aus aufrufen können sie überall in Ihrer Anwendung, die Zugriff auf das Modul, Klasse oder Struktur, die in der Sie definiert wurde. Der Begriff *Methode*, beschreibt eine `Sub` oder `Function` Prozedur, die aus, außerhalb dessen definieren zugegriffen wird-Modul, Klasse oder Struktur. Weitere Informationen finden Sie unter [Prozeduren](./index.md).  
  
 Ein `Sub` Argumenten, z. B. Konstanten, Variablen oder Ausdrücke, die an ihn, der aufrufende Code übergeben werden kann in Anspruch nehmen.  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Die Syntax zum Deklarieren einer `Sub` Verfahren lautet wie folgt:  
  
 `[` *Modifizierer* `] Sub` *Subname* `[(` *Parameterlist* `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 Die `modifiers` Zugriffsebene und Informationen zu überladen, überschreiben, freigeben und shadowing angeben können. Weitere Informationen finden Sie unter [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="parameter-declaration"></a>Parameterdeklaration  
 Jeder Prozedurparameter auf ähnliche Weise wie Sie eine Variable deklarieren Angabe des Parametertyps und deklariert. Sie können auch angeben, den Übergabemechanismus und gibt an, ob der Parameter optional ist oder ein Parameterarray.  
  
 Die Syntax für jeden Parameter in der Liste der Parameter lautet wie folgt aus:  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *Parametername*`As`*Datatype*  
  
 Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben. Die Syntax zum Angeben der Standardwert ist wie folgt aus:  
  
 `Optional [ByVal | ByRef]`  *Parametername*`As`*Datatype*`=`*Defaultvalue*  
  
### <a name="parameters-as-local-variables"></a>Parameter als lokale Variablen  
 Wenn die Steuerung an die Prozedur übergeben, wird jeder Parameter als lokale Variable behandelt. Dies bedeutet, dass seine Lebensdauer identisch mit der Prozedur ist und der Bereich die ganze Prozedur ist.  
  
## <a name="calling-syntax"></a>Die Syntax aufrufen  
 Rufen Sie eine `Sub` Prozedur explizit mit einer eigenständigen aufrufenden Anweisung. Sie können nicht durch die Verwendung des Namens in einem Ausdruck aufgerufen werden. Geben Sie Werte für alle Argumente, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen. Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen. Die Verwendung der `Call` Schlüsselwort ist optional, jedoch nicht empfohlen.  
  
 Die Syntax für einen Aufruf einer `Sub` Verfahren lautet wie folgt:  
  
 `[Call]`  *subname* `[(` *argumentlist* `)]`  
  
 Rufen Sie eine `Sub` Methode außerhalb der Klasse, die es definiert. Zunächst müssen Sie mit der `New` Schlüsselwort, erstellen Sie eine Instanz der Klasse oder eine Methode aufrufen, gibt eine Instanz der Klasse zurück. Weitere Informationen finden Sie unter [neuer Operator](../../../../visual-basic/language-reference/operators/new-operator.md). Anschließend können die folgende Syntax zum Aufrufen der `Sub` Methode für das Instance-Objekt:  
  
 *Objekt*. *MethodName*`[(`*Argumentlist*`)]`  
  
### <a name="illustration-of-declaration-and-call"></a>Abbildung der Deklaration und Aufruf  
 Die folgenden `Sub` -Prozedur meldet die welche Aufgabe die Anwendung ausführen, sowie einen Zeitstempel an. Statt diesen Code am Anfang jeder Aufgabe zu wiederholen, ruft die Anwendung nur `tellOperator` an verschiedenen Standorten. Jeder Aufruf übergibt eine Zeichenfolge in die `task` Argument, das die gestartete Aufgabe identifiziert.  
  
 [!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]  
  
 Das folgende Beispiel zeigt einen typischen Aufruf von `tellOperator`.  
  
 [!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Function-Prozeduren](./function-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [Vorgehensweise: Aufrufen eines Ereignishandlers in Visual Basic](./how-to-call-an-event-handler.md)
