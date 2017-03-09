---
title: "Troubleshooting Inherited Event Handlers in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "troubleshooting events"
  - "inherited events"
  - "troubleshooting Visual Basic, event handlers"
  - "event handling, troubleshooting"
  - "event handlers, troubleshooting"
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Troubleshooting Inherited Event Handlers in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Unter diesem Thema sind allgemeine Probleme aufgeführt, die sich bei Ereignishandlern in geerbten Komponenten ergeben.  
  
## Arbeitsschritte  
  
#### Code im Ereignishandler wird für jeden Aufruf zweimal ausgeführt  
  
-   Ein geerbter Ereignishandler darf keine [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md)\-Klausel enthalten.  Die Methode in der Basisklasse ist bereits mit dem Ereignis verknüpft und wird entsprechend ausgelöst.  Entfernen Sie die `Handles`\-Klausel aus der geerbten Methode.  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#32)]  
  
-   Wenn die geerbte Methode kein `Handles`\-Schlüsselwort enthält, darf der Code nicht zusätzlich eine [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) oder zusätzliche Methoden zum Behandeln desselben Ereignisses enthalten.  
  
## Siehe auch  
 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)