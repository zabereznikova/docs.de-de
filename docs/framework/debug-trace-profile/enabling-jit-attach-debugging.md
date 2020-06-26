---
title: Aktivieren von JIT-attach Debugging
description: Aktivieren Sie das Just-in-time (JIT)-Debuggen, um beim Auftreten von Fehlern einen Debugger an einen Prozess anzufügen. Sie kann durch bestimmte Methoden oder Funktionen ausgelöst werden.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
ms.openlocfilehash: d1190c51a9cc6b5322ec832e0d35bc01dc855b12
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416043"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="e526a-104">Aktivieren von JIT-attach Debugging</span><span class="sxs-lookup"><span data-stu-id="e526a-104">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="e526a-105">Mit „JIT-attach Debugging“ wird das Anfügen eines Debuggers an einen Prozess beim Auftreten von Fehlern beschrieben. Es kann auch von bestimmten Methoden oder Funktionen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e526a-105">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="e526a-106">JIT-attach Debugging wird bei den folgenden Fehlerzuständen verwendet:</span><span class="sxs-lookup"><span data-stu-id="e526a-106">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
- <span data-ttu-id="e526a-107">bei Ausnahmefehlern (im nativen und im verwalteten Code)</span><span class="sxs-lookup"><span data-stu-id="e526a-107">Unhandled exceptions (in both native and managed code).</span></span>  
  
- <span data-ttu-id="e526a-108">bei der <xref:System.Environment.FailFast%2A?displayProperty=nameWithType>-Methode oder [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception)-Funktion (Windows 7-Produktfamilie)</span><span class="sxs-lookup"><span data-stu-id="e526a-108"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) function (Windows 7 family).</span></span>  
  
- <span data-ttu-id="e526a-109">bei schwerwiegenden Laufzeitfehlern</span><span class="sxs-lookup"><span data-stu-id="e526a-109">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="e526a-110">JIT-attach Debugging wird auch durch Aufrufen der folgenden Methoden und Funktionen ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="e526a-110">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
- <span data-ttu-id="e526a-111"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="e526a-111"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="e526a-112"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="e526a-112"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="e526a-113">[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak)-Funktion (Win32)</span><span class="sxs-lookup"><span data-stu-id="e526a-113">[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) function (Win32).</span></span>  
  
 <span data-ttu-id="e526a-114">Vor der .NET Framework 4 haben die .NET Framework separate Registrierungsschlüssel bereitgestellt, um das Verhalten von nativen und verwalteten Debuggern zu steuern.</span><span class="sxs-lookup"><span data-stu-id="e526a-114">Before the .NET Framework 4, the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="e526a-115">Ab .NET Framework 4 wird die Steuerung unter einem einzelnen Registrierungsschlüssel konsolidiert: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span><span class="sxs-lookup"><span data-stu-id="e526a-115">Starting with the .NET Framework 4, control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="e526a-116">Mit den Werten, die Sie für diesen Schlüssel festlegen können, bestimmen Sie, ob ein Debugger aufgerufen wird. Außerdem können Sie festlegen, ob in diesem Fall ein Dialogfeld angezeigt werden soll, das eine Benutzereingabe erfordert.</span><span class="sxs-lookup"><span data-stu-id="e526a-116">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="e526a-117">Weitere Informationen zum Festlegen dieses Registrierungsschlüssels finden Sie unter [Konfigurieren des automatischen Debuggens](/windows/win32/debug/configuring-automatic-debugging).</span><span class="sxs-lookup"><span data-stu-id="e526a-117">For information about setting this registry key, see [Configuring Automatic Debugging](/windows/win32/debug/configuring-automatic-debugging).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e526a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e526a-118">See also</span></span>

- [<span data-ttu-id="e526a-119">Debuggen, Ablaufverfolgung und Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="e526a-119">Debugging, Tracing, and Profiling</span></span>](index.md)
- [<span data-ttu-id="e526a-120">Erleichtern des Debuggens für ein Abbild</span><span class="sxs-lookup"><span data-stu-id="e526a-120">Making an Image Easier to Debug</span></span>](making-an-image-easier-to-debug.md)
