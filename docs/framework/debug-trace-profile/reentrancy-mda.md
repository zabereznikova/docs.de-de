---
title: Reentranz-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged code, debugging
- transitioning threads unmanaged to managed code
- reentrancy MDA
- reentrancy without an orderly transition
- managed debugging assistants (MDAs), reentrancy
- illegal reentrancy
- MDAs (managed debugging assistants), reentrancy
- threading [.NET Framework], managed debugging assistants
- managed code, debugging
- native debugging, MDAs
ms.assetid: 7240c3f3-7df8-4b03-bbf1-17cdce142d45
ms.openlocfilehash: 5cbe8e843ad72785010240f3db30b1d344c80650
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181764"
---
# <a name="reentrancy-mda"></a><span data-ttu-id="e1b5c-102">Reentranz-MDA</span><span class="sxs-lookup"><span data-stu-id="e1b5c-102">reentrancy MDA</span></span>
<span data-ttu-id="e1b5c-103">Der `reentrancy`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn versucht wird, von nativem zu verwaltetem Code überzugehen, und wenn ein vorheriger Wechsel von verwaltetem zu nativem Code nicht über einen ordnungsgemäßen Übergang ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-103">The `reentrancy` managed debugging assistant (MDA) is activated when an attempt is made to transition from native to managed code in cases where a prior switch from managed to native code was not performed through an orderly transition.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="e1b5c-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="e1b5c-104">Symptoms</span></span>  
 <span data-ttu-id="e1b5c-105">Der Objektheap ist beschädigt oder es treten andere schwerwiegende Fehler beim Übergang von nativem zu verwaltetem Code auf.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-105">The object heap is corrupted or other serious errors are occurring when transitioning from native to managed code.</span></span>  
  
 <span data-ttu-id="e1b5c-106">Threads, die zwischen nativem und verwaltetem Code in beide Richtungen wechseln, müssen einen ordnungsgemäßen Übergang durchführen.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-106">Threads that switch between native and managed code in either direction must perform an orderly transition.</span></span> <span data-ttu-id="e1b5c-107">Allerdings erlauben bestimmte Erweiterbarkeitspunkte auf niedriger Ebene, wie beispielsweise Ausnahmehandler von Vektoren, dass Schalter ohne ordnungsgemäßen Übergang aus verwaltetem zu nativem Code wechseln.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-107">However, certain low-level extensibility points in the operating system, such as the vectored exception handler, allow switches from managed to native code without performing an orderly transition.</span></span>  <span data-ttu-id="e1b5c-108">Diese Schalter werden vom Betriebssystem gesteuert und nicht von der Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e1b5c-108">These switches are under operating system control, rather than under common language runtime (CLR) control.</span></span>  <span data-ttu-id="e1b5c-109">Jede native Code, der in diesen Erweiterungspunkten ausgeführt wird, muss Rückrufe in verwaltetem Code vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-109">Any native code that executes inside these extensibility points must avoid calling back into managed code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="e1b5c-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="e1b5c-110">Cause</span></span>  
 <span data-ttu-id="e1b5c-111">Ein Erweiterungspunkt auf niedriger Ebene, wie z.B. der Ausnahmehandler für Vektoren, wurde während der Ausführung von verwaltetem Code aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-111">A low-level operating system extensibility point, such as the vectored exception handler, has activated while executing managed code.</span></span>  <span data-ttu-id="e1b5c-112">Der Anwendungscode, der über diesen Erweiterungspunkt aufgerufen wird, versucht einen Rückruf in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-112">The application code that is invoked through that extensibility point is attempting to call back into managed code.</span></span>  
  
 <span data-ttu-id="e1b5c-113">Dieses Problem wird immer durch den Anwendungscode verursacht.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-113">This problem is always caused by application code.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="e1b5c-114">Lösung</span><span class="sxs-lookup"><span data-stu-id="e1b5c-114">Resolution</span></span>  
 <span data-ttu-id="e1b5c-115">Überprüfen Sie die Stapelüberwachung für den Thread, der diesen MDA aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-115">Examine the stack trace for the thread that has activated this MDA.</span></span>  <span data-ttu-id="e1b5c-116">Der Thread versucht illegal verwalteten Code aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-116">The thread is attempting to illegally call into managed code.</span></span>  <span data-ttu-id="e1b5c-117">Die Stapelüberwachung sollte den Anwendungscode, der diesen Erweiterungspunkt nutzt, den Code des Betriebssystems, der diesen Erweiterungspunkt bereitstellt, und den verwalteten Code, der durch den Erweiterungspunkt unterbrochen wurde, anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-117">The stack trace should reveal the application code using this extensibility point, the operating system code that provides this extensibility point, and the managed code that was interrupted by the extensibility point.</span></span>  
  
 <span data-ttu-id="e1b5c-118">Sie sehen beispielsweise, dass der MDA bei einem Versuch aktiviert wird, bei dem verwalteter Code innerhalb eines Ausnahmehandlers für Vektoren aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-118">For example, you will see the MDA activated in an attempt to call managed code from inside a vectored exception handler.</span></span>  <span data-ttu-id="e1b5c-119">Auf dem Stapel sehen Sie den Code für die Ausnahmebehandlung des Betriebssystems und verwalteten Code wie z.B. <xref:System.DivideByZeroException> oder <xref:System.AccessViolationException>, der eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-119">On the stack you will see the operating system exception handling code and some managed code triggering an exception such as a <xref:System.DivideByZeroException> or an <xref:System.AccessViolationException>.</span></span>  
  
 <span data-ttu-id="e1b5c-120">In diesem Beispiel ist die richtige Lösung die vollständige Implementierung des Ausnahmehandlers für Vektoren in nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-120">In this example, the correct resolution is to implement the vectored exception handler completely in unmanaged code.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e1b5c-121">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="e1b5c-121">Effect on the Runtime</span></span>  
 <span data-ttu-id="e1b5c-122">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-122">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e1b5c-123">Output</span><span class="sxs-lookup"><span data-stu-id="e1b5c-123">Output</span></span>  
 <span data-ttu-id="e1b5c-124">Der MDA meldet, dass ungültiges Wiedereintreten versucht wird.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-124">The MDA reports that illegal reentrancy is being attempted.</span></span>  <span data-ttu-id="e1b5c-125">Überprüfen Sie die Threadstapel, um zu bestimmen, warum dies geschieht und wie Sie das Problem beheben können.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-125">Examine the thread's stack to determine why this is happening and how to correct the problem.</span></span> <span data-ttu-id="e1b5c-126">Nachfolgend ist die Ausgabe des Beispiels aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-126">The following is sample output.</span></span>  
  
```output
Additional Information: Attempting to call into managed code without
transitioning out first.  Do not attempt to run managed code inside
low-level native extensibility points. Managed Debugging Assistant
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## <a name="configuration"></a><span data-ttu-id="e1b5c-127">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e1b5c-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="e1b5c-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1b5c-128">Example</span></span>  
 <span data-ttu-id="e1b5c-129">Im folgenden Codebeispiel wird eine <xref:System.AccessViolationException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-129">The following code example causes an <xref:System.AccessViolationException> to be thrown.</span></span>  <span data-ttu-id="e1b5c-130">Bei Windows-Versionen, die Ausnahmebehandlung für Vektoren unterstützen, wird der verwaltete Ausnahmehandler für Vektoren aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-130">On versions of Windows that support vectored exception handling, this will cause the managed vectored exception handler to be called.</span></span>  <span data-ttu-id="e1b5c-131">Wenn der `reentrancy`-MDA aktiviert ist, wird der MDA beim versuchten Aufruf von `MyHandler` aus dem Unterstützungscode des Ausnahmebehandlers für Vektoren aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e1b5c-131">If the `reentrancy` MDA is enabled, the MDA will activate during the attempted call to `MyHandler` from the operating system's vectored exception handling support code.</span></span>  
  
```csharp
using System;  
public delegate int ExceptionHandler(IntPtr ptrExceptionInfo);  
  
public class Reenter
{  
    public static ExceptionHandler keepAlive;  
  
    [System.Runtime.InteropServices.DllImport("kernel32", ExactSpelling=true,
        CharSet=System.Runtime.InteropServices.CharSet.Auto)]  
    public static extern IntPtr AddVectoredExceptionHandler(int bFirst,
        ExceptionHandler handler);  
  
    static int MyHandler(IntPtr ptrExceptionInfo)
    {  
        // EXCEPTION_CONTINUE_SEARCH  
        return 0;  
    }  
    void Run() {}  
  
    static void Main()
    {  
        keepAlive = new ExceptionHandler(Reenter.MyHandler);  
        IntPtr ret = AddVectoredExceptionHandler(1, keepAlive);  
        try
        {  
            // Dispatch on null should AV.  
            Reenter r = null;
            r.Run();  
        }
        catch { }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1b5c-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1b5c-132">See also</span></span>

- [<span data-ttu-id="e1b5c-133">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="e1b5c-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
