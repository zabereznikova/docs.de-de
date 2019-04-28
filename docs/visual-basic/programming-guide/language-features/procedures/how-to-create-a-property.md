---
title: 'Vorgehensweise: Erstellen Sie eine Eigenschaft (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: 91f34de36e88724ccab21097bf54a4604f7eee37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665779"
---
# <a name="how-to-create-a-property-visual-basic"></a>Vorgehensweise: Erstellen Sie eine Eigenschaft (Visual Basic)
Sie setzen eine Eigenschaftsdefinition zwischen einem `Property` Anweisung und eine `End Property` Anweisung. Innerhalb dieser Definition, die Sie definieren eine `Get` Verfahren einen `Set` -Prozedur oder beides. Der Eigenschaftenwert Code ist in diesen Prozeduren.  
  
 Die `Get` Prozedur ruft ab, der Wert der Eigenschaft, und die `Set` Prozedur speichert einen Wert. Wenn Sie die Eigenschaft Lese-/Schreibzugriff verfügen soll, müssen Sie beide Verfahren definieren. Für eine schreibgeschützte Eigenschaft, die Sie definieren nur `Get`, und für eine WriteOnly-Eigenschaft, definieren Sie nur `Set`.  
  
### <a name="to-create-a-property"></a>So erstellen Sie eine Eigenschaft  
  
1. Außerhalb einer Eigenschaft oder Prozedur verwendet eine [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md), gefolgt von einer `End Property` Anweisung.  
  
2. Wenn die Eigenschaft Parameter akzeptiert, führen Sie die `Property` Schlüsselwort durch den Namen der Prozedur, und klicken Sie dann auf die Parameterliste in Klammern angegeben.  
  
3. Führen Sie die Klammern mit einer `As` -Klausel, um den Datentyp des Werts der Eigenschaft angeben. Sie müssen den Datentyp für eine WriteOnly-Eigenschaft selbst angeben.  
  
4. Hinzufügen `Get` und `Set` Verfahren nach Bedarf. Sehen Sie die folgenden Anweisungen ein.  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>Zum Erstellen einer Get-Prozedur, die einen Eigenschaftswert abruft.  
  
1. Zwischen der `Property` und `End Property` Schreiben von Anweisungen, eine [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md), gefolgt von einem `End Get` Anweisung. Sie müssen keine Parameter für definieren die `Get` Verfahren.  
  
2. Platzieren Sie den Code-Anweisungen zum Abrufen des Eigenschaftswerts zwischen der `Get` und `End Get` Anweisungen. Dieser Code kann es sich um andere Berechnungen und Datenverarbeitungsaufgaben zusätzlich zum Erstellen und Zurückgeben der Wert der Eigenschaft enthalten.  
  
3. Verwenden einer `Return` -Anweisung den Wert der Eigenschaft an den aufrufenden Code zurückgegeben.  
  
 Müssen Sie schreiben eine `Get` Verfahren für die Schreib-Lese-Eigenschaft und für eine schreibgeschützte Eigenschaft. Sie müssen keine definieren eine `Get` Prozedur für eine WriteOnly-Eigenschaft.  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>So erstellen Sie eine Set-Prozedur schreibt, die den Wert einer Eigenschaft  
  
1. Zwischen der `Property` und `End Property` Schreiben von Anweisungen, eine [Set-Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md), gefolgt von einem `End Set` Anweisung.  
  
2. In der `Set` -Anweisung, befolgen Sie die `Set` Schlüsselwort mit einer Liste von Parametern in Klammern. Dieser Parameter muss mindestens ein Value-Parameter für den Wert, der vom aufrufenden Code übergeben enthalten. Der Standardname für diesen Wertparameter lautet `Value`, aber Sie können einen anderen Namen verwenden, falls zutreffend. Der Value-Parameter müssen den gleichen Datentyp wie die Eigenschaft selbst.  
  
3. Platzieren Sie die codeanweisungen zum Speichern eines Werts in der Eigenschaft zwischen den `Set` und `End Set` Anweisungen. Dieser Code kann es sich um andere Berechnungen und Datenverarbeitungsaufgaben zusätzlich zu überprüfen, und speichern den Wert der Eigenschaft enthalten.  
  
4. Verwenden Sie den Value-Parameter, um den Wert des aufrufenden Codes zu akzeptieren. Sie können diesen Wert direkt in einer zuweisungsanweisung speichern oder verwenden es in einem Ausdruck zum Berechnen des internen Wert gespeichert werden.  
  
 Müssen Sie schreiben eine `Set` Verfahren für die Schreib-Lese-Eigenschaft und für eine WriteOnly-Eigenschaft. Sie müssen keine definieren eine `Set` Prozedur für eine schreibgeschützte Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Lese-/Schreibeigenschaft, die einen vollständigen Namen als zwei enthaltenen Namen, der Vorname und Nachname gespeichert. Wenn der aufrufende Code liest `fullName`, `Get` Prozedur kombiniert die beiden zugehörigen Namen und gibt den vollständigen Namen zurück. Wenn der aufrufende Code einen neuen vollständigen Namen, weist der `Set` Prozedur versucht, die in zwei enthaltenen Namen aufzulösen. Wenn sie ein Leerzeichen nicht gefunden wird, es alle als den ersten Namen gespeichert.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 Das folgende Beispiel zeigt die typischen Aufrufe an die Eigenschaftenprozeduren von `fullName`. Der erste Aufruf legt den Eigenschaftswert fest, und der zweite Aufruf abgerufen.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
