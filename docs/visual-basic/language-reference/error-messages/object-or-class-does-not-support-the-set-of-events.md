---
title: Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: bc75e031c2d05bea3aa64774a9d3817756e51e8b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409360"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="56553-102">Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.</span><span class="sxs-lookup"><span data-stu-id="56553-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="56553-103">Sie haben versucht, eine `WithEvents` Variable mit einer Komponente zu verwenden, die nicht als Ereignis Quelle für den angegebenen Satz von Ereignissen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="56553-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="56553-104">Sie möchten z. b. die Ereignisse eines Objekts senken und dann ein weiteres Objekt erstellen, das `Implements` das erste Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="56553-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="56553-105">Obwohl Sie vielleicht denken, dass Sie die Ereignisse aus dem implementierten Objekt absenken könnten, ist dies nicht immer der Fall.</span><span class="sxs-lookup"><span data-stu-id="56553-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="56553-106">`Implements`implementiert nur eine Schnittstelle für Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="56553-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="56553-107">`WithEvents`wird für private nicht unterstützt `UserControls` , da die Typinformationen, die erforderlich sind, um den zu erhöhen, zur `ObjectEvent` Laufzeit nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="56553-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="56553-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="56553-108">To correct this error</span></span>  
  
1. <span data-ttu-id="56553-109">Ereignisse für eine Komponente, die keine Ereignisse enthält, können nicht als Senke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="56553-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56553-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56553-110">See also</span></span>

- [<span data-ttu-id="56553-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="56553-111">WithEvents</span></span>](../modifiers/withevents.md)
- [<span data-ttu-id="56553-112">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56553-112">Implements Statement</span></span>](../statements/implements-statement.md)
