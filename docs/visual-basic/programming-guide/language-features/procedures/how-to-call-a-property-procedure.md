---
title: 'Gewusst wie: Aufrufen einer Eigenschaftenprozedur (Visual Basic) | Microsoft-Dokumentation'
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
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], property procedures
- procedure calls, property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
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
ms.openlocfilehash: 7dd3d53f602886f65c951de34b915b2672b1a817
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Gewusst wie: Aufrufen einer Eigenschaftenprozedur (Visual Basic)
Sie aufrufen eine Eigenschaftenprozedur zum Speichern eines Werts in der Eigenschaft oder deren Wert abrufen. Sie Zugriff auf eine Eigenschaft die gleiche Weise, die Sie auf eine Variable zugreifen.  
  
 Der Eigenschaft `Set` -Prozedur einen Wert speichert und dessen `Get` Prozedur ruft den Wert ab. Jedoch Sie nicht explizit diese Prozeduren anhand des Namens aufrufen. Wie würden Sie speichern oder den Wert einer Variablen abzurufen, verwenden Sie die Eigenschaft in eine Zuweisung oder einen Ausdruck. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Ruft die Prozeduren der Eigenschaft.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Aufrufen einer Eigenschaftenprozedur Get  
  
1.  Verwenden Sie den Eigenschaftennamen in einem Ausdruck die gleiche Weise wie ein Variablenname. Sie können eine Eigenschaft überall dort verwenden, eine Variable oder eine Konstante.  
  
     - oder -   
  
     Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) melden Sie sich eine Zuweisung.  
  
     Das folgende Beispiel liest den Wert der <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>Eigenschaft implizit aufgerufen seine `Get` Prozedur.</xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
  
     [!code-vb[VbVbalrDateProperties&4;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Wenn die Eigenschaft Argumente annimmt, führen Sie die Namen der Eigenschaft in Klammern, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt. Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.  
  
 Der Wert der Eigenschaft hat im Ausdruck wie eine Variable oder Konstante, oder wird in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Zum Aufrufen einer Eigenschaft der Prozedur festgelegt.  
  
1.  Verwenden Sie den Eigenschaftsnamen auf der linken Seite einer Zuweisung-Anweisung.  
  
     Im folgenden Beispiel wird der Wert der <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>Eigenschaft implizit aufgerufen der `Set` Prozedur.</xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
  
     [!code-vb[VbVbcnProcedures&#11;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Wenn die Eigenschaft Argumente annimmt, führen Sie die Namen der Eigenschaft in Klammern, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt. Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.  
  
 Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Eigenschaft gespeichert.  
  
## <a name="see-also"></a>Siehe auch  
 [Property-Prozeduren](./property-procedures.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)   
 [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)   
 [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)   
 [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)   
 [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)   
 [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)   
 [Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md)   
 [Set-Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md)
