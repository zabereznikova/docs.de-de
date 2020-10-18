---
title: <eventname> ist ein Ereignis und kann nicht direkt aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 246cb92daa2c838c95f695542f33cf02af42764d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161984"
---
# <a name="bc32022-eventname-is-an-event-and-cannot-be-called-directly"></a>BC32022: " \<eventname> " ist ein Ereignis und kann nicht direkt aufgerufen werden.

"<`eventname`>" ist ein Ereignis und kann daher nicht direkt aufgerufen werden. Verwenden Sie eine- `RaiseEvent` Anweisung, um ein Ereignis zu erhöhen.

 Ein Prozedur aufruame gibt ein Ereignis für den Prozedur Namen an. Ein Ereignishandler ist eine Prozedur, aber das Ereignis selbst ist ein Signalisierungs Gerät, das ausgelöst und behandelt werden muss.

 **Fehler-ID:** BC32022

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Verwenden `RaiseEvent` Sie eine-Anweisung, um ein Ereignis zu signalisieren und die Prozeduren und Prozeduren aufzurufen, die

## <a name="see-also"></a>Siehe auch

- [RaiseEvent-Anweisung](../statements/raiseevent-statement.md)
