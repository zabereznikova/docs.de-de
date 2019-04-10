---
title: 'Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 5e2676a0880092a78405fe5dafa0469161b85610
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59302932"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)
Sie rufen den Wert einer Eigenschaft, indem Sie den Eigenschaftennamen in einen Ausdruck einschließen.  
  
 Des Eigenschaftenwert `Get` Prozedur ruft den Wert ab, aber Sie rufen sie nicht explizit anhand des Namens. Verwenden Sie die Eigenschaft, genauso wie Sie eine Variable. Visual Basic ermöglicht, die Aufrufe an die Prozeduren der Eigenschaft.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Zum Abrufen eines Werts aus einer Eigenschaft  
  
1. Verwenden Sie die Namen der Eigenschaft in einem Ausdruck die gleiche Weise, die Sie einen Variablennamen verwenden würden. Sie können eine Eigenschaft an einer beliebigen Stelle können Sie eine Variable oder eine Konstante.  
  
     - oder -   
  
     Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung anmelden.  
  
     Das folgende Beispiel liest den Wert der Visual Basic `Now` implizit aufrufen-Eigenschaft der `Get` Verfahren.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft über die entsprechenden Parameter definiert.  
  
 Der Wert der Eigenschaft ist Teil des Ausdrucks wie eine Variable oder Konstante würde, oder es befindet sich in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Erstellen einer Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Ablegen eines Werts in eine Eigenschaft](./how-to-put-a-value-in-a-property.md)
