---
title: 'Gewusst wie: Ablegen eines Werts in eine Eigenschaft (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: 29e68ca2b9436921c81346eb1def2417157aae9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650370"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Gewusst wie: Ablegen eines Werts in eine Eigenschaft (Visual Basic)
Sie speichern einen Wert in einer Eigenschaft an, indem Sie den Namen der Eigenschaft auf der linken Seite einer zuweisungsanweisung.  
  
 Der Eigenschaft `Set` Prozedur speichert einen Wert, aber Sie rufen sie nicht explizit nach Namen. Sie können die Eigenschaft verwenden, wie Sie eine Variable verwenden würden. Visual Basic ermöglicht die Aufrufe an die Eigenschaftenprozeduren.  
  
### <a name="to-store-a-value-in-a-property"></a>Zum Speichern eines Werts in einer Eigenschaft  
  
1.  Verwenden Sie den Namen der Eigenschaft, auf der linken Seite einer zuweisungsanweisung.  
  
     Im folgenden Beispiel wird den Wert der Visual Basic `TimeOfDay` Eigenschaft am Mittag implizit Aufrufen seiner `Set` Prozedur.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.  
  
4.  Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Eigenschaft gespeichert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)  
 [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)  
 [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)  
 [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
