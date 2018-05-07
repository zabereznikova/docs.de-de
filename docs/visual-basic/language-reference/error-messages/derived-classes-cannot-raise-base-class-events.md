---
title: Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 365ce6ece1d964d3fac2a44f7ed4c1e16f44c95d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
Ein Ereignis kann nur vom Deklarationsabschnitt ausgelöst werden, in der sie deklariert ist. Aus diesem Grund kann keine Klasse von einer anderen Klasse, eine Auslösen von Ereignissen von der sie abgeleitet ist.  
  
 **Fehler-ID:** BC30029  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verschieben der `Event` Anweisung oder der `RaiseEvent` Anweisung, sodass sie sich in derselben Klasse befinden.  
  
## <a name="see-also"></a>Siehe auch  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
 [RaiseEvent-Anweisung](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
