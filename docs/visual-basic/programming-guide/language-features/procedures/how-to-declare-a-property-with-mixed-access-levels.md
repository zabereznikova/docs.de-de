---
title: 'Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 90fe20303f6f2ed692e54e44ee8cc65897531543
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
