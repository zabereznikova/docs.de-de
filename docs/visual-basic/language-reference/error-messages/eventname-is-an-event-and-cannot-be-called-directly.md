---
title: <eventname> ist ein Ereignis und kann nicht direkt aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 3366bc215a45cd7de9dc2de285758a78144df509
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874319"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a>\<eventname> ist ein Ereignis und kann nicht direkt aufgerufen werden.

"<`eventname`>" ist ein Ereignis und kann daher nicht direkt aufgerufen werden. Verwenden Sie eine- `RaiseEvent` Anweisung, um ein Ereignis zu erhöhen.  
  
 Ein Prozedur aufruame gibt ein Ereignis für den Prozedur Namen an. Ein Ereignishandler ist eine Prozedur, aber das Ereignis selbst ist ein Signalisierungs Gerät, das ausgelöst und behandelt werden muss.  
  
 **Fehler-ID:** BC32022  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Verwenden `RaiseEvent` Sie eine-Anweisung, um ein Ereignis zu signalisieren und die Prozeduren und Prozeduren aufzurufen, die  
  
## <a name="see-also"></a>Weitere Informationen

- [RaiseEvent-Anweisung](../statements/raiseevent-statement.md)
