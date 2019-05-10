---
title: Ereignisse freigegebener WithEvents-Variablen können nicht von freigegebenen Methoden behandelt werden.
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: d6067c75835ecd14f1dd796c20ae3f29f456e541
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642929"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="65cb2-102">Ereignisse freigegebener WithEvents-Variablen können nicht von freigegebenen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="65cb2-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="65cb2-103">Eine Variable mit dem `Shared` Modifizierer ist eine freigegebene Variable.</span><span class="sxs-lookup"><span data-stu-id="65cb2-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="65cb2-104">Eine freigegebene Variable gibt genau einen Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="65cb2-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="65cb2-105">Eine Variable mit dem `WithEvents` Modifizierer bestätigt, dass der Typ, der die Variable angehört, den Satz von Ereignissen verarbeitet der Variablen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="65cb2-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="65cb2-106">Ein Wert der Variablen zugewiesen ist, die Eigenschaft erstellt, wenn die `WithEvents` Deklaration hebt alle vorhandenen Ereignishandler und verknüpft den neuen Ereignishandler über die `Add` Methode.</span><span class="sxs-lookup"><span data-stu-id="65cb2-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="65cb2-107">**Fehler-ID:** BC30594</span><span class="sxs-lookup"><span data-stu-id="65cb2-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="65cb2-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="65cb2-108">To correct this error</span></span>  
  
- <span data-ttu-id="65cb2-109">Deklarieren Sie Ihre Ereignishandler `Shared`.</span><span class="sxs-lookup"><span data-stu-id="65cb2-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65cb2-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65cb2-110">See also</span></span>

- [<span data-ttu-id="65cb2-111">Shared</span><span class="sxs-lookup"><span data-stu-id="65cb2-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="65cb2-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="65cb2-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
