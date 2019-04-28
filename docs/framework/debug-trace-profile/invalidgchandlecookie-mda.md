---
title: invalidGCHandleCookie-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 876f0fe3c40cb6754b4ba714833dd160dc4de3a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754400"
---
# <a name="invalidgchandlecookie-mda"></a><span data-ttu-id="d9258-102">invalidGCHandleCookie-MDA</span><span class="sxs-lookup"><span data-stu-id="d9258-102">invalidGCHandleCookie MDA</span></span>
<span data-ttu-id="d9258-103">Der `invalidGCHandleCookie`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine Konvertierung von einem ungültigen <xref:System.IntPtr>-Cookie in ein <xref:System.Runtime.InteropServices.GCHandle> versucht wird.</span><span class="sxs-lookup"><span data-stu-id="d9258-103">The `invalidGCHandleCookie` managed debugging assistant (MDA) is activated when a conversion from an invalid <xref:System.IntPtr> cookie to a <xref:System.Runtime.InteropServices.GCHandle> is attempted.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d9258-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="d9258-104">Symptoms</span></span>  
 <span data-ttu-id="d9258-105">Ein nicht definiertes Verhalten, z.B. Zugriffsverletzungen und Speicherschäden, beim Versuch <xref:System.Runtime.InteropServices.GCHandle> aus <xref:System.IntPtr> abzurufen oder zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9258-105">Undefined behavior such as access violations and memory corruption while attempting to use or retrieve a <xref:System.Runtime.InteropServices.GCHandle> from an <xref:System.IntPtr>.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d9258-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="d9258-106">Cause</span></span>  
 <span data-ttu-id="d9258-107">Das Cookie ist wahrscheinlich ungültig, da es entweder nicht ursprünglich von <xref:System.Runtime.InteropServices.GCHandle> erstellt wurde, <xref:System.Runtime.InteropServices.GCHandle> darstellt, das bereits freigegeben wurde oder ein Cookie für <xref:System.Runtime.InteropServices.GCHandle> in einer anderen Anwendungsdomäne ist. Außerdem könnte es als <xref:System.Runtime.InteropServices.GCHandle> in nativen Code gemarshallt und als <xref:System.IntPtr> in die CLR zurückgegeben worden sein, in der eine Umwandlung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="d9258-107">The cookie is probably invalid because it was not originally created from a <xref:System.Runtime.InteropServices.GCHandle>, represents a <xref:System.Runtime.InteropServices.GCHandle> that has already been freed, is a cookie to a <xref:System.Runtime.InteropServices.GCHandle> in a different application domain, or was marshaled to native code as a <xref:System.Runtime.InteropServices.GCHandle> but passed back into the CLR as an <xref:System.IntPtr>, where a cast was attempted.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d9258-108">Auflösung</span><span class="sxs-lookup"><span data-stu-id="d9258-108">Resolution</span></span>  
 <span data-ttu-id="d9258-109">Geben Sie ein gültiges <xref:System.IntPtr>-Cookie für <xref:System.Runtime.InteropServices.GCHandle> an.</span><span class="sxs-lookup"><span data-stu-id="d9258-109">Specify a valid <xref:System.IntPtr> cookie for the <xref:System.Runtime.InteropServices.GCHandle>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d9258-110">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d9258-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="d9258-111">Wenn dieser MDA aktiviert ist, kann der Debugger die Stämme nicht länger zu ihren Objekten zurückverfolgen, da die zurückgegebenen Cookiewerte sich von denjenigen unterscheiden, die zurückgegeben werden, wenn der MDA nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d9258-111">When this MDA is enabled, the debugger is no longer able to trace the roots back to their objects because the cookie values passed back are different from the ones returned when the MDA is not enabled.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d9258-112">Output</span><span class="sxs-lookup"><span data-stu-id="d9258-112">Output</span></span>  
 <span data-ttu-id="d9258-113">Der ungültige <xref:System.IntPtr>-Cookiewert wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="d9258-113">The invalid <xref:System.IntPtr> cookie value is reported.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d9258-114">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d9258-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9258-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9258-115">See also</span></span>

- <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>
- <xref:System.Runtime.InteropServices.GCHandle>
- [<span data-ttu-id="d9258-116">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="d9258-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
