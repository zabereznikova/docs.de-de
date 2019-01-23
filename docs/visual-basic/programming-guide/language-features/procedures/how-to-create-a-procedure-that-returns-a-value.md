---
title: 'Vorgehensweise: Erstellen Sie eine Prozedur, die einen Wert zurückgibt (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 18becfe05da27e538c5c294b26e0bb7aa19cad2b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506419"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Vorgehensweise: Erstellen Sie eine Prozedur, die einen Wert zurückgibt (Visual Basic)
Sie verwenden eine `Function` -Prozedur, einen Wert an den aufrufenden Code zurückgibt.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Zum Erstellen einer Prozedur, die einen Wert zurückgibt.  
  
1.  Verwendung außerhalb anderer Prozeduren ein `Function` -Anweisung, gefolgt von einer `End Function` Anweisung.  
  
2.  In der `Function` -Anweisung, befolgen Sie die `Function` Schlüsselwort mit dem Namen der Prozedur, und klicken Sie dann die Liste der Parameter in Klammern.  
  
3.  Führen Sie die Klammern mit einer `As` -Klausel, um den Datentyp des zurückgegebenen Werts angeben.  
  
4.  Platzieren Sie Anweisungen von der Prozedur bei der Code zwischen den `Function` und `End Function` Anweisungen.  
  
5.  Verwenden einer `Return` -Anweisung den Wert an den aufrufenden Code zurückgegeben.  
  
     Die folgenden `Function` Prozedur berechnet werden, die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, anhand der Werte der beiden anderen Seiten.  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     Das folgende Beispiel zeigt einen typischen Aufruf von `hypotenuse`.  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Vorgehensweise: Zurückgeben eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md)
- [Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt.](./how-to-call-a-procedure-that-returns-a-value.md)
