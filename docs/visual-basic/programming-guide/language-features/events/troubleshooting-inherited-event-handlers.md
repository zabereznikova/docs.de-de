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
ms.openlocfilehash: fd2ef1c25233cc1eaad6bcde68923688393b471d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345107"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Problembehandlung für geerbte Ereignishandler in Visual Basic
In diesem Thema werden häufige Probleme aufgelistet, die bei Ereignis Handlern in geerbten Komponenten auftreten.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Der Code im Ereignis Handler wird für jeden-Befehl zweimal ausgeführt.  
  
- Ein geerbter Ereignishandler darf keine [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) -Klausel enthalten. Die-Methode in der-Basisklasse ist bereits dem-Ereignis zugeordnet und wird entsprechend ausgelöst. Entfernen Sie die `Handles`-Klausel aus der geerbten Methode.  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- Wenn die geerbte Methode nicht über ein `Handles`-Schlüsselwort verfügt, vergewissern Sie sich, dass der Code keine zusätzliche [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) oder zusätzliche Methoden enthält, die das gleiche Ereignis behandeln.  
  
## <a name="see-also"></a>Siehe auch

- [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
