---
title: 'Gewusst wie: Aufrufen einer Eigenschaftenprozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 52e6c62ffb81c480ccc1abf06f04eb780218dbf1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340551"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Gewusst wie: Aufrufen einer Eigenschaftenprozedur (Visual Basic)
Sie rufen eine Eigenschaften Prozedur auf, indem Sie einen Wert in der Eigenschaft speichern oder den Wert abrufen. Sie greifen auf eine Eigenschaft genauso zu, wie Sie auf eine Variable zugreifen.  
  
 Die `Set` Prozedur der Eigenschaft speichert einen Wert, und die `Get` Prozedur ruft den Wert ab. Diese Prozeduren werden jedoch nicht explizit anhand ihres Namens aufgerufen. Sie verwenden die-Eigenschaft in einer Zuweisungsanweisung oder einem Ausdruck, genauso wie Sie den Wert einer Variablen speichern oder abrufen. Visual Basic führt die Aufrufe der Prozeduren der Eigenschaft aus.  
  
### <a name="to-call-a-propertys-get-procedure"></a>So wenden Sie die Get-Prozedur einer Eigenschaft an  
  
1. Verwenden Sie den Eigenschaftsnamen in einem Ausdruck auf die gleiche Weise wie einen Variablennamen. Sie können eine Eigenschaft überall dort verwenden, wo Sie eine Variable oder eine Konstante verwenden können.  
  
     \- oder -  
  
     Verwenden Sie den Eigenschaftsnamen nach dem Gleichheitszeichen (`=`) in einer Zuweisungsanweisung.  
  
     Im folgenden Beispiel wird der Wert der <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>-Eigenschaft gelesen, wobei die `Get` Prozedur implizit aufgerufen wird.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Wenn die Eigenschaft Argumente annimmt, befolgen Sie den Eigenschaftsnamen mit Klammern, um die Argumentliste einzuschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas. Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die-Eigenschaft die entsprechenden Parameter definiert.  
  
 Der Wert der Eigenschaft nimmt an dem Ausdruck genau so ein, wie eine Variable oder Konstante, oder er wird in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.  
  
### <a name="to-call-a-propertys-set-procedure"></a>So wenden Sie die Set-Prozedur einer Eigenschaft an  
  
1. Verwenden Sie den Eigenschaftsnamen auf der linken Seite einer Zuweisungsanweisung.  
  
     Im folgenden Beispiel wird der Wert der <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>-Eigenschaft festgelegt, wobei der `Set` Prozedur implizit aufgerufen wird.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. Wenn die Eigenschaft Argumente annimmt, befolgen Sie den Eigenschaftsnamen mit Klammern, um die Argumentliste einzuschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas. Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die-Eigenschaft die entsprechenden Parameter definiert.  
  
 Der auf der rechten Seite der Zuweisungsanweisung generierte Wert wird in der-Eigenschaft gespeichert.  
  
## <a name="see-also"></a>Siehe auch

- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)
- [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Vorgehensweise: Deklarieren und Abrufen einer Standard Eigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
- [Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md)
- [Set-Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md)
