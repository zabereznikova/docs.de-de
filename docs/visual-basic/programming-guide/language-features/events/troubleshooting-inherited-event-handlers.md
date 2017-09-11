---
title: "Problembehandlung für geerbte Ereignishandler in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting events
- inherited events
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f64395975821226d42664bbf78b04120d49a38bc
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="06a27-102">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="06a27-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="06a27-103">In diesem Thema werden häufige Probleme, die mit Ereignishandlern in vererbten Komponenten auftreten.</span><span class="sxs-lookup"><span data-stu-id="06a27-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="06a27-104">Verfahren</span><span class="sxs-lookup"><span data-stu-id="06a27-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="06a27-105">Code im Ereignishandler wird für jeden Aufruf zweimal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="06a27-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="06a27-106">Ein geerbter Ereignishandler darf kein [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="06a27-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="06a27-107">Die Methode in der Basisklasse ist bereits mit dem Ereignis verknüpft und wird entsprechend ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="06a27-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="06a27-108">Entfernen Sie die `Handles` -Klausel aus der geerbten Methode.</span><span class="sxs-lookup"><span data-stu-id="06a27-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     <span data-ttu-id="06a27-109">[!code-vb[VbVbalrEvents&#32;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="06a27-109">[!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]</span></span>  
  
-   <span data-ttu-id="06a27-110">Die geerbte Methode kein `Handles` -Schlüsselwort, stellen Sie sicher, dass Ihr Code keine zusätzliche enthält [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) oder zusätzliche Methoden, die das gleiche Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="06a27-110">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a27-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06a27-111">See Also</span></span>  
 [<span data-ttu-id="06a27-112">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="06a27-112">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
