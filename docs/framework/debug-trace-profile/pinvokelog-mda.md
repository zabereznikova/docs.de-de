---
title: pInvokeLog-MDA
description: Verstehen Sie den PInvokeLog Managed Debug Assistant (MDA), der für jede eindeutige Platt Form Aufruf-Signatur aktiviert wird, die während der Ausführung in .NET verwendet wird.
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
ms.openlocfilehash: b8cb4805663a2b28a133f98503730199af695c4f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271459"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="bdd01-103">pInvokeLog-MDA</span><span class="sxs-lookup"><span data-stu-id="bdd01-103">pInvokeLog MDA</span></span>

<span data-ttu-id="bdd01-104">Der `pInvokeLog`-MDA (Assistent für verwaltetes Debuggen) wird für jede eindeutige Plattformaufrufsignatur aktiviert, die während der Ausführung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bdd01-104">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="bdd01-105">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="bdd01-105">Effect on the Runtime</span></span>  

 <span data-ttu-id="bdd01-106">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="bdd01-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="bdd01-107">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="bdd01-107">Output</span></span>  

 <span data-ttu-id="bdd01-108">Die Meldung, die die Plattformaufrufsignatur während der Ausführung angibt.</span><span class="sxs-lookup"><span data-stu-id="bdd01-108">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="bdd01-109">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bdd01-109">Configuration</span></span>  

 <span data-ttu-id="bdd01-110">Jedes Übereinstimmungselement filtert die DLL-Dateien, für die Plattformaufrufe erfolgen.</span><span class="sxs-lookup"><span data-stu-id="bdd01-110">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bdd01-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bdd01-111">See also</span></span>

- [<span data-ttu-id="bdd01-112">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="bdd01-112">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="bdd01-113">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="bdd01-113">Consuming Unmanaged DLL Functions</span></span>](../interop/consuming-unmanaged-dll-functions.md)
