---
title: "Problembehandlung für geerbte Ereignishandler in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0e8f0b669566bbee6530931bfba9808fad0c085
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Problembehandlung für geerbte Ereignishandler in Visual Basic
Dieses Thema enthält allgemeine Probleme, die mit Ereignishandlern in vererbten Komponenten auftreten.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Code im Ereignishandler wird zweimal für jeden Aufruf ausgeführt.  
  
-   Ein geerbter Ereignishandler dürfen keine [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Klausel. Die Methode in der Basisklasse ist bereits mit dem Ereignis zugeordnet und wird entsprechend ausgelöst. Entfernen Sie die `Handles` -Klausel aus der geerbte Methode.  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   Wenn die geerbte Methode keine `Handles` -Schlüsselwort, stellen Sie sicher, dass Ihr Code keine zusätzliche enthält [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) oder zusätzliche Methoden, die das gleiche Ereignis zu behandeln.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
