---
title: RemoveHandler-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 0d982768707948bd6c616445509e16a462b86f2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597987"
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
|`event`|Der Name des Ereignisses verarbeitet wird.|  
|`eventhandler`|Der Name der Prozedur, die derzeit Behandlung des Ereignisses.|  
  
## <a name="remarks"></a>Hinweise  
 Die `AddHandler` und `RemoveHandler` Anweisungen ermöglichen das Starten und Beenden der Ereignisbehandlung für ein bestimmtes Ereignis zu einem beliebigen Zeitpunkt während der Ausführung des Programms.  
  
> [!NOTE]
>  Für benutzerdefinierte Ereignisse die `RemoveHandler` -Anweisung ruft des Ereignis `RemoveHandler` Accessor. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
