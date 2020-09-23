---
title: Problembehandlung für geerbte Ereignishandler
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: d228e916e45054bc088aa633afd9d591e592210d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058000"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Problembehandlung für geerbte Ereignishandler in Visual Basic

In diesem Thema werden häufige Probleme aufgelistet, die bei Ereignis Handlern in geerbten Komponenten auftreten.  
  
## <a name="procedures"></a>Prozeduren  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Der Code im Ereignis Handler wird für jeden-Befehl zweimal ausgeführt.  
  
- Ein geerbter Ereignishandler darf keine [Handles](../../../language-reference/statements/handles-clause.md) -Klausel enthalten. Die-Methode in der-Basisklasse ist bereits dem-Ereignis zugeordnet und wird entsprechend ausgelöst. Entfernen Sie die- `Handles` Klausel aus der geerbten Methode.  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- Wenn die geerbte Methode kein `Handles` Schlüsselwort hat, vergewissern Sie sich, dass der Code keine zusätzliche [AddHandler-Anweisung](../../../language-reference/statements/addhandler-statement.md) oder zusätzliche Methoden enthält, die das gleiche Ereignis behandeln.  
  
## <a name="see-also"></a>Siehe auch

- [Ereignisse](index.md)
