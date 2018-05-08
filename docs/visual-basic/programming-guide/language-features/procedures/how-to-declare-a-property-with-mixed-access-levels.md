---
title: 'Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen (Visual Basic)'
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
ms.openlocfilehash: 8d25086fe6f8b5f5300006466ef49782cb065edf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen (Visual Basic)
Gegebenenfalls die `Get` und `Set` Prozeduren in einer Eigenschaft, die über verschiedene Zugriffsebenen verfügen, können Sie die restriktivere Ebene in der `Property` -Anweisung und die restriktivere Ebene entweder in der `Get` oder `Set` -Anweisung. Verwenden Sie gemischten Zugriffsebenen auf eine Eigenschaft, wenn Sie bestimmte Teile des Codes, um den Wert der Eigenschaft abrufen zu können, und bestimmte andere Teile des Codes in der Lage, zum Ändern des Werts sein möchten.  
  
 Weitere Informationen zu Zugriffsebenen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen  
  
1.  Deklarieren Sie die Eigenschaft auf die übliche Weise, und geben Sie die weniger restriktive Zugriffsebene (z. B. `Public`) in der `Property` Anweisung.  
  
2.  Deklarieren Sie entweder die `Get` oder `Set` Prozedur die stärker einschränkende Zugriffsebene angeben (z. B. `Friend`).  
  
3.  Geben Sie eine Zugriffsebene auf die anderen Eigenschaftenprozedur. Es wird davon ausgegangen, die Zugriffsebene, die deklariert wird, der `Property` Anweisung. Sie können den Zugriff auf nur einer der Eigenschaftenprozeduren einschränken.  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     Im vorherigen Beispiel der `Get` Prozedur hat die gleiche `Protected` Zugriff wie die Eigenschaft selbst, während die `Set` Prozedur umfasst `Private` Zugriff. Eine abgeleitete Klasse `employee` lesen können die `salary` Wert, sondern nur die `employee` Klasse festlegen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)  
 [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)  
 [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)  
 [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)  
 [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
