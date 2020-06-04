---
title: Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: c59212a28ba27123a7db9163ff7437c159a3d310
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409698"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
Ein Ereignis kann nur aus dem Deklarations Bereich ausgelöst werden, in dem es deklariert ist. Daher kann eine Klasse keine Ereignisse von einer anderen Klasse, auch von einer Klasse, von der Sie abgeleitet ist, ableiten.  
  
 **Fehler-ID:** BC30029  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verschieben Sie die- `Event` Anweisung oder die- `RaiseEvent` Anweisung so, dass Sie sich in derselben Klasse befinden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Event-Anweisung](../statements/event-statement.md)
- [RaiseEvent-Anweisung](../statements/raiseevent-statement.md)
