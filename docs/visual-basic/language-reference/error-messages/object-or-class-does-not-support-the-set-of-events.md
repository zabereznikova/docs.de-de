---
title: Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: e55a5515d88bd2782e31fdea7c07e16c595d43b5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873654"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="cf147-102">Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.</span><span class="sxs-lookup"><span data-stu-id="cf147-102">Object or class does not support the set of events</span></span>

<span data-ttu-id="cf147-103">Sie haben versucht, eine `WithEvents` Variable mit einer Komponente zu verwenden, die nicht als Ereignis Quelle für den angegebenen Satz von Ereignissen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cf147-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="cf147-104">Sie möchten z. b. die Ereignisse eines Objekts senken und dann ein weiteres Objekt erstellen, das `Implements` das erste Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="cf147-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="cf147-105">Obwohl Sie vielleicht denken, dass Sie die Ereignisse aus dem implementierten Objekt absenken könnten, ist dies nicht immer der Fall.</span><span class="sxs-lookup"><span data-stu-id="cf147-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="cf147-106">`Implements` implementiert nur eine Schnittstelle für Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="cf147-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="cf147-107">`WithEvents` wird für private nicht unterstützt `UserControls` , da die Typinformationen, die erforderlich sind, um den zu erhöhen, zur `ObjectEvent` Laufzeit nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cf147-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cf147-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="cf147-108">To correct this error</span></span>  
  
1. <span data-ttu-id="cf147-109">Ereignisse für eine Komponente, die keine Ereignisse enthält, können nicht als Senke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf147-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf147-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf147-110">See also</span></span>

- [<span data-ttu-id="cf147-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="cf147-111">WithEvents</span></span>](../modifiers/withevents.md)
- [<span data-ttu-id="cf147-112">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cf147-112">Implements Statement</span></span>](../statements/implements-statement.md)
