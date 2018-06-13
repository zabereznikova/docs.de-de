---
title: Implements-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 1e34245ac528e9e2463afbfd07dff91bf693830b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603404"
---
# <a name="implements-clause-visual-basic"></a>Implements-Klausel (Visual Basic)
Gibt an, dass die Implementierung für einen in einer Schnittstelle definierten Member einer Klasse oder Struktur-Element bereitstellt.  
  
## <a name="remarks"></a>Hinweise  
Die `Implements` Schlüsselwort ist nicht identisch mit der [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md). Verwenden Sie die `Implements` Anweisung, um anzugeben, dass eine Klasse oder Struktur eine oder mehrere Schnittstellen implementiert, und klicken Sie dann für jedes Element Sie verwenden die `Implements` Schlüsselwort an, welche Schnittstelle und welcher Member implementiert.

Wenn eine Klasse oder Struktur eine Schnittstelle implementiert, muss sie enthalten die `Implements` Anweisung unmittelbar nach der [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md) oder [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md), und sie müssen alle Member implementiert durch die Schnittstelle definiert.

## <a name="reimplementation"></a>Neuimplementierung  
In einer abgeleiteten Klasse kann einen Schnittstellenmember erneut implementieren, den die Basisklasse bereits implementiert wurde. Dies unterscheidet sich von überschreiben die Member der Basisklasse in folgender Hinsicht:

- Member der Basisklasse muss nicht [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) , um erneut implementiert werden.
- Sie können das Element mit einem anderen Namen erneut implementieren.

Die `Implements` -Schlüsselwort kann in den folgenden Kontexten verwendet werden:
- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)
