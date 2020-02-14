---
title: invalidApartmentStateChange-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid apartment state
- managed debugging assistants (MDAs), invalid apartment state
- InvalidApartmentStateChange MDA
- invalid apartment state changes
- threading [.NET Framework], apartment states
- apartment states
- threading [.NET Framework], managed debugging assistants
- COM apartment states
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
ms.openlocfilehash: 8acafcc2fba9a7d30cc77f25f06adaca7c79db32
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217415"
---
# <a name="invalidapartmentstatechange-mda"></a><span data-ttu-id="44776-102">invalidApartmentStateChange-MDA</span><span class="sxs-lookup"><span data-stu-id="44776-102">invalidApartmentStateChange MDA</span></span>
<span data-ttu-id="44776-103">Der `invalidApartmentStateChange`-MDA (Assistent für verwaltetes Debuggen) wird durch eines der folgenden zwei Probleme aktiviert:</span><span class="sxs-lookup"><span data-stu-id="44776-103">The `invalidApartmentStateChange` managed debugging assistant (MDS) is activated by either of two problems:</span></span>  
  
- <span data-ttu-id="44776-104">Es wird versucht, den COM-Apartmentzustand eines Threads zu ändern, der bereits von COM an einen anderen Apartmentzustand initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="44776-104">An attempt is made to change the COM apartment state of a thread that has already been initialized by COM to a different apartment state.</span></span>  
  
- <span data-ttu-id="44776-105">Der COM-Apartmentzustand eines Threads verändert sich unerwartet.</span><span class="sxs-lookup"><span data-stu-id="44776-105">The COM apartment state of a thread changes unexpectedly.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="44776-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="44776-106">Symptoms</span></span>  
  
- <span data-ttu-id="44776-107">Der COM-Apartmentzustand eines Threads ist nicht das, was angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="44776-107">A thread's COM apartment state is not what was requested.</span></span> <span data-ttu-id="44776-108">Dies kann möglicherweise dazu führen, dass Proxys für COM-Komponenten verwendet werden, die ein anderes Threadmodell als das aktuelle aufweisen.</span><span class="sxs-lookup"><span data-stu-id="44776-108">This may cause proxies to be used for COM components that have a threading model different from the current one.</span></span> <span data-ttu-id="44776-109">Dies wiederum kann dazu führen, dass ein <xref:System.InvalidCastException> ausgelöst wird, wenn das COM-Objekt über Schnittstellen aufgerufen wird, die nicht für das apartmentübergreifende Marshalling eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="44776-109">This in turn may cause an <xref:System.InvalidCastException> to be thrown when calling the COM object through interfaces that are not set up for cross-apartment marshaling.</span></span>  
  
- <span data-ttu-id="44776-110">Der COM-Apartmentzustand des Threads ist anders als erwartet.</span><span class="sxs-lookup"><span data-stu-id="44776-110">The COM apartment state of the thread is different than expected.</span></span> <span data-ttu-id="44776-111">Dies kann dazu führen, dass eine <xref:System.Runtime.InteropServices.COMException> mit einem HRESULT von RPC_E_WRONG_THREAD sowie ein <xref:System.InvalidCastException> ausgelöst wird, wenn ein [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="44776-111">This can cause a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD as well as a <xref:System.InvalidCastException> when making calls on a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="44776-112">Dies kann auch dazu führen, dass mehrere Threads gleichzeitig auf einige Singlethread-COM-Komponenten zugreifen können, was zu einer Beschädigung oder einem Verlust von Daten führen kann.</span><span class="sxs-lookup"><span data-stu-id="44776-112">This can also cause some single-threaded COM components to be accessed by multiple threads at the same time, which can lead to corruption or data loss.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="44776-113">Ursache</span><span class="sxs-lookup"><span data-stu-id="44776-113">Cause</span></span>  
  
- <span data-ttu-id="44776-114">Der Thread wurde zuvor in einen anderen COM-Apartmentzustand initialisiert.</span><span class="sxs-lookup"><span data-stu-id="44776-114">The thread was previously initialized to a different COM apartment state.</span></span> <span data-ttu-id="44776-115">Beachten Sie, dass ein Apartmentzustand eines Threads explizit oder implizit festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="44776-115">Note that the apartment state of a thread can be set either explicitly or implicitly.</span></span> <span data-ttu-id="44776-116">Zu den expliziten Vorgängen zählen die <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType>-Eigenschaft und die <xref:System.Threading.Thread.SetApartmentState%2A>- und <xref:System.Threading.Thread.TrySetApartmentState%2A>-Methoden.</span><span class="sxs-lookup"><span data-stu-id="44776-116">The explicit operations include the <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> property and the <xref:System.Threading.Thread.SetApartmentState%2A> and <xref:System.Threading.Thread.TrySetApartmentState%2A> methods.</span></span> <span data-ttu-id="44776-117">Ein Thread, der mit der <xref:System.Threading.Thread.Start%2A>-Methode erstellt wurde, wird implizit auf <xref:System.Threading.ApartmentState.MTA> festgelegt, wenn <xref:System.Threading.Thread.SetApartmentState%2A> vor dem Start des Threads aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="44776-117">A thread created using the <xref:System.Threading.Thread.Start%2A> method is implicitly set to <xref:System.Threading.ApartmentState.MTA> unless <xref:System.Threading.Thread.SetApartmentState%2A> is called before the thread is started.</span></span> <span data-ttu-id="44776-118">Der Hauptthread der Anwendung wird ebenfalls implizit auf <xref:System.Threading.ApartmentState.MTA> initialisiert, sofern das <xref:System.STAThreadAttribute>-Attribut für die Hauptmethode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="44776-118">The main thread of the application is also implicitly initialized to <xref:System.Threading.ApartmentState.MTA> unless the <xref:System.STAThreadAttribute> attribute is specified on the main method.</span></span>  
  
- <span data-ttu-id="44776-119">Die `CoUninitialize`-Methode (oder die `CoInitializeEx`-Methode) wird mit einem anderen Parallelitätsmodell für den Thread aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="44776-119">The `CoUninitialize` method (or the `CoInitializeEx` method) with a different concurrency model is called on the thread.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="44776-120">Lösung</span><span class="sxs-lookup"><span data-stu-id="44776-120">Resolution</span></span>  
 <span data-ttu-id="44776-121">Legen Sie den Apartmentzustand des Threads fest, bevor die Ausführung beginnt, oder wenden Sie entweder das <xref:System.STAThreadAttribute>- oder das <xref:System.MTAThreadAttribute>-Attribut auf die Hauptmethode der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="44776-121">Set the apartment state of the thread before it begins executing, or apply either the <xref:System.STAThreadAttribute> attribute or the <xref:System.MTAThreadAttribute> attribute to the main method of the application.</span></span>  
  
 <span data-ttu-id="44776-122">Hinsichtlich der zweiten Ursache sollte der Code, der die `CoUninitialize`-Methode aufruft, idealerweise geändert werden, um den Aufruf zu verzögern, bis der Thread beendet wird und keine RCWs und ihre zugrunde liegenden COM-Komponenten noch vom Thread verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44776-122">For the second cause, ideally, the code that calls the `CoUninitialize` method should be modified to delay the call until the thread is about to terminate and there are no RCWs and their underlying COM components still in use by the thread.</span></span> <span data-ttu-id="44776-123">Sollte es jedoch nicht möglich sein, den Code zu ändern, der die `CoUninitialize`-Methode aufruft, dann sollten keine RCWs aus Threads verwendet werden, die auf diese Weise nicht initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="44776-123">However, if it is not possible to modify the code that calls the `CoUninitialize` method, then no RCWs should be used from threads that are uninitialized in this way.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="44776-124">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="44776-124">Effect on the Runtime</span></span>  
 <span data-ttu-id="44776-125">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="44776-125">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="44776-126">Output</span><span class="sxs-lookup"><span data-stu-id="44776-126">Output</span></span>  
 <span data-ttu-id="44776-127">Der COM-Apartmentzustand des aktuellen Threads und der Zustand, den der Code versucht hat anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="44776-127">The COM apartment state of the current thread, and the state that the code was attempting to apply.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="44776-128">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="44776-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="44776-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="44776-129">Example</span></span>  
 <span data-ttu-id="44776-130">Im folgenden Codebeispiel wird eine Situation veranschaulicht, die zum Aktivieren dieses MDA führen kann.</span><span class="sxs-lookup"><span data-stu-id="44776-130">The following code example demonstrates a situation that can activate this MDA.</span></span>  
  
```csharp
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="44776-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44776-131">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="44776-132">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="44776-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="44776-133">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="44776-133">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
