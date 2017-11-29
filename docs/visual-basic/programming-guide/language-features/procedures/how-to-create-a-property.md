---
title: 'Gewusst wie: Erstellen einer Eigenschaft (Visual Basic)'
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
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d140e6a10061f7fabe3d12c6cce5d0c201e103d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-property-visual-basic"></a>Gewusst wie: Erstellen einer Eigenschaft (Visual Basic)
Sie setzen eine Eigenschaftsdefinition zwischen einer `Property` Anweisung und eine `End Property` Anweisung. Innerhalb dieser Definition, die Sie definieren eine `Get` Prozedur, eine `Set` Prozedur oder beides. Alle Eigenschaft Code ist in diesen Prozeduren.  
  
 Die `Get` Prozedur ruft den Wert der Eigenschaft ab, und die `Set` Prozedur speichert einen Wert. Wenn Sie die Eigenschaft Lese-/Schreibzugriff verfügen soll, müssen Sie beide Prozeduren definieren. Für eine schreibgeschützte Eigenschaft, definieren Sie nur `Get`, und für eine WriteOnly-Eigenschaft, definieren Sie nur `Set`.  
  
### <a name="to-create-a-property"></a>So erstellen Sie eine Eigenschaft  
  
1.  Außerhalb einer Eigenschaft oder Prozedur verwendet eine [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md), gefolgt von einem `End Property` Anweisung.  
  
2.  Wenn die Eigenschaft Parameter annimmt, führen Sie die `Property` Schlüsselwort mit dem Namen der Prozedur, und klicken Sie dann auf die Parameterliste in Klammern.  
  
3.  Führen Sie die Klammern mit einer `As` -Klausel, um den Datentyp des Werts der Eigenschaft angeben. Sie müssen den Datentyp auch für eine WriteOnly-Eigenschaft angeben.  
  
4.  Hinzufügen `Get` und `Set` Prozeduren nach Bedarf. Finden Sie unter den folgenden Anweisungen.  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>Zum Erstellen einer Get-Prozedur, die einen Eigenschaftswert abruft.  
  
1.  Zwischen der `Property` und `End Property` -Anweisungen Schreiben einer [Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md), gefolgt von einer `End Get` Anweisung. Sie müssen keine Parameter für definieren die `Get` Prozedur.  
  
2.  Platzieren Sie die codeanweisungen zum Abrufen des Eigenschaftswerts zwischen den `Get` und `End Get` Anweisungen. Dieser Code kann andere Berechnungen und Datenmanipulationen zusätzlich zu generieren und den Wert der Eigenschaft zurückgeben enthalten.  
  
3.  Verwenden einer `Return` -Anweisung den Wert der Eigenschaft an den aufrufenden Code zurückgegeben.  
  
 Sie schreiben eine `Get` Prozedur für eine Eigenschaft Lese-/ Schreibzugriff und für eine schreibgeschützte Eigenschaft. Sie müssen nicht definieren eine `Get` Prozedur für eine WriteOnly-Eigenschaft.  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>So erstellen Sie eine Set-Prozedur schreibt, die den Wert einer Eigenschaft  
  
1.  Zwischen der `Property` und `End Property` -Anweisungen Schreiben einer [Set-Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md), gefolgt von einer `End Set` Anweisung.  
  
2.  In der `Set` -Anweisung, befolgen Sie die `Set` Schlüsselwort in einer Parameterliste in Klammern. Diese Parameterliste muss mindestens ein Werteparameter für die vom aufrufenden Code übergebene Wert enthalten. Der Standardname für diesen Wertparameter lautet `Value`, aber Sie können einen anderen Namen verwenden, falls zutreffend. Der Value-Parameter muss den gleichen Datentyp wie die Eigenschaft selbst verfügen.  
  
3.  Platzieren Sie die codeanweisungen zum Speichern eines Werts in der Eigenschaft zwischen den `Set` und `End Set` Anweisungen. Dieser Code kann andere Berechnungen und Datenmanipulationen zusätzlich zu überprüfen, und speichern den Wert der Eigenschaft enthalten.  
  
4.  Verwenden Sie den Value-Parameter, um den Wert des aufrufenden Codes nicht annehmen. Sie können entweder speichern den Wert direkt in einer zuweisungsanweisung, oder sie in einem Ausdruck verwenden, berechnen Sie den internen Wert gespeichert werden soll.  
  
 Sie schreiben eine `Set` Prozedur für eine Eigenschaft Lese-/ Schreibzugriff und für eine WriteOnly-Eigenschaft. Sie müssen nicht definieren eine `Set` Prozedur für eine schreibgeschützte Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Lese-/Schreibzugriff-Eigenschaft, die einen vollständigen Namen als zwei konstituierende Namen, den Vornamen und den Nachnamen des speichert. Wenn der aufrufende Code liest `fullName`die `Get` Prozedur kombiniert die beiden konstituierenden Namen und gibt den vollständigen Namen zurück. Wenn der aufrufende Code einen neuen vollständigen Name weist das `Set` Prozedur versucht, die sie in zwei konstituierende Namen aufzulösen. Wenn sie ein Leerzeichen nicht gefunden wird, wird er alle als den Vornamen gespeichert.  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 Das folgende Beispiel zeigt typische Aufrufe der Eigenschaftenprozeduren `fullName`. Der erste Aufruf legt den Eigenschaftswert fest, und der zweite Aufruf abgerufen.  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)  
 [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)  
 [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)  
 [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
