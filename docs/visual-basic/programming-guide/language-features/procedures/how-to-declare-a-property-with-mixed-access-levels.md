---
title: 'Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: aa0c71621b72d01067db0749a0678b706d13fbfa
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832124"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen (Visual Basic)
Wenn Sie möchten die `Get` und `Set` Prozeduren für eine Eigenschaft, um unterschiedliche Zugriffsebenen haben, können Sie die weniger restriktive Ebene in der `Property` -Anweisung und die weniger einschränkende Zugriffsebene in einem der `Get` oder `Set` -Anweisung. Verwenden Sie gemischten Zugriffsebenen auf eine Eigenschaft, wenn Sie bestimmte Teile des Codes, um den Wert der Eigenschaft abrufen zu können, und bestimmte andere Teile des Codes, um den Wert ändern zu können möchten.  
  
 Weitere Informationen zu Zugriffsebenen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>Um eine Eigenschaft mit gemischten Zugriffsebenen zu deklarieren.  
  
1.  Deklarieren Sie die Eigenschaft auf die übliche Weise, und geben Sie die weniger restriktive Zugriffsebene (z. B. `Public`) in der `Property` Anweisung.  
  
2.  Deklarieren Sie entweder die `Get` oder `Set` Prozedur, die stärker einschränkende Zugriffsebene angeben (z. B. `Friend`).  
  
3.  Geben Sie eine Zugriffsebene nicht auf die anderen Eigenschaftenprozedur. Es wird davon ausgegangen, die Zugriffsebene in deklariert die `Property` Anweisung. Sie können den Zugriff auf nur einer der Eigenschaftenprozeduren einschränken.  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     Im vorherigen Beispiel die `Get` Prozedur verfügt über die gleiche `Protected` Zugriff wie die Eigenschaft selbst, während die `Set` Prozedur `Private` Zugriff. Eine abgeleitete Klasse `employee` erhalten die `salary` Wert, aber nur die `employee` -Klasse festgelegt werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Erstellen Sie eine Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
