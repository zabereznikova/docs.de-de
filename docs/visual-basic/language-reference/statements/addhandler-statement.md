---
title: AddHandler-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: dd57f63b5741822de7b11c1fafe90452a767aa34
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965643"
---
# <a name="addhandler-statement"></a>AddHandler-Anweisung
Ordnet ein Ereignis ein Ereignishandler zur Laufzeit.  
  
## <a name="syntax"></a>Syntax  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Teile  
|||
|---|---|
|event|Der Name des zu behandelnden Ereignisses.|  
|`eventhandler`|Der Name einer Prozedur, die das Ereignis behandelt.|
|||
  
## <a name="remarks"></a>Hinweise  
 Die `AddHandler` und `RemoveHandler` Anweisungen ermöglichen das Starten und beenden die Behandlung von Ereignissen zu einem beliebigen Zeitpunkt während der programmausführung.  
  
 Die Signatur der `eventhandler` Verfahren muss der Signatur des Ereignisses entsprechen `event`.  
  
 Mit dem Schlüsselwort `Handles` und der Anweisung `AddHandler` können Sie angeben, dass diese bestimmten Prozeduren bestimmte Ereignisse verarbeiten. Es bestehen jedoch keine Unterschiede. Die Anweisung `AddHandler` verbindet Prozeduren zur Laufzeit mit Ereignissen. Verwenden Sie das Schlüsselwort `Handles`, wenn Sie eine Prozedur definieren, um anzugeben, dass sie ein bestimmtes Ereignis verarbeitet.  Weitere Informationen finden Sie unter [behandelt](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
>  Für benutzerdefinierte Ereignisse die `AddHandler` -Anweisung ruft des Ereignisses `AddHandler` Accessor. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Siehe auch
- [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)
- [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
