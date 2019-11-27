---
title: AddHandler-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: c110116af75d4fb39c016b8d6afcdb707fa6599b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350192"
---
# <a name="addhandler-statement"></a>AddHandler-Anweisung
Ordnet ein Ereignis einem Ereignishandler zur Laufzeit zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>-Komponenten  
|||
|---|---|
|event|Der Name des zu behandelnden Ereignisses.|  
|`eventhandler`|Der Name einer Prozedur, die das Ereignis behandelt.|
|||
  
## <a name="remarks"></a>Hinweise  
 Die Anweisungen `AddHandler` und `RemoveHandler` ermöglichen das Starten und Abbrechen der Ereignis Behandlung während der Programmausführung.  
  
 Die Signatur der `eventhandler` Prozedur muss mit der Signatur des Ereignis `event`identisch sein.  
  
 Mit dem Schlüsselwort `Handles` und der Anweisung `AddHandler` können Sie angeben, dass diese bestimmten Prozeduren bestimmte Ereignisse verarbeiten. Es bestehen jedoch keine Unterschiede. Die Anweisung `AddHandler` verbindet Prozeduren zur Laufzeit mit Ereignissen. Verwenden Sie das Schlüsselwort `Handles`, wenn Sie eine Prozedur definieren, um anzugeben, dass sie ein bestimmtes Ereignis verarbeitet. Weitere Informationen finden Sie unter [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
> Für benutzerdefinierte Ereignisse ruft die `AddHandler`-Anweisung den `AddHandler` Accessor des Ereignisses auf. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Siehe auch

- [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)
- [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
