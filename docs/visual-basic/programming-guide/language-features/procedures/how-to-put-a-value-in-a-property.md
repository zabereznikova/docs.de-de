---
title: 'Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: e6aee5ea36c0315d5b01ae2734d17c9e7dab8e93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341854"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft (Visual Basic)
Sie können einen Wert in einer Eigenschaft speichern, indem Sie die Namen der Eigenschaft auf der linken Seite einer zuweisungsanweisung einfügen.  
  
 Des Eigenschaftenwert `Set` Prozedur speichert einen Wert, aber Sie rufen sie nicht explizit anhand des Namens. Verwenden Sie die Eigenschaft, genauso wie Sie eine Variable. Visual Basic ermöglicht, die Aufrufe an die Prozeduren der Eigenschaft.  
  
### <a name="to-store-a-value-in-a-property"></a>Zum Speichern eines Werts in einer Eigenschaft  
  
1. Verwenden Sie den Eigenschaftennamen, auf der linken Seite einer zuweisungsanweisung.  
  
     Im folgenden Beispiel wird den Wert des Visual Basic `TimeOfDay` Eigenschaft am Mittag implizit Aufrufen seiner `Set` Verfahren.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft über die entsprechenden Parameter definiert.  
  
4. Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Eigenschaft gespeichert.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Erstellen Sie eine Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
