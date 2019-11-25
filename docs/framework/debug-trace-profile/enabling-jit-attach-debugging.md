---
title: Aktivieren von JIT-attach Debugging
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be619f8e84b176872361fdd43faa9c704832c8e0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975591"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="b664a-102">Aktivieren von JIT-attach Debugging</span><span class="sxs-lookup"><span data-stu-id="b664a-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="b664a-103">Mit „JIT-attach Debugging“ wird das Anfügen eines Debuggers an einen Prozess beim Auftreten von Fehlern beschrieben. Es kann auch von bestimmten Methoden oder Funktionen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="b664a-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="b664a-104">JIT-attach Debugging wird bei den folgenden Fehlerzuständen verwendet:</span><span class="sxs-lookup"><span data-stu-id="b664a-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
- <span data-ttu-id="b664a-105">bei Ausnahmefehlern (im nativen und im verwalteten Code)</span><span class="sxs-lookup"><span data-stu-id="b664a-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
- <span data-ttu-id="b664a-106">bei der <xref:System.Environment.FailFast%2A?displayProperty=nameWithType>-Methode oder [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception)-Funktion (Windows 7-Produktfamilie)</span><span class="sxs-lookup"><span data-stu-id="b664a-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) function (Windows 7 family).</span></span>  
  
- <span data-ttu-id="b664a-107">bei schwerwiegenden Laufzeitfehlern</span><span class="sxs-lookup"><span data-stu-id="b664a-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="b664a-108">JIT-attach Debugging wird auch durch Aufrufen der folgenden Methoden und Funktionen ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="b664a-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
- <span data-ttu-id="b664a-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="b664a-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="b664a-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="b664a-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="b664a-111">[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak)-Funktion (Win32)</span><span class="sxs-lookup"><span data-stu-id="b664a-111">[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) function (Win32).</span></span>  
  
 <span data-ttu-id="b664a-112">Vor der .NET Framework 4 haben die .NET Framework separate Registrierungsschlüssel bereitgestellt, um das Verhalten von nativen und verwalteten Debuggern zu steuern.</span><span class="sxs-lookup"><span data-stu-id="b664a-112">Before the .NET Framework 4, the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="b664a-113">Ab .NET Framework 4 wird die Steuerung unter einem einzelnen Registrierungsschlüssel konsolidiert: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span><span class="sxs-lookup"><span data-stu-id="b664a-113">Starting with the .NET Framework 4, control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="b664a-114">Mit den Werten, die Sie für diesen Schlüssel festlegen können, bestimmen Sie, ob ein Debugger aufgerufen wird. Außerdem können Sie festlegen, ob in diesem Fall ein Dialogfeld angezeigt werden soll, das eine Benutzereingabe erfordert.</span><span class="sxs-lookup"><span data-stu-id="b664a-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="b664a-115">Weitere Informationen zum Festlegen dieses Registrierungsschlüssels finden Sie unter [Konfigurieren des automatischen Debuggens](/windows/win32/debug/configuring-automatic-debugging).</span><span class="sxs-lookup"><span data-stu-id="b664a-115">For information about setting this registry key, see [Configuring Automatic Debugging](/windows/win32/debug/configuring-automatic-debugging).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b664a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b664a-116">See also</span></span>

- [<span data-ttu-id="b664a-117">Debuggen, Ablaufverfolgung und Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="b664a-117">Debugging, Tracing, and Profiling</span></span>](index.md)
- [<span data-ttu-id="b664a-118">Erleichtern des Debuggens für ein Abbild</span><span class="sxs-lookup"><span data-stu-id="b664a-118">Making an Image Easier to Debug</span></span>](making-an-image-easier-to-debug.md)
