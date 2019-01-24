---
title: pInvokeLog-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe1d783017369a78074e5abf278ac2facf6ee32b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734064"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="b81d4-102">pInvokeLog-MDA</span><span class="sxs-lookup"><span data-stu-id="b81d4-102">pInvokeLog MDA</span></span>
<span data-ttu-id="b81d4-103">Der `pInvokeLog`-MDA (Assistent für verwaltetes Debuggen) wird für jede eindeutige Plattformaufrufsignatur aktiviert, die während der Ausführung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b81d4-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b81d4-104">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b81d4-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="b81d4-105">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="b81d4-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b81d4-106">Output</span><span class="sxs-lookup"><span data-stu-id="b81d4-106">Output</span></span>  
 <span data-ttu-id="b81d4-107">Die Meldung, die die Plattformaufrufsignatur während der Ausführung angibt.</span><span class="sxs-lookup"><span data-stu-id="b81d4-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b81d4-108">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b81d4-108">Configuration</span></span>  
 <span data-ttu-id="b81d4-109">Jedes Übereinstimmungselement filtert die DLL-Dateien, für die Plattformaufrufe erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b81d4-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b81d4-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b81d4-110">See also</span></span>
- [<span data-ttu-id="b81d4-111">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="b81d4-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b81d4-112">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="b81d4-112">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
