---
title: Ereignisse freigegebener WithEvents-Variablen können nicht von freigegebenen Methoden behandelt werden.
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 02039b81251e59a951a0fe37ec2c9534b458b6a5
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161919"
---
# <a name="bc30594-events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="1eabe-102">BC30594: Ereignisse von freigegebenen widervents-Variablen können nicht von nicht freigegebenen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="1eabe-102">BC30594: Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>

<span data-ttu-id="1eabe-103">Eine mit dem- `Shared` Modifizierer deklarierte Variable ist eine freigegebene Variable.</span><span class="sxs-lookup"><span data-stu-id="1eabe-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="1eabe-104">Eine freigegebene Variable identifiziert genau einen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="1eabe-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="1eabe-105">Eine mit dem-Modifizierer deklarierte Variable bestätigt `WithEvents` , dass der Typ, zu dem die Variable gehört, den Satz von Ereignissen behandelt, den die Variable auslöst.</span><span class="sxs-lookup"><span data-stu-id="1eabe-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="1eabe-106">Wenn der Variablen ein Wert zugewiesen wird, entbindet die von der `WithEvents` Deklaration erstellte Eigenschaft jeden vorhandenen Ereignishandler und verknüpft den neuen Ereignishandler über die- `Add` Methode.</span><span class="sxs-lookup"><span data-stu-id="1eabe-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>

 <span data-ttu-id="1eabe-107">**Fehler-ID:** BC30594</span><span class="sxs-lookup"><span data-stu-id="1eabe-107">**Error ID:** BC30594</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1eabe-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="1eabe-108">To correct this error</span></span>

- <span data-ttu-id="1eabe-109">Deklarieren Sie den Ereignishandler `Shared` .</span><span class="sxs-lookup"><span data-stu-id="1eabe-109">Declare your event handler `Shared`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1eabe-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eabe-110">See also</span></span>

- [<span data-ttu-id="1eabe-111">Freigegeben</span><span class="sxs-lookup"><span data-stu-id="1eabe-111">Shared</span></span>](../modifiers/shared.md)
- [<span data-ttu-id="1eabe-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="1eabe-112">WithEvents</span></span>](../modifiers/withevents.md)
