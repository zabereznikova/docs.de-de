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
ms.openlocfilehash: 704ca667a6d14ade7be0192e872f5e40791cb864
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830187"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="d974f-102">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d974f-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="d974f-103">Dieses Thema enthält allgemeine Probleme, die bei Ereignishandlern in geerbten Komponenten auftreten.</span><span class="sxs-lookup"><span data-stu-id="d974f-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d974f-104">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d974f-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="d974f-105">Code im Ereignishandler wird zweimal für jeden Aufruf ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d974f-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="d974f-106">Ein geerbten Ereignishandler dürfen keine [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="d974f-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="d974f-107">Die Methode in der Basisklasse ist bereits mit dem Ereignis verknüpft und wird entsprechend ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d974f-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="d974f-108">Entfernen Sie die `Handles` Klausel aus der geerbten Methode.</span><span class="sxs-lookup"><span data-stu-id="d974f-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
-   <span data-ttu-id="d974f-109">Wenn die geerbte Methode keine `Handles` -Schlüsselwort, stellen Sie sicher, dass Ihr Code keine zusätzlichen [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) oder zusätzliche Methoden, die das gleiche Ereignis zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="d974f-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d974f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d974f-110">See also</span></span>

- [<span data-ttu-id="d974f-111">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="d974f-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
