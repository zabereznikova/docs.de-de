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
ms.openlocfilehash: 91bded2f1249bfcbeeca28419ee9bcec819babf6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965423"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="9ea25-102">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ea25-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="9ea25-103">Dieses Thema enthält allgemeine Probleme, die bei Ereignishandlern in geerbten Komponenten auftreten.</span><span class="sxs-lookup"><span data-stu-id="9ea25-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="9ea25-104">Verfahren</span><span class="sxs-lookup"><span data-stu-id="9ea25-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="9ea25-105">Code im Ereignishandler wird zweimal für jeden Aufruf ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9ea25-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="9ea25-106">Ein geerbten Ereignishandler dürfen keine [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="9ea25-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="9ea25-107">Die Methode in der Basisklasse ist bereits mit dem Ereignis verknüpft und wird entsprechend ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9ea25-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="9ea25-108">Entfernen Sie die `Handles` Klausel aus der geerbten Methode.</span><span class="sxs-lookup"><span data-stu-id="9ea25-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
-   <span data-ttu-id="9ea25-109">Wenn die geerbte Methode keine `Handles` -Schlüsselwort, stellen Sie sicher, dass Ihr Code keine zusätzlichen [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) oder zusätzliche Methoden, die das gleiche Ereignis zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="9ea25-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea25-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ea25-110">See also</span></span>
- [<span data-ttu-id="9ea25-111">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="9ea25-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
