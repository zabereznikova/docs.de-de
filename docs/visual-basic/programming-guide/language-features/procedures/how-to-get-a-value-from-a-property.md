---
title: 'Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 2c92cd4a869acbb7c8c52fbf4117112967386498
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387893"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Gewusst wie: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)
Sie rufen den Wert einer Eigenschaft ab, indem Sie den Eigenschaftsnamen in einen Ausdruck einschließen.  
  
 Die-Prozedur der Eigenschaft `Get` Ruft den Wert ab, aber Sie rufen ihn nicht explizit anhand des Namens auf. Sie verwenden die-Eigenschaft wie eine Variable. Visual Basic führt die Aufrufe der Prozeduren der Eigenschaft aus.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>So rufen Sie einen Wert aus einer Eigenschaft ab  
  
1. Verwenden Sie den Eigenschaftsnamen in einem Ausdruck auf die gleiche Weise wie einen Variablennamen. Sie können eine Eigenschaft überall dort verwenden, wo Sie eine Variable oder eine Konstante verwenden können.  
  
     Oder  
  
     Verwenden Sie den Eigenschaftsnamen nach dem Gleichheits `=` Zeichen () in einer Zuweisungsanweisung.  
  
     Im folgenden Beispiel wird der Wert der Visual Basic- `Now` Eigenschaft gelesen, wobei die Prozedur implizit aufgerufen wird `Get` .  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Wenn die Eigenschaft Argumente annimmt, befolgen Sie den Eigenschaftsnamen mit Klammern, um die Argumentliste einzuschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas. Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die-Eigenschaft die entsprechenden Parameter definiert.  
  
 Der Wert der Eigenschaft nimmt an dem Ausdruck genau so ein, wie eine Variable oder Konstante, oder er wird in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweisen](./index.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Erstellen einer Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Ablegen eines Werts in eine Eigenschaft](./how-to-put-a-value-in-a-property.md)
