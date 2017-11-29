---
title: 'Gewusst wie: Aufrufen einer Eigenschaftenprozedur (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf9080e3c2b23302257499f13e734231f3614495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Gewusst wie: Aufrufen einer Eigenschaftenprozedur (Visual Basic)
Zum Aufrufen einer Eigenschaftenprozedur zum Speichern eines Werts in der Eigenschaft oder der Wert abgerufen. Eine Eigenschaft die gleiche Weise, die Sie Zugriff auf eine Variable zugegriffen.  
  
 Der Eigenschaft `Set` Prozedur speichert einen Wert ein, und die zugehörige `Get` Prozedur ruft den Wert ab. Allerdings sind Sie nicht explizit diese Prozeduren anhand des Namens aufrufen. Verwenden Sie die Eigenschaft in einer zuweisungsanweisung oder einen Ausdruck, wie würden Sie speichern oder des Werts einer Variablen abrufen. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Ruft die Eigenschaftenprozeduren.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Aufrufen einer Eigenschaftenprozedur Get  
  
1.  Verwenden Sie den Namen der Eigenschaft in einem Ausdruck die gleiche Weise wie ein Variablenname. Sie können eine Eigenschaft an einer beliebigen Stelle können Sie eine Variable oder eine Konstante.  
  
     - oder -   
  
     Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung signieren.  
  
     Das folgende Beispiel liest den Wert der <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> Eigenschaft implizit Aufrufen seiner `Get` Prozedur.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.  
  
 Der Wert der Eigenschaft beteiligt ist, in dem Ausdruck ebenso wie eine Variable oder Konstante oder befindet sich in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Rufen Sie eine Eigenschaft auf die Prozedur festzulegen.  
  
1.  Verwenden Sie den Namen der Eigenschaft, auf der linken Seite einer zuweisungsanweisung.  
  
     Im folgenden Beispiel wird den Wert von der <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> Eigenschaft implizit Aufrufen der `Set` Prozedur.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.  
  
 Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Eigenschaft gespeichert.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)  
 [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)  
 [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)  
 [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)  
 [Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set-Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md)
