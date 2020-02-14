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
ms.openlocfilehash: 12d7f60bcaedc5a97a7718610f40188547f87050
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216134"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="0a532-102">pInvokeLog-MDA</span><span class="sxs-lookup"><span data-stu-id="0a532-102">pInvokeLog MDA</span></span>
<span data-ttu-id="0a532-103">Der `pInvokeLog`-MDA (Assistent für verwaltetes Debuggen) wird für jede eindeutige Plattformaufrufsignatur aktiviert, die während der Ausführung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0a532-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0a532-104">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0a532-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="0a532-105">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="0a532-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0a532-106">Output</span><span class="sxs-lookup"><span data-stu-id="0a532-106">Output</span></span>  
 <span data-ttu-id="0a532-107">Die Meldung, die die Plattformaufrufsignatur während der Ausführung angibt.</span><span class="sxs-lookup"><span data-stu-id="0a532-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0a532-108">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0a532-108">Configuration</span></span>  
 <span data-ttu-id="0a532-109">Jedes Übereinstimmungselement filtert die DLL-Dateien, für die Plattformaufrufe erfolgen.</span><span class="sxs-lookup"><span data-stu-id="0a532-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0a532-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a532-110">See also</span></span>

- [<span data-ttu-id="0a532-111">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="0a532-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="0a532-112">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="0a532-112">Consuming Unmanaged DLL Functions</span></span>](../interop/consuming-unmanaged-dll-functions.md)
