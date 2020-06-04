---
title: 'Vorgehensweise: Ablegen eines Werts in eine Eigenschaft'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: c0fb3e137010390097a68aea161efcff93839d94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414336"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Gewusst wie: Ablegen eines Werts in eine Eigenschaft (Visual Basic)
Sie speichern einen Wert in einer Eigenschaft, indem Sie den Eigenschaftsnamen auf der linken Seite einer Zuweisungsanweisung platzieren.  
  
 Die-Prozedur der Eigenschaft `Set` speichert einen Wert, Sie wird jedoch nicht explizit anhand des Namens aufgerufen. Sie verwenden die-Eigenschaft wie eine Variable. Visual Basic führt die Aufrufe der Prozeduren der Eigenschaft aus.  
  
### <a name="to-store-a-value-in-a-property"></a>So speichern Sie einen Wert in einer Eigenschaft  
  
1. Verwenden Sie den Eigenschaftsnamen auf der linken Seite einer Zuweisungsanweisung.  
  
     Im folgenden Beispiel wird der Wert der Visual Basic- `TimeOfDay` Eigenschaft auf 12 Uhr festgelegt, und die Prozedur wird implizit aufgerufen `Set` .  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. Wenn die Eigenschaft Argumente annimmt, befolgen Sie den Eigenschaftsnamen mit Klammern, um die Argumentliste einzuschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas. Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die-Eigenschaft die entsprechenden Parameter definiert.  
  
4. Der auf der rechten Seite der Zuweisungsanweisung generierte Wert wird in der-Eigenschaft gespeichert.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Erstellen einer Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
