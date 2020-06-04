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
ms.openlocfilehash: de995a13b34678410e2af74b59f2d0c467982b75
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408483"
---
# <a name="addhandler-statement"></a>AddHandler-Anweisung
Ordnet ein Ereignis einem Ereignishandler zur Laufzeit zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Bestandteile  
|||
|---|---|
|event|Der Name des zu behandelnden Ereignisses.|  
|`eventhandler`|Der Name einer Prozedur, die das Ereignis behandelt.|
|||
  
## <a name="remarks"></a>Bemerkungen  
 Mit der `AddHandler` -Anweisung und der- `RemoveHandler` Anweisung können Sie die Ereignis Behandlung jederzeit während der Programmausführung starten und Abbrechen.  
  
 Die Signatur der `eventhandler` Prozedur muss mit der Signatur des Ereignisses identisch sein `event` .  
  
 Mit dem Schlüsselwort `Handles` und der Anweisung `AddHandler` können Sie angeben, dass diese bestimmten Prozeduren bestimmte Ereignisse verarbeiten. Es bestehen jedoch keine Unterschiede. Die Anweisung `AddHandler` verbindet Prozeduren zur Laufzeit mit Ereignissen. Verwenden Sie das Schlüsselwort `Handles`, wenn Sie eine Prozedur definieren, um anzugeben, dass sie ein bestimmtes Ereignis verarbeitet.  Weitere Informationen finden Sie unter [Handles](handles-clause.md).  
  
> [!NOTE]
> Für benutzerdefinierte Ereignisse `AddHandler` Ruft die-Anweisung den- `AddHandler` Accessor des Ereignisses auf. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](event-statement.md).  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Weitere Informationen

- [RemoveHandler-Anweisung](removehandler-statement.md)
- [Ziehpunkte](handles-clause.md)
- [Event-Anweisung](event-statement.md)
- [Ereignisse](../../programming-guide/language-features/events/index.md)
