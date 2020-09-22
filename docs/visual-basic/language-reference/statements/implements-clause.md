---
title: Implements-Klausel
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
ms.openlocfilehash: 7c95cf76b1bac24e2a0f20857b8984d54ebbea85
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866170"
---
# <a name="implements-clause-visual-basic"></a>Implements-Klausel (Visual Basic)

Gibt an, dass ein Klassen-oder Strukturmember die Implementierung für einen in einer Schnittstelle definierten Member bereitstellt.  
  
## <a name="remarks"></a>Bemerkungen  

Das `Implements` Schlüsselwort ist nicht mit der [implementierten Anweisung](implements-statement.md)identisch. Verwenden Sie die- `Implements` Anweisung, um anzugeben, dass eine Klasse oder Struktur eine oder mehrere Schnittstellen implementiert. Anschließend verwenden Sie das- `Implements` Schlüsselwort, um anzugeben, welche Schnittstelle und welcher Member implementiert werden.

Wenn eine Klasse oder Struktur eine Schnittstelle implementiert, muss Sie die `Implements` Anweisung unmittelbar nach der [Klassen Anweisung](class-statement.md) oder [Struktur Anweisung](structure-statement.md)enthalten, und Sie muss alle Member implementieren, die durch die Schnittstelle definiert werden.

## <a name="reimplementation"></a>Neuimplementierung  

In einer abgeleiteten Klasse können Sie einen Schnittstellenmember erneut implementieren, der von der Basisklasse bereits implementiert wurde. Dies unterscheidet sich von der Überschreibung des Basisklassenmembers in den folgenden Punkten:

- Der Basisklassenmember muss nicht [über schreibbar](../modifiers/overridable.md) sein, um neu implementiert werden zu können.
- Sie können den Member mit einem anderen Namen neu implementieren.

Das- `Implements` Schlüsselwort kann in den folgenden Kontexten verwendet werden:

- [Event-Anweisung](event-statement.md)
- [Function-Anweisung](function-statement.md)
- [Property Statement](property-statement.md)
- [Sub-Anweisung](sub-statement.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Implements-Anweisung](implements-statement.md)
- [Interface-Anweisung](interface-statement.md)
- [Class-Anweisung](class-statement.md)
- [Structure Statement](structure-statement.md)
