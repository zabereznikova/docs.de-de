---
title: Keine Maus vorhanden
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: ceb850d98d29c232da304fbdfaddf5611714ef1a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078852"
---
# <a name="no-mouse-is-present"></a><span data-ttu-id="00a04-102">Keine Maus vorhanden</span><span class="sxs-lookup"><span data-stu-id="00a04-102">No mouse is present</span></span>

<span data-ttu-id="00a04-103">Eine der Eigenschaften des `My.Computer.Mouse` -Objekts wurde aufgerufen, aber der Computer verfügt über keine Maus, oder es ist kein Port für die Maus installiert.</span><span class="sxs-lookup"><span data-stu-id="00a04-103">One of the properties of the `My.Computer.Mouse` object was called, but the computer has no mouse or mouse port installed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="00a04-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="00a04-104">To correct this error</span></span>  
  
- <span data-ttu-id="00a04-105">Fügen Sie rund um den Aufruf der Eigenschaft des `Try...Catch` -Objekts einen `My.Computer.Mouse` -Block hinzu.</span><span class="sxs-lookup"><span data-stu-id="00a04-105">Add a `Try...Catch` block around the call to the property of the `My.Computer.Mouse` object.</span></span>  
  
     <span data-ttu-id="00a04-106">\- oder -</span><span class="sxs-lookup"><span data-stu-id="00a04-106">— or —</span></span>  
  
- <span data-ttu-id="00a04-107">Installieren Sie auf dem Computer eine Maus.</span><span class="sxs-lookup"><span data-stu-id="00a04-107">Install a mouse on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a04-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00a04-108">See also</span></span>

- [<span data-ttu-id="00a04-109">My.Computer.Mouse</span><span class="sxs-lookup"><span data-stu-id="00a04-109">My.Computer.Mouse</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse)
- [<span data-ttu-id="00a04-110">Behandeln und Auslösen von Ausnahmen in .NET</span><span class="sxs-lookup"><span data-stu-id="00a04-110">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="00a04-111">Try... Catch... Abschließend-Anweisung</span><span class="sxs-lookup"><span data-stu-id="00a04-111">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
