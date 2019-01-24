---
title: Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 3cb61a40e4522695b876d85f67dac1a109d3c3e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595863"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
Ein Ereignis kann nur aus der Deklaration ausgelöst werden, in dem sie deklariert ist. Eine Klasse kann nicht aus diesem Grund Ereignisse aus einer beliebigen anderen Klasse, selbst eine auslösen, von dem er abgeleitet ist.  
  
 **Fehler-ID:** BC30029  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verschieben der `Event` Anweisung oder der `RaiseEvent` Anweisung, sodass sie sich in derselben Klasse befinden.  
  
## <a name="see-also"></a>Siehe auch
- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)
- [RaiseEvent-Anweisung](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
