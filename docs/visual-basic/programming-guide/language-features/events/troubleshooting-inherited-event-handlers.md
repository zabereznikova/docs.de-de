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
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="f598f-102">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f598f-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>

<span data-ttu-id="f598f-103">In diesem Thema werden häufige Probleme aufgelistet, die bei Ereignis Handlern in geerbten Komponenten auftreten.</span><span class="sxs-lookup"><span data-stu-id="f598f-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="f598f-104">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f598f-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="f598f-105">Der Code im Ereignis Handler wird für jeden-Befehl zweimal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f598f-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
- <span data-ttu-id="f598f-106">Ein geerbter Ereignishandler darf keine [Handles](../../../language-reference/statements/handles-clause.md) -Klausel enthalten.</span><span class="sxs-lookup"><span data-stu-id="f598f-106">An inherited event handler must not include a [Handles](../../../language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="f598f-107">Die-Methode in der-Basisklasse ist bereits dem-Ereignis zugeordnet und wird entsprechend ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f598f-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="f598f-108">Entfernen Sie die- `Handles` Klausel aus der geerbten Methode.</span><span class="sxs-lookup"><span data-stu-id="f598f-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- <span data-ttu-id="f598f-109">Wenn die geerbte Methode kein `Handles` Schlüsselwort hat, vergewissern Sie sich, dass der Code keine zusätzliche [AddHandler-Anweisung](../../../language-reference/statements/addhandler-statement.md) oder zusätzliche Methoden enthält, die das gleiche Ereignis behandeln.</span><span class="sxs-lookup"><span data-stu-id="f598f-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f598f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f598f-110">See also</span></span>

- [<span data-ttu-id="f598f-111">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f598f-111">Events</span></span>](index.md)
