---
title: '&#39;&lt;EventName&gt; &#39; ist ein Ereignis aus, und nicht direkt aufgerufen werden'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 3efd8c18497ce288e16659db4ca4693d5a3e6acc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54581994"
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39;&lt;EventName&gt; &#39; ist ein Ereignis aus, und nicht direkt aufgerufen werden
' <`eventname`>' ist ein Ereignis und kann daher nicht direkt aufgerufen werden. Verwenden einer `RaiseEvent` Anweisung, um ein Ereignis auszulösen.  
  
 Ein Prozeduraufruf gibt ein Ereignis für den Namen der Prozedur an. Ein Ereignishandler ist eine Prozedur, aber das Ereignis selbst ist ein Signalisierung Gerät ausgelöst und verarbeitet werden muss.  
  
 **Fehler-ID:** BC32022  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Verwenden einer `RaiseEvent` Anweisung, um ein Ereignis zu signalisieren und Aufrufen der Prozedur oder die Prozeduren, die sie verarbeiten.  
  
## <a name="see-also"></a>Siehe auch
- [RaiseEvent-Anweisung](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
