---
title: 'Minderung: EventSource.WriteEvent-Methodenaufrufe'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 327a9fdb-ba8e-40f7-89e5-4c89b46e594f
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 270f89183bced5d07598b1731f18acf90ec9715a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-eventsourcewriteevent-method-calls"></a><span data-ttu-id="409be-102">Minderung: EventSource.WriteEvent-Methodenaufrufe</span><span class="sxs-lookup"><span data-stu-id="409be-102">Mitigation: EventSource.WriteEvent Method Calls</span></span>
<span data-ttu-id="409be-103">[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] setzt einen Vertrag zwischen einer ETW-Ereignismethode in einer Klasse, die von <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> abgeleitet wird, und der <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> -Methode der Basisklasse durch.</span><span class="sxs-lookup"><span data-stu-id="409be-103">The [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] enforces a contract between an ETW event method in a class that is derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> and  the <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> method of its base class.</span></span> <span data-ttu-id="409be-104">Die ETW-Ereignismethode muss der <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> -Methode die Ereignis-ID gefolgt von den gleichen Argumenten übergeben, die an die Ereignismethode übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="409be-104">The ETW event method must pass the <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> method the event ID followed by the same arguments that were passed to the event method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="409be-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="409be-105">Impact</span></span>  
 <span data-ttu-id="409be-106">Eine ETW-Ereignismethode, die folgendermaßen definiert ist, verstößt gegen den Vertrag:</span><span class="sxs-lookup"><span data-stu-id="409be-106">An ETW event method defined in the following way breaks the contract:</span></span>  
  
```  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message, "-");  
}  
```  
  
 <span data-ttu-id="409be-107">Wenn gegen diesen Vertrag verstoßen wird, wird eine <xref:System.IndexOutOfRangeException> -Ausnahme zur Laufzeit ausgelöst, wenn ein <xref:System.Diagnostics.Tracing.EventListener> -Objekt <xref:System.Diagnostics.Tracing.EventSource> -Daten im Prozess liest.</span><span class="sxs-lookup"><span data-stu-id="409be-107">When this contract is violated, an <xref:System.IndexOutOfRangeException> exception is thrown at run time if an <xref:System.Diagnostics.Tracing.EventListener> object reads <xref:System.Diagnostics.Tracing.EventSource> data in process.</span></span>  
  
 <span data-ttu-id="409be-108">Die Definition für diese ETW-Ereignismethode sollte diesem Muster folgen:</span><span class="sxs-lookup"><span data-stu-id="409be-108">The definition for this ETW event method should follow this pattern:</span></span>  
  
```  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message);  
}  
```  
  
## <a name="mitigation"></a><span data-ttu-id="409be-109">Minderung</span><span class="sxs-lookup"><span data-stu-id="409be-109">Mitigation</span></span>  
 <span data-ttu-id="409be-110">Sie müssen vorhandenen Code so ändern, dass dieser dem erforderlichen Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="409be-110">You must modify existing code to conform to the required pattern.</span></span>  
  
 <span data-ttu-id="409be-111">Sie können den Code, den Sie ändern müssen, minimieren, indem Sie wie folgt zwei Methoden zum Aufrufen der <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> -Methode definieren:</span><span class="sxs-lookup"><span data-stu-id="409be-111">You can minimize the amount of code that you have to change by defining two methods for calling the <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> method, as follows:</span></span>  
  
```  
[NonEvent]  
public void Info2(string message)  
{  
   Info2Internal(message, "-");  
}  
  
public void Info2Internal(string message, string prefix)  
{  
   WriteEvent(2, message, prefix);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="409be-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="409be-112">See Also</span></span>  
 [<span data-ttu-id="409be-113">Änderungen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="409be-113">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

