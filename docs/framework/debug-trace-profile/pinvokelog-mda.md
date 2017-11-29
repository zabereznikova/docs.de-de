---
title: pInvokeLog-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9c4842d838fd5b4fee29187f118c784c55e0eb13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="d968b-102">pInvokeLog-MDA</span><span class="sxs-lookup"><span data-stu-id="d968b-102">pInvokeLog MDA</span></span>
<span data-ttu-id="d968b-103">Der `pInvokeLog`-MDA (Assistent für verwaltetes Debuggen) wird für jede eindeutige Plattformaufrufsignatur aktiviert, die während der Ausführung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d968b-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d968b-104">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d968b-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="d968b-105">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="d968b-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d968b-106">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="d968b-106">Output</span></span>  
 <span data-ttu-id="d968b-107">Die Meldung, die die Plattformaufrufsignatur während der Ausführung angibt.</span><span class="sxs-lookup"><span data-stu-id="d968b-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d968b-108">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d968b-108">Configuration</span></span>  
 <span data-ttu-id="d968b-109">Jedes Übereinstimmungselement filtert die DLL-Dateien, für die Plattformaufrufe erfolgen.</span><span class="sxs-lookup"><span data-stu-id="d968b-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d968b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d968b-110">See Also</span></span>  
 [<span data-ttu-id="d968b-111">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="d968b-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="d968b-112">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="d968b-112">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
