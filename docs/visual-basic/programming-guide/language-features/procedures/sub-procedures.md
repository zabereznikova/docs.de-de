---
title: Sub-Prozeduren (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7258d57d2677042a2020097893a4f7a0adb35508
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="sub-procedures-visual-basic"></a>Sub-Prozeduren (Visual Basic)
Ein `Sub` Verfahren besteht aus einer Reihe von Visual Basic-Anweisungen von der `Sub` und `End Sub` Anweisungen. Die `Sub` Prozedur, eine Aufgabe ausführt, und klicken Sie dann die Steuerung an den aufrufenden Code zurückgegeben, aber es wird keinen Wert an den aufrufenden Code zurückgegeben.  
  
 Jedes Mal, die die Prozedur aufgerufen wird, die Anweisungen werden ausgeführt, beginnend mit der ersten ausführbaren Anweisung nach der `Sub` -Anweisung und endet mit dem ersten `End Sub`, `Exit Sub`, oder `Return` Anweisung wurde gefunden.  
  
 Sie können definieren, eine `Sub` Prozedur in Modulen, Klassen und Strukturen. Standardmäßig ist es `Public`, das bedeutet, dass erreichen sie von jedem beliebigen Standort in Ihrer Anwendung, die Zugriff auf das Modul, Klasse oder Struktur an, in dem Sie definiert, wurde. Der Begriff *Methode*, beschreibt eine `Sub` oder `Function` Prozedur, die aus außerhalb seiner Definition erfolgt-Modul, die Klasse oder Struktur. Weitere Informationen finden Sie unter [Prozeduren](./index.md).  
  
 Ein `Sub` Argumenten, z. B. Konstanten, Variablen oder Ausdrücke, die an ihn, der aufrufende Code übergeben werden kann in Anspruch nehmen.  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Die Syntax zum Deklarieren einer `Sub` Prozedur lautet wie folgt:  
  
 `[` *Modifizierer* `] Sub` *Subname* `[(` *Parameterlist*  `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 Die `modifiers` Zugriffsebene und Informationen zu überladen, überschreiben, freigeben und shadowing angeben können. Weitere Informationen finden Sie unter [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="parameter-declaration"></a>Parameterdeklaration  
 Sie deklarieren, jede Prozedurparameter auf ähnliche Weise, wie Sie eine Variable zu deklarieren, die Parameter und den Datentyp angibt. Sie können auch den Übergabemechanismus angeben und gibt an, ob der Parameter optional ist oder ein Parameterarray.  
  
 Die Syntax für jeden Parameter in der Parameterliste lautet wie folgt:  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *Parametername*`As`*Datatype*   
  
 Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben. Die Syntax zum Angeben der Standardwert lautet wie folgt:  
  
 `Optional [ByVal | ByRef]`  *Parametername*`As`*Datatype*`=`*"DefaultValue"*   
  
### <a name="parameters-as-local-variables"></a>Parameter als lokale Variablen  
 Wenn die Steuerung an die Prozedur übergeben wird, wird jeder Parameter als lokale Variable behandelt. Dies bedeutet, dass seine Lebensdauer identisch mit der Prozedur ist und der Bereich die gesamte Prozedur ist.  
  
## <a name="calling-syntax"></a>Aufrufen der Syntax  
 Rufen Sie eine `Sub` Prozedur explizit mit einer eigenständigen aufrufende Anweisung. Es kann nicht anhand des Namens in einem Ausdruck aufgerufen werden. Geben Sie Werte für alle Argumente, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen. Wenn keine Argumente übergeben werden, können Sie die Klammern optional weglassen. Die Verwendung der `Call` -Schlüsselwort ist optional, jedoch nicht empfohlen.  
  
 Die Syntax für einen Aufruf einer `Sub` Prozedur lautet wie folgt:  
  
 `[Call]`  *Subname* `[(` *Argumentlist* `)]`  
  
 Sie erreichen eine `Sub` Methode von außerhalb der Klasse, die ihn definiert. Zunächst müssen Sie die `New` Schlüsselwort erstellen Sie eine Instanz der Klasse oder eine Methode aufrufen, gibt eine Instanz der Klasse zurück. Weitere Informationen finden Sie unter [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md). Anschließend können die folgende Syntax zum Aufrufen der `Sub` -Methode für das Instance-Objekt:  
  
 *Objekt*. *Methodenname*`[(`*Argumentlist*`)]`  
  
### <a name="illustration-of-declaration-and-call"></a>Abbildung der Deklaration und Aufruf  
 Die folgenden `Sub` Prozedur Computer der Operator weist die Aufgabe die Anwendung und zeigt außerdem einen Zeitstempel. Anstelle von duplizieren diesen Code am Anfang jeder Aufgabe an, ruft die Anwendung nur `tellOperator` an verschiedenen Standorten. Jeder Aufruf übergibt eine Zeichenfolge in der `task` Argument, das die gestartete Aufgabe identifiziert.  
  
 [!code-vb[VbVbcnProcedures#2](./codesnippet/VisualBasic/sub-procedures_1.vb)]  
  
 Das folgende Beispiel zeigt einen typischen Aufruf `tellOperator`.  
  
 [!code-vb[VbVbcnProcedures#3](./codesnippet/VisualBasic/sub-procedures_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Function-Prozeduren](./function-procedures.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Operatorprozeduren](./operator-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)  
 [Vorgehensweise: Aufrufen eines Ereignishandlers in Visual Basic](./how-to-call-an-event-handler.md)
