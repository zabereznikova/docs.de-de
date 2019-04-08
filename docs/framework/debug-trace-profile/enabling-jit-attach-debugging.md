---
title: Aktivieren von JIT-attach Debugging
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f1696f9054d44a5f80a1f67cc38e315a8627d295
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078783"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="c21a4-102">Aktivieren von JIT-attach Debugging</span><span class="sxs-lookup"><span data-stu-id="c21a4-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="c21a4-103">Mit „JIT-attach Debugging“ wird das Anfügen eines Debuggers an einen Prozess beim Auftreten von Fehlern beschrieben. Es kann auch von bestimmten Methoden oder Funktionen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="c21a4-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="c21a4-104">JIT-attach Debugging wird bei den folgenden Fehlerzuständen verwendet:</span><span class="sxs-lookup"><span data-stu-id="c21a4-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
-   <span data-ttu-id="c21a4-105">bei Ausnahmefehlern (im nativen und im verwalteten Code)</span><span class="sxs-lookup"><span data-stu-id="c21a4-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
-   <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> <span data-ttu-id="c21a4-106">Methode oder [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) Funktion (Windows 7-Produktfamilie).</span><span class="sxs-lookup"><span data-stu-id="c21a4-106">method or [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) function (Windows 7 family).</span></span>  
  
-   <span data-ttu-id="c21a4-107">bei schwerwiegenden Laufzeitfehlern</span><span class="sxs-lookup"><span data-stu-id="c21a4-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="c21a4-108">JIT-attach Debugging wird auch durch Aufrufen der folgenden Methoden und Funktionen ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="c21a4-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
-   <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> <span data-ttu-id="c21a4-109">-Methode.</span><span class="sxs-lookup"><span data-stu-id="c21a4-109">method.</span></span>  
  
-   <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> <span data-ttu-id="c21a4-110">-Methode.</span><span class="sxs-lookup"><span data-stu-id="c21a4-110">method.</span></span>  
  
-   <span data-ttu-id="c21a4-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106)-Funktion (Win32)</span><span class="sxs-lookup"><span data-stu-id="c21a4-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) function (Win32).</span></span>  
  
 <span data-ttu-id="c21a4-112">Vor [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] stellte .NET Framework separate Registrierungsschlüssel zur Verhaltenssteuerung von nativen und verwalteten Debuggern bereit.</span><span class="sxs-lookup"><span data-stu-id="c21a4-112">Before the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="c21a4-113">Beginnend mit der [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], ist die Steuerung unter einem einzelnen Registrierungsschlüssel konsolidiert: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span><span class="sxs-lookup"><span data-stu-id="c21a4-113">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="c21a4-114">Mit den Werten, die Sie für diesen Schlüssel festlegen können, bestimmen Sie, ob ein Debugger aufgerufen wird. Außerdem können Sie festlegen, ob in diesem Fall ein Dialogfeld angezeigt werden soll, das eine Benutzereingabe erfordert.</span><span class="sxs-lookup"><span data-stu-id="c21a4-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="c21a4-115">Informationen zum Festlegen dieses Registrierungsschlüssels finden Sie unter [Konfigurieren des automatischen Debuggens](https://go.microsoft.com/fwlink/?LinkId=181767).</span><span class="sxs-lookup"><span data-stu-id="c21a4-115">For information about setting this registry key, see [Configuring Automatic Debugging](https://go.microsoft.com/fwlink/?LinkId=181767).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c21a4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c21a4-116">See also</span></span>

- [<span data-ttu-id="c21a4-117">Debuggen, Ablaufverfolgung und Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="c21a4-117">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)
- [<span data-ttu-id="c21a4-118">Erleichtern des Debuggens für ein Abbild</span><span class="sxs-lookup"><span data-stu-id="c21a4-118">Making an Image Easier to Debug</span></span>](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)
