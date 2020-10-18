---
title: Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 7b86420466d77a6aa45b1201a9375b4433e4b5ec
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163440"
---
# <a name="bc30029-derived-classes-cannot-raise-base-class-events"></a>BC30029: abgeleitete Klassen können keine Basisklassen Ereignisse hervorrufen

Ein Ereignis kann nur aus dem Deklarations Bereich ausgelöst werden, in dem es deklariert ist. Daher kann eine Klasse keine Ereignisse von einer anderen Klasse, auch von einer Klasse, von der Sie abgeleitet ist, ableiten.

 **Fehler-ID:** BC30029

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Verschieben Sie die- `Event` Anweisung oder die- `RaiseEvent` Anweisung so, dass Sie sich in derselben Klasse befinden.

## <a name="see-also"></a>Siehe auch

- [Event-Anweisung](../statements/event-statement.md)
- [RaiseEvent-Anweisung](../statements/raiseevent-statement.md)
