---
title: Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0233a1584c5e871506b5c4762e98874c343f19b8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874488"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Abgeleitete Klassen können keine Basisklassenereignisse auslösen.

Ein Ereignis kann nur aus dem Deklarations Bereich ausgelöst werden, in dem es deklariert ist. Daher kann eine Klasse keine Ereignisse von einer anderen Klasse, auch von einer Klasse, von der Sie abgeleitet ist, ableiten.  
  
 **Fehler-ID:** BC30029  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verschieben Sie die- `Event` Anweisung oder die- `RaiseEvent` Anweisung so, dass Sie sich in derselben Klasse befinden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Event-Anweisung](../statements/event-statement.md)
- [RaiseEvent-Anweisung](../statements/raiseevent-statement.md)
