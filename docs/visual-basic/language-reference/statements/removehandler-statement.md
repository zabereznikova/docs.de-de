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
ms.openlocfilehash: 3514a79f2430b148e6a3727b83029b4e207a677b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404251"
---
# <a name="removehandler-statement"></a>RemoveHandler-Anweisung
Entfernt die Zuordnung zwischen einem Ereignis und einem Ereignishandler.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`event`|Der Name des behandelten Ereignisses.|  
|`eventhandler`|Der Name der Prozedur, die das Ereignis momentan behandelt.|  
  
## <a name="remarks"></a>Bemerkungen  
 Mit der `AddHandler` -Anweisung und der- `RemoveHandler` Anweisung können Sie die Ereignis Behandlung für ein bestimmtes Ereignis zu einem beliebigen Zeitpunkt während der Programmausführung starten und Abbrechen.  
  
> [!NOTE]
> Für benutzerdefinierte Ereignisse `RemoveHandler` Ruft die-Anweisung den- `RemoveHandler` Accessor des Ereignisses auf. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](event-statement.md).  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Weitere Informationen

- [AddHandler-Anweisung](addhandler-statement.md)
- [Ziehpunkte](handles-clause.md)
- [Event-Anweisung](event-statement.md)
- [Ereignisse](../../programming-guide/language-features/events/index.md)
