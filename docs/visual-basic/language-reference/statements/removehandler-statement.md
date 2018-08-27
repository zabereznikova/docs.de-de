---
title: RemoveHandler-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: c1e6ffec64bc01936955a2e94aa9c110b317109f
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925165"
---
# <a name="removehandler-statement"></a>RemoveHandler-Anweisung
Entfernt die Zuordnung zwischen einem Ereignis und einen Ereignishandler.  
  
## <a name="syntax"></a>Syntax  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`event`|Der Name des behandelten Ereignisses.|  
|`eventhandler`|Der Name der Prozedur zurzeit verarbeitet das Ereignis.|  
  
## <a name="remarks"></a>Hinweise  
 Die `AddHandler` und `RemoveHandler` Anweisungen ermöglichen das Starten und Beenden der Ereignisbehandlung für ein bestimmtes Ereignis zu einem beliebigen Zeitpunkt während der programmausführung.  
  
> [!NOTE]
>  Für benutzerdefinierte Ereignisse die `RemoveHandler` -Anweisung ruft des Ereignisses `RemoveHandler` Accessor. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
