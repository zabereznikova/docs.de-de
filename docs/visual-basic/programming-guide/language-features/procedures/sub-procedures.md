---
title: Sub-Prozeduren (Visual Basic) | Microsoft-Dokumentation
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
- Sub procedures, about Sub procedures
- statement blocks
- Sub procedures, calling
- procedures, calling
- Sub procedures, syntax
- Sub procedures
- procedures, Sub
- syntax, Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
caps.latest.revision: 21
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
ms.openlocfilehash: d224fa3338ca707070ee431380578a8fdde47e07
ms.lasthandoff: 03/13/2017

---
# <a name="sub-procedures-visual-basic"></a>Sub-Prozeduren (Visual Basic)
Ein `Sub` Prozedur ist eine Reihe von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Anweisungen, die durch die `Sub` und `End Sub` Anweisungen. Die `Sub` Prozedur eine Aufgabe ausführt, und dann wird die Steuerung an den aufrufenden Code zurückgegeben, aber keinen Wert an den aufrufenden Code zurück.  
  
 Jedes Mal die Prozedur aufgerufen wird, die Anweisungen ausgeführt werden, beginnend mit der ersten ausführbaren Anweisung nach der `Sub` -Anweisung und endet mit dem ersten `End Sub`, `Exit Sub`, oder `Return` Anweisung aufgetreten.  
  
 Sie können eine `Sub` Verfahren in Modulen, Klassen und Strukturen. In der Standardeinstellung ist `Public`, womit Sie können ihn Aufrufen von überall in Ihrer Anwendung, die Zugriff auf das Modul, Klasse oder Struktur, in der Sie definiert, wurde. Der Begriff *Methode*, beschreibt eine `Sub` oder `Function` -Prozedur, die außerhalb der definieren aus zugegriffen werden kann-Modul, die Klasse oder Struktur. Weitere Informationen finden Sie unter [Prozeduren](./index.md).  
  
 Ein `Sub` -Prozeduren können Argumente, wie z. B. Konstanten, Variablen oder Ausdrücke, die durch den Aufrufcode an sie übergeben werden.  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Die Syntax zum Deklarieren einer `Sub` Prozedur lautet wie folgt:  
  
 `[`*modifiers* `] Sub`*subname* `[(` *parameterlist*  `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 Die `modifiers` können Zugriffsebene und Informationen zum Überladen, überschreiben, freigeben und shadowing angeben. Weitere Informationen finden Sie unter [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="parameter-declaration"></a>Parameterdeklaration  
 Sie deklarieren jeder Prozedurparameter wird auf ähnliche Weise, wie Sie eine Variable deklarieren, den Parametertyp und den Datentyp angibt. Sie können auch angeben, den Mechanismus übergeben, und gibt an, ob der Parameter optional ist oder ein Parameterarray.  
  
 Die Syntax für jeden Parameter in der Parameterliste lautet wie folgt:  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *Parametername*`As`*Datentyp    *  
  
 Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben. Die Syntax zum Angeben der Standardwert lautet wie folgt:  
  
 `Optional [ByVal | ByRef]`  *Parametername*`As`*Datentyp*`=`*Defaultvalue        *  
  
### <a name="parameters-as-local-variables"></a>Parameter als lokale Variablen  
 Wenn die Steuerung an die Prozedur übergeben wird, wird jeder Parameter als lokale Variable behandelt. Dies bedeutet, dass seine Lebensdauer identisch mit der Prozedur ist, und der Gültigkeitsbereich die gesamte Prozedur ist.  
  
## <a name="calling-syntax"></a>Aufrufen der Syntax  
 Rufen Sie eine `Sub` Prozedur explizit mit dem eigenständigen aufrufen. Sie können nicht durch die Verwendung des Namens in einem Ausdruck aufgerufen werden. Geben Sie Werte für alle Argumente, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen. Wenn keine Argumente angegeben sind, können Sie die Klammern auch weglassen. Die Verwendung der `Call` -Schlüsselwort ist optional, wird aber empfohlen.  
  
 Die Syntax für einen Aufruf einer `Sub` Prozedur lautet wie folgt:  
  
 `[Call]`  *Subname* `[(` *Argumentlist*`)]`  
  
 Rufen Sie eine `Sub` -Methode außerhalb der Klasse, die es definiert. Zuerst müssen Sie verwenden die `New` -Schlüsselwort verwenden, um eine Instanz der Klasse erstellen oder eine Methode aufrufen, gibt eine Instanz der Klasse zurück. Weitere Informationen finden Sie unter [Operator New](../../../../visual-basic/language-reference/operators/new-operator.md). Anschließend können die folgende Syntax zum Aufrufen der `Sub` -Methode für das Instanzobjekt:  
  
 *Object*.* MethodName*`[(`*Argumentlist*`)]`  
  
### <a name="illustration-of-declaration-and-call"></a>Darstellung von Deklaration und Aufruf  
 Die folgenden `Sub` -Prozedur meldet die welche Aufgabe die Anwendung sowie einen Zeitstempel an. Anstatt diesen Code am Anfang jeder Aufgabe wiederholt auszuführen, ruft die Anwendung nur `tellOperator` von verschiedenen Standorten. Jeder Aufruf übergibt eine Zeichenfolge in der `task` -Argument, das die gestartete Aufgabe identifiziert.  
  
 [!code-vb[VbVbcnProcedures&#2;](./codesnippet/VisualBasic/sub-procedures_1.vb)]  
  
 Das folgende Beispiel zeigt einen normalen Aufruf `tellOperator`.  
  
 [!code-vb[VbVbcnProcedures&3;](./codesnippet/VisualBasic/sub-procedures_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Function-Prozeduren](./function-procedures.md)   
 [Property-Prozeduren](./property-procedures.md)   
 [Operatorprozeduren](./operator-procedures.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)   
 [Gewusst wie: Aufrufen von einem Ereignishandler in Visual Basic](./how-to-call-an-event-handler.md)
