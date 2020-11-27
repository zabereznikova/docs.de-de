---
title: invalidGCHandleCookie-MDA
description: Überprüfen Sie den invalidGCHandleCookie-MDA (Managed Debugging Assistant), der aktiviert wird, wenn eine Konvertierung von einem ungültigen IntPtr-Cookie in ein GCHandle versucht wird.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
ms.openlocfilehash: 36806498445da78c8d9dd5c51c1903b253a39da0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272604"
---
# <a name="invalidgchandlecookie-mda"></a><span data-ttu-id="a355b-103">invalidGCHandleCookie-MDA</span><span class="sxs-lookup"><span data-stu-id="a355b-103">invalidGCHandleCookie MDA</span></span>

<span data-ttu-id="a355b-104">Der `invalidGCHandleCookie`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine Konvertierung von einem ungültigen <xref:System.IntPtr>-Cookie in ein <xref:System.Runtime.InteropServices.GCHandle> versucht wird.</span><span class="sxs-lookup"><span data-stu-id="a355b-104">The `invalidGCHandleCookie` managed debugging assistant (MDA) is activated when a conversion from an invalid <xref:System.IntPtr> cookie to a <xref:System.Runtime.InteropServices.GCHandle> is attempted.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a355b-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="a355b-105">Symptoms</span></span>  

 <span data-ttu-id="a355b-106">Ein nicht definiertes Verhalten, z.B. Zugriffsverletzungen und Speicherschäden, beim Versuch <xref:System.Runtime.InteropServices.GCHandle> aus <xref:System.IntPtr> abzurufen oder zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a355b-106">Undefined behavior such as access violations and memory corruption while attempting to use or retrieve a <xref:System.Runtime.InteropServices.GCHandle> from an <xref:System.IntPtr>.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a355b-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="a355b-107">Cause</span></span>  

 <span data-ttu-id="a355b-108">Das Cookie ist wahrscheinlich ungültig, da es entweder nicht ursprünglich von <xref:System.Runtime.InteropServices.GCHandle> erstellt wurde, <xref:System.Runtime.InteropServices.GCHandle> darstellt, das bereits freigegeben wurde oder ein Cookie für <xref:System.Runtime.InteropServices.GCHandle> in einer anderen Anwendungsdomäne ist. Außerdem könnte es als <xref:System.Runtime.InteropServices.GCHandle> in nativen Code gemarshallt und als <xref:System.IntPtr> in die CLR zurückgegeben worden sein, in der eine Umwandlung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="a355b-108">The cookie is probably invalid because it was not originally created from a <xref:System.Runtime.InteropServices.GCHandle>, represents a <xref:System.Runtime.InteropServices.GCHandle> that has already been freed, is a cookie to a <xref:System.Runtime.InteropServices.GCHandle> in a different application domain, or was marshaled to native code as a <xref:System.Runtime.InteropServices.GCHandle> but passed back into the CLR as an <xref:System.IntPtr>, where a cast was attempted.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a355b-109">Lösung</span><span class="sxs-lookup"><span data-stu-id="a355b-109">Resolution</span></span>  

 <span data-ttu-id="a355b-110">Geben Sie ein gültiges <xref:System.IntPtr>-Cookie für <xref:System.Runtime.InteropServices.GCHandle> an.</span><span class="sxs-lookup"><span data-stu-id="a355b-110">Specify a valid <xref:System.IntPtr> cookie for the <xref:System.Runtime.InteropServices.GCHandle>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a355b-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a355b-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="a355b-112">Wenn dieser MDA aktiviert ist, kann der Debugger die Stämme nicht länger zu ihren Objekten zurückverfolgen, da die zurückgegebenen Cookiewerte sich von denjenigen unterscheiden, die zurückgegeben werden, wenn der MDA nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a355b-112">When this MDA is enabled, the debugger is no longer able to trace the roots back to their objects because the cookie values passed back are different from the ones returned when the MDA is not enabled.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a355b-113">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="a355b-113">Output</span></span>  

 <span data-ttu-id="a355b-114">Der ungültige <xref:System.IntPtr>-Cookiewert wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="a355b-114">The invalid <xref:System.IntPtr> cookie value is reported.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a355b-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a355b-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a355b-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a355b-116">See also</span></span>

- <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>
- <xref:System.Runtime.InteropServices.GCHandle>
- [<span data-ttu-id="a355b-117">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="a355b-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
