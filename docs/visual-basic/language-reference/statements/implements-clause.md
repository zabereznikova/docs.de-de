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
ms.openlocfilehash: dcd20f21a989c327dcfcf27d5638d500b6e4b6da
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929315"
---
# <a name="implements-clause-visual-basic"></a>Implements-Klausel (Visual Basic)
Gibt an, dass ein Klassen-oder Strukturmember die Implementierung für einen in einer Schnittstelle definierten Member bereitstellt.  
  
## <a name="remarks"></a>Hinweise  
Das `Implements` Schlüsselwort ist nicht mit der [implementierten Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)identisch. Verwenden Sie die `Implements` -Anweisung, um anzugeben, dass eine Klasse oder Struktur eine oder mehrere Schnittstellen implementiert. Anschließend verwenden Sie das `Implements` -Schlüsselwort, um anzugeben, welche Schnittstelle und welcher Member implementiert werden.

Wenn eine Klasse oder Struktur eine Schnittstelle implementiert, muss Sie die `Implements` Anweisung unmittelbar nach der [Klassen Anweisung](../../../visual-basic/language-reference/statements/class-statement.md) oder [Struktur Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)enthalten, und Sie muss alle Member implementieren, die durch die Schnittstelle definiert werden.

## <a name="reimplementation"></a>Neuimplementierung  
In einer abgeleiteten Klasse können Sie einen Schnittstellenmember erneut implementieren, der von der Basisklasse bereits implementiert wurde. Dies unterscheidet sich von der Überschreibung des Basisklassenmembers in den folgenden Punkten:

- Der Basisklassenmember muss nicht [über schreibbar](../../../visual-basic/language-reference/modifiers/overridable.md) sein, um neu implementiert werden zu können.
- Sie können den Member mit einem anderen Namen neu implementieren.

Das `Implements` -Schlüsselwort kann in den folgenden Kontexten verwendet werden:

- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)
- [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)
