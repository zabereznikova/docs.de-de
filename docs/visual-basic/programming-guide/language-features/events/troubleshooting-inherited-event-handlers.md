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
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="04aea-102">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04aea-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="04aea-103">Dieses Thema enthält allgemeine Probleme, die bei Ereignishandlern in geerbten Komponenten auftreten.</span><span class="sxs-lookup"><span data-stu-id="04aea-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="04aea-104">Verfahren</span><span class="sxs-lookup"><span data-stu-id="04aea-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="04aea-105">Code im Ereignishandler wird zweimal für jeden Aufruf ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="04aea-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="04aea-106">Ein geerbten Ereignishandler dürfen keine [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="04aea-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="04aea-107">Die Methode in der Basisklasse ist bereits mit dem Ereignis verknüpft und wird entsprechend ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="04aea-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="04aea-108">Entfernen Sie die `Handles` Klausel aus der geerbten Methode.</span><span class="sxs-lookup"><span data-stu-id="04aea-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   <span data-ttu-id="04aea-109">Wenn die geerbte Methode keine `Handles` -Schlüsselwort, stellen Sie sicher, dass Ihr Code keine zusätzlichen [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) oder zusätzliche Methoden, die das gleiche Ereignis zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="04aea-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04aea-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04aea-110">See also</span></span>
- [<span data-ttu-id="04aea-111">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="04aea-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
