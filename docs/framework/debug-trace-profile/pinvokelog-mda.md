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
ms.openlocfilehash: a7fe0b33bbd77143da6d2f4a26b170e4d7afe1fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104467"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="7e701-102">pInvokeLog-MDA</span><span class="sxs-lookup"><span data-stu-id="7e701-102">pInvokeLog MDA</span></span>
<span data-ttu-id="7e701-103">Der `pInvokeLog`-MDA (Assistent für verwaltetes Debuggen) wird für jede eindeutige Plattformaufrufsignatur aktiviert, die während der Ausführung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7e701-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="7e701-104">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7e701-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="7e701-105">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="7e701-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="7e701-106">Output</span><span class="sxs-lookup"><span data-stu-id="7e701-106">Output</span></span>  
 <span data-ttu-id="7e701-107">Die Meldung, die die Plattformaufrufsignatur während der Ausführung angibt.</span><span class="sxs-lookup"><span data-stu-id="7e701-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="7e701-108">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7e701-108">Configuration</span></span>  
 <span data-ttu-id="7e701-109">Jedes Übereinstimmungselement filtert die DLL-Dateien, für die Plattformaufrufe erfolgen.</span><span class="sxs-lookup"><span data-stu-id="7e701-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7e701-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e701-110">See also</span></span>

- [<span data-ttu-id="7e701-111">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="7e701-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="7e701-112">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="7e701-112">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
