---
title: Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: 4a6f1f59f43cdb351d49fbcbfd18362db888586e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593203"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="efc12-102">Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.</span><span class="sxs-lookup"><span data-stu-id="efc12-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="efc12-103">Sie haben versucht, mit einem `WithEvents` Variable mit einer Komponente, die als Ereignisquelle für den angegebenen Satz von Ereignissen nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="efc12-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="efc12-104">Sie möchten z. B. die Ereignisse eines Objekts aufzufangen und anschließend ein anderes Objekt zu erstellen, die `Implements` das erste Objekt.</span><span class="sxs-lookup"><span data-stu-id="efc12-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="efc12-105">Obwohl Sie denken, dass Sie die Ereignisse aus dem Objekt implementiert sink konnte vielleicht, ist dies nicht immer der Fall.</span><span class="sxs-lookup"><span data-stu-id="efc12-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="efc12-106">`Implements` nur eine Schnittstelle für Methoden und Eigenschaften implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="efc12-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="efc12-107">`WithEvents` wird nicht unterstützt für Private `UserControls`, da die Typinformationen zum Auslösen der `ObjectEvent` zur Laufzeit nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="efc12-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="efc12-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="efc12-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="efc12-109">Sie können nicht für eine Komponente Auffangen von Ereignissen, die nicht im Quellmodell Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="efc12-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc12-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efc12-110">See Also</span></span>  
 [<span data-ttu-id="efc12-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="efc12-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [<span data-ttu-id="efc12-112">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="efc12-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
