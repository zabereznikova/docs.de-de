---
title: 'Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen'
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
ms.openlocfilehash: d74e23f33fbf7d9d29ab84b9b1bd4fc08863ac48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349696"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen (Visual Basic)
Wenn Sie möchten, dass die `Get`-und `Set` Prozeduren einer Eigenschaft über unterschiedliche Zugriffsebenen verfügen, können Sie in der `Property`-Anweisung die restriktivere Ebene und die restriktivere Ebene in der `Get`-oder `Set`-Anweisung verwenden. Sie verwenden gemischte Zugriffsebenen für eine Eigenschaft, wenn bestimmte Teile des Codes in der Lage sein sollen, den Wert der Eigenschaft zu erhalten, und bestimmte andere Teile des Codes in der Lage sein sollen, den Wert zu ändern.  
  
 Weitere Informationen zu Zugriffsebenen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>So deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen  
  
1. Deklarieren Sie die Eigenschaft auf normale Weise, und geben Sie die weniger restriktive Zugriffsebene (z. b. `Public`) in der `Property`-Anweisung an.  
  
2. Deklarieren Sie entweder die `Get` oder die `Set` Prozedur, und geben Sie die restriktivere Zugriffsebene (z. b. `Friend`) an  
  
3. Geben Sie für die andere Eigenschaften Prozedur keine Zugriffsebene an. Dabei wird die in der `Property`-Anweisung deklarierte Zugriffsebene angenommen. Sie können den Zugriff nur für eine der Eigenschaften Prozeduren einschränken.  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     Im vorherigen Beispiel hat die `Get` Prozedur denselben `Protected` Zugriff wie die Eigenschaft selbst, während die `Set` Prozedur `Private` Zugriff hat. Eine von `employee` abgeleitete Klasse kann den `salary` Wert lesen, aber nur die `employee` Klasse kann Sie festlegen.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)
- [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Vorgehensweise: Deklarieren und Abrufen einer Standard Eigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
