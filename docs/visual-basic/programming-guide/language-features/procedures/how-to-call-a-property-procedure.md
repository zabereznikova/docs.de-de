---
title: 'Vorgehensweise: Aufrufen einer Eigenschaftenprozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: d05c1b63f5567ade9935f80ecc022eb4840e0af0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318746"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Vorgehensweise: Aufrufen einer Eigenschaftenprozedur (Visual Basic)
Sie aufrufen eine Eigenschaftenprozedur zum Speichern eines Werts in der Eigenschaft oder der Wert abgerufen. Sie Zugriff auf eine Eigenschaft die gleiche Weise, die Sie eine Variable zuzugreifen.  
  
 Des Eigenschaftenwert `Set` Prozedur speichert einen Wert ein, und die zugehörige `Get` Prozedur ruft den Wert ab. Allerdings sind Sie nicht explizit dazu anhand des Namens aufrufen. Verwenden Sie die Eigenschaft in einer zuweisungsanweisung oder einem Ausdruck, wie würden Sie speichern oder des Werts einer Variablen abrufen. Visual Basic ermöglicht, die Aufrufe an die Prozeduren der Eigenschaft.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Zum Aufrufen einer Eigenschaft Get-Prozedur  
  
1. Verwenden Sie die Namen der Eigenschaft in einem Ausdruck die gleiche Weise, die Sie einen Variablennamen verwenden würden. Sie können eine Eigenschaft an einer beliebigen Stelle können Sie eine Variable oder eine Konstante.  
  
     - oder -   
  
     Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung anmelden.  
  
     Das folgende Beispiel liest den Wert des der <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> implizit aufrufen-Eigenschaft der `Get` Prozedur.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft über die entsprechenden Parameter definiert.  
  
 Der Wert der Eigenschaft ist Teil des Ausdrucks wie eine Variable oder Konstante würde, oder es befindet sich in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Um eine Eigenschaft Aufrufen der Prozedur festzulegen.  
  
1. Verwenden Sie den Eigenschaftennamen, auf der linken Seite einer zuweisungsanweisung.  
  
     Im folgenden Beispiel wird den Wert des der <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> implizit aufrufen-Eigenschaft der `Set` Verfahren.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft über die entsprechenden Parameter definiert.  
  
 Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Eigenschaft gespeichert.  
  
## <a name="see-also"></a>Siehe auch

- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Erstellen einer Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Ablegen eines Werts in eine Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
- [Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md)
- [Set-Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md)
