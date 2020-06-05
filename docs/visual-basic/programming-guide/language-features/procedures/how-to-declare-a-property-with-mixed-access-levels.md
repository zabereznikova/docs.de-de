---
title: 'Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen'
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
ms.openlocfilehash: f0f7aba25888544dfcc093906850ae7ada621182
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388244"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen (Visual Basic)
Wenn Sie möchten, dass die `Get` -und- `Set` Prozeduren einer Eigenschaft über unterschiedliche Zugriffsebenen verfügen, können Sie in der- `Property` Anweisung und in der-oder-Anweisung die restriktivere Ebene verwenden `Get` `Set` . Sie verwenden gemischte Zugriffsebenen für eine Eigenschaft, wenn bestimmte Teile des Codes in der Lage sein sollen, den Wert der Eigenschaft zu erhalten, und bestimmte andere Teile des Codes in der Lage sein sollen, den Wert zu ändern.  
  
 Weitere Informationen zu Zugriffsebenen finden Sie unter [Zugriffsebenen in Visual Basic](../declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>So deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen  
  
1. Deklarieren Sie die-Eigenschaft auf normale Weise, und geben Sie die weniger restriktive Zugriffsebene (z `Public` . b.) in der- `Property` Anweisung an.  
  
2. Deklarieren Sie entweder die- `Get` oder die-Prozedur, und geben Sie `Set` die restriktivere Zugriffsebene (z `Friend` . b  
  
3. Geben Sie für die andere Eigenschaften Prozedur keine Zugriffsebene an. Es wird davon ausgegangen, dass die in der Anweisung deklarierte Zugriffsebene `Property` . Sie können den Zugriff nur für eine der Eigenschaften Prozeduren einschränken.  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     Im vorherigen Beispiel `Get` hat die Prozedur denselben `Protected` Zugriff wie die Eigenschaft selbst, während die `Set` Prozedur `Private` Zugriff hat. Eine von abgeleitete Klasse `employee` kann den `salary` Wert lesen, aber nur von der `employee` Klasse kann Sie festgelegt werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweisen](./index.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Erstellen einer Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Ablegen eines Werts in eine Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
