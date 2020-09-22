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
ms.openlocfilehash: a815241f20be12b3b7b4f2b87d50a8965021bbf0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871936"
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
