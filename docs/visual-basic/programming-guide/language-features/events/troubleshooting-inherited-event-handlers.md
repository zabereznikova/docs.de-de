---
title: Problembehandlung für geerbte Ereignishandler in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: e7c56757d18a22a65b4ef8e81d2a05e5f4f4dffc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680196"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Problembehandlung für geerbte Ereignishandler in Visual Basic
Dieses Thema enthält allgemeine Probleme, die bei Ereignishandlern in geerbten Komponenten auftreten.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Code im Ereignishandler wird zweimal für jeden Aufruf ausgeführt.  
  
-   Ein geerbten Ereignishandler dürfen keine [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Klausel. Die Methode in der Basisklasse ist bereits mit dem Ereignis verknüpft und wird entsprechend ausgelöst. Entfernen Sie die `Handles` Klausel aus der geerbten Methode.  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   Wenn die geerbte Methode keine `Handles` -Schlüsselwort, stellen Sie sicher, dass Ihr Code keine zusätzlichen [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) oder zusätzliche Methoden, die das gleiche Ereignis zu behandeln.  
  
## <a name="see-also"></a>Siehe auch
- [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
