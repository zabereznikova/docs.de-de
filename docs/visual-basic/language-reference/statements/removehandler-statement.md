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
ms.openlocfilehash: 177952acf362ccb36a36b5f09b11a1a93dbefa29
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333034"
---
# <a name="removehandler-statement"></a>RemoveHandler-Anweisung
Entfernt die Zuordnung zwischen einem Ereignis und einem Ereignishandler.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`event`|Der Name des behandelten Ereignisses.|  
|`eventhandler`|Der Name der Prozedur, die das Ereignis momentan behandelt.|  
  
## <a name="remarks"></a>Hinweise  
 Die Anweisungen `AddHandler` und `RemoveHandler` ermöglichen das Starten und Abbrechen der Ereignis Behandlung für ein bestimmtes Ereignis während der Programmausführung.  
  
> [!NOTE]
> Für benutzerdefinierte Ereignisse ruft die `RemoveHandler`-Anweisung den `RemoveHandler` Accessor des Ereignisses auf. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Siehe auch

- [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)
- [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
