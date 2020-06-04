---
title: 'Vorgehensweise: Aufrufen einer Eigenschaftenprozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 006961a0f1d4be6b0d52be5bc273dad9733bfe56
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388698"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Gewusst wie: Aufrufen einer Eigenschaftenprozedur (Visual Basic)
Sie rufen eine Eigenschaften Prozedur auf, indem Sie einen Wert in der Eigenschaft speichern oder den Wert abrufen. Sie greifen auf eine Eigenschaft genauso zu, wie Sie auf eine Variable zugreifen.  
  
 Die-Prozedur der Eigenschaft `Set` speichert einen Wert, und `Get` die Prozedur ruft den Wert ab. Diese Prozeduren werden jedoch nicht explizit anhand ihres Namens aufgerufen. Sie verwenden die-Eigenschaft in einer Zuweisungsanweisung oder einem Ausdruck, genauso wie Sie den Wert einer Variablen speichern oder abrufen. Visual Basic führt die Aufrufe der Prozeduren der Eigenschaft aus.  
  
### <a name="to-call-a-propertys-get-procedure"></a>So wenden Sie die Get-Prozedur einer Eigenschaft an  
  
1. Verwenden Sie den Eigenschaftsnamen in einem Ausdruck auf die gleiche Weise wie einen Variablennamen. Sie können eine Eigenschaft überall dort verwenden, wo Sie eine Variable oder eine Konstante verwenden können.  
  
     Oder  
  
     Verwenden Sie den Eigenschaftsnamen nach dem Gleichheits `=` Zeichen () in einer Zuweisungsanweisung.  
  
     Im folgenden Beispiel wird der Wert der- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> Eigenschaft gelesen, wobei die Prozedur implizit aufgerufen wird `Get` .  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Wenn die Eigenschaft Argumente annimmt, befolgen Sie den Eigenschaftsnamen mit Klammern, um die Argumentliste einzuschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas. Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die-Eigenschaft die entsprechenden Parameter definiert.  
  
 Der Wert der Eigenschaft nimmt an dem Ausdruck genau so ein, wie eine Variable oder Konstante, oder er wird in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.  
  
### <a name="to-call-a-propertys-set-procedure"></a>So wenden Sie die Set-Prozedur einer Eigenschaft an  
  
1. Verwenden Sie den Eigenschaftsnamen auf der linken Seite einer Zuweisungsanweisung.  
  
     Im folgenden Beispiel wird der Wert der- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> Eigenschaft festgelegt, der implizit die-Prozedur aufruft `Set` .  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. Wenn die Eigenschaft Argumente annimmt, befolgen Sie den Eigenschaftsnamen mit Klammern, um die Argumentliste einzuschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas. Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die-Eigenschaft die entsprechenden Parameter definiert.  
  
 Der auf der rechten Seite der Zuweisungsanweisung generierte Wert wird in der-Eigenschaft gespeichert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Erstellen einer Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Ablegen eines Werts in eine Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
- [Get-Anweisung](../../../language-reference/statements/get-statement.md)
- [Set-Anweisung](../../../language-reference/statements/set-statement.md)
