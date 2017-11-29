---
title: "Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 787eddc1fd1cdb9dd6b655a8556b75044b2a49dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt (Visual Basic)
Sie verwenden eine `Function` -Prozedur, einen Wert an den aufrufenden Code zurückgibt.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>So erstellen Sie eine Prozedur, die einen Wert zurückgibt  
  
1.  Außerhalb eine beliebige andere Prozedur verwendet eine `Function` Anweisung, gefolgt von einem `End Function` Anweisung.  
  
2.  In der `Function` -Anweisung, befolgen Sie die `Function` Schlüsselwort mit dem Namen der Prozedur, und klicken Sie dann die Parameterliste in Klammern.  
  
3.  Führen Sie die Klammern mit einer `As` -Klausel, um den Datentyp des zurückgegebenen Werts angeben.  
  
4.  Platzieren Sie die Prozedur codeanweisungen zwischen der `Function` und `End Function` Anweisungen.  
  
5.  Verwenden einer `Return` -Anweisung den Wert an den aufrufenden Code zurückgegeben.  
  
     Die folgenden `Function` Prozedur berechnet die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, anhand der Werte der beiden anderen Seiten.  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     Das folgende Beispiel zeigt einen typischen Aufruf `hypotenuse`.  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Operatorprozeduren](./operator-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Gewusst wie: Abrufen eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md)  
 [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)
