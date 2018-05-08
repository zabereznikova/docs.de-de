---
title: '&#39;&lt;Ereignisname&gt; &#39; ist ein Ereignis und kann nicht direkt aufgerufen werden'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 4d8a7d716d2b7c52d1d027a1e7959d981bb0857e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39;&lt;Ereignisname&gt; &#39; ist ein Ereignis und kann nicht direkt aufgerufen werden
"<`eventname`>' ist ein Ereignis und kann daher nicht direkt aufgerufen werden. Verwenden einer `RaiseEvent` Anweisung, um ein Ereignis auszulösen.  
  
 Ein Prozeduraufruf gibt ein Ereignis für den Namen der Prozedur. Ein Ereignishandler ist eine Prozedur, aber das Ereignis selbst ist ein signaling Gerät, die ausgelöst und behandelt werden muss.  
  
 **Fehler-ID:** BC32022  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Verwenden einer `RaiseEvent` Anweisung signalisieren eines Ereignisses und das Aufrufen der Prozedur oder Prozeduren, die sie behandeln.  
  
## <a name="see-also"></a>Siehe auch  
 [RaiseEvent-Anweisung](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
