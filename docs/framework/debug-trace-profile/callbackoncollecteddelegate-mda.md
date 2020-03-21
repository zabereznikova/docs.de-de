---
title: CallbackOnCollectedDelegate-MDA
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- managed debugging assistants (MDAs), callback on collected delegates
- MDAs (managed debugging assistants), callback on collected delegates
- callback on delegate after garbage collection
- callbackOnCollectedDelegate MDA
- managed debugging assistants (MDAs), garbage collection
- call back collected delegates
- garbage collection, run-time errors
- delegates [.NET Framework], garbage collection
ms.assetid: 398b0ce0-5cc9-4518-978d-b8263aa21e5b
ms.openlocfilehash: d4ca777fa5b41433eec227762fe315f22ab33cf6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174224"
---
# <a name="callbackoncollecteddelegate-mda"></a><span data-ttu-id="8a716-102">CallbackOnCollectedDelegate-MDA</span><span class="sxs-lookup"><span data-stu-id="8a716-102">callbackOnCollectedDelegate MDA</span></span>
<span data-ttu-id="8a716-103">Der `callbackOnCollectedDelegate`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn das Marshalling eines Delegaten von verwaltetem zu nicht verwaltetem Code als Funktionszeiger durchgeführt wird und nach der Garbage Collection des Delegaten ein Rückruf mit diesem Funktionszeiger erfolgt.</span><span class="sxs-lookup"><span data-stu-id="8a716-103">The `callbackOnCollectedDelegate` managed debugging assistant (MDA) is activated if a delegate is marshaled from managed to unmanaged code as a function pointer and a callback is placed on that function pointer after the delegate has been garbage collected.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8a716-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="8a716-104">Symptoms</span></span>  
 <span data-ttu-id="8a716-105">Beim Versuch, mithilfe von aus verwalteten Delegaten stammenden Funktionszeigern verwalteten Code aufzurufen, treten Zugriffsverletzungen auf.</span><span class="sxs-lookup"><span data-stu-id="8a716-105">Access violations occur when attempting to call into managed code through function pointers that were obtained from managed delegates.</span></span> <span data-ttu-id="8a716-106">Ursache der Zugriffsverletzungen sind keine Programmfehler der CLR (Common Language Runtime), auch wenn dieser Eindruck entsteht, da sie im CLR-Code auftreten.</span><span class="sxs-lookup"><span data-stu-id="8a716-106">These failures, while not common language runtime (CLR) bugs, may appear to be so because the access violation occurs in the CLR code.</span></span>  
  
 <span data-ttu-id="8a716-107">Der Fehler ist nicht konsistent. Manchmal ist der Aufruf mit dem Funktionszeiger erfolgreich und manchmal nicht.</span><span class="sxs-lookup"><span data-stu-id="8a716-107">The failure is not consistent; sometimes the call on the function pointer succeeds and sometimes it fails.</span></span> <span data-ttu-id="8a716-108">Der Fehler tritt möglicherweise nur bei hoher Auslastung oder bei einer zufälligen Anzahl von Versuchen auf.</span><span class="sxs-lookup"><span data-stu-id="8a716-108">The failure might occur only under heavy load or on a random number of attempts.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8a716-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="8a716-109">Cause</span></span>  
 <span data-ttu-id="8a716-110">Für den Delegaten, von dem der Funktionszeiger erstellt und dem nicht verwaltetem Code verfügbar gemacht wurde, erfolgte die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8a716-110">The delegate from which the function pointer was created and exposed to unmanaged code was garbage collected.</span></span> <span data-ttu-id="8a716-111">Wenn die nicht verwaltete Komponente versucht, einen Aufruf mit dem Funktionszeiger durchzuführen, wird eine Zugriffsverletzung generiert.</span><span class="sxs-lookup"><span data-stu-id="8a716-111">When the unmanaged component tries to call on the function pointer, it generates an access violation.</span></span>  
  
 <span data-ttu-id="8a716-112">Das Auftreten des Fehlers ist nicht vorhersagbar, da er vom Zeitpunkt der Garbage Collection abhängt.</span><span class="sxs-lookup"><span data-stu-id="8a716-112">The failure appears random because it depends on when garbage collection occurs.</span></span> <span data-ttu-id="8a716-113">Wenn ein Delegat für die Garbage Collection freigegeben ist und diese nach dem Rückruf erfolgt, ist der Aufruf erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8a716-113">If a delegate is eligible for collection, the garbage collection can occur after the callback and the call succeeds.</span></span> <span data-ttu-id="8a716-114">Wenn zu einem anderen Zeitpunkt die Garbage Collection vor dem Rückruf erfolgt, tritt eine Zugriffsverletzung auf, und das Programm wird beendet.</span><span class="sxs-lookup"><span data-stu-id="8a716-114">At other times, the garbage collection occurs before the callback, the callback generates an access violation, and the program stops.</span></span>  
  
 <span data-ttu-id="8a716-115">Die Fehlerwahrscheinlichkeit hängt vom Zeitraum zwischen dem Marshalling des Delegaten und dem Rückruf mithilfe des Funktionszeigers sowie von der Häufigkeit der Garbage Collection ab.</span><span class="sxs-lookup"><span data-stu-id="8a716-115">The probability of the failure depends on the time between marshaling the delegate and the callback on the function pointer as well as the frequency of garbage collections.</span></span> <span data-ttu-id="8a716-116">Der Fehler tritt sporadisch auf, wenn der Zeitraum zwischen dem Marshalling des Delegaten und dem folgenden Rückruf kurz ist.</span><span class="sxs-lookup"><span data-stu-id="8a716-116">The failure is sporadic if the time between marshaling the delegate and the ensuing callback is short.</span></span> <span data-ttu-id="8a716-117">Dies ist gewöhnlich der Fall, wenn die nicht verwaltete Methode, der der Funktionszeiger übergeben wird, diesen nicht zur späteren Verwendung speichert, sondern mit ihm sofort einen Rückruf ausführt, um den entsprechenden Vorgang vor dem Verlassen der Methode abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="8a716-117">This is usually the case if the unmanaged method receiving the function pointer does not save the function pointer for later use but instead calls back on the function pointer immediately to complete its operation before returning.</span></span> <span data-ttu-id="8a716-118">Die Häufigkeit der Garbage Collection erhöht sich auch, wenn ein System stark ausgelastet ist. Dabei steigt die Wahrscheinlichkeit, dass vor dem Rückruf eine Garbage Collection erfolgt.</span><span class="sxs-lookup"><span data-stu-id="8a716-118">Similarly, more garbage collections occur when a system is under heavy load, which makes it more likely that a garbage collection will occur before the callback.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8a716-119">Lösung</span><span class="sxs-lookup"><span data-stu-id="8a716-119">Resolution</span></span>  
 <span data-ttu-id="8a716-120">Nach dem Marshalling eines Delegaten in einen nicht verwalteten Funktionszeiger ist es für den Garbage Collector unmöglich, dessen Lebensdauer zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="8a716-120">Once a delegate has been marshaled out as an unmanaged function pointer, the garbage collector cannot track its lifetime.</span></span> <span data-ttu-id="8a716-121">Stattdessen muss der Programmcode für die Lebensdauer des nicht verwalteten Funktionszeigers einen Verweis auf den Delegaten aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="8a716-121">Instead, your code must keep a reference to the delegate for the lifetime of the unmanaged function pointer.</span></span> <span data-ttu-id="8a716-122">Bevor dies jedoch möglich ist, müssen Sie zuerst ermitteln, welcher Delegat durch die Garbage Collection bereinigt wurde.</span><span class="sxs-lookup"><span data-stu-id="8a716-122">But before you can do that, you first must identify which delegate was collected.</span></span> <span data-ttu-id="8a716-123">Wenn der MDA aktiviert wird, stellt er den Typnamen des Delegaten bereit.</span><span class="sxs-lookup"><span data-stu-id="8a716-123">When the MDA is activated, it provides the type name of the delegate.</span></span> <span data-ttu-id="8a716-124">Durchsuchen Sie mithilfe dieses Namens den Programmcode nach Plattformaufruf- oder COM-Signaturen, die einen Delegaten an nicht verwalteten Code übergeben.</span><span class="sxs-lookup"><span data-stu-id="8a716-124">Use this name to search your code for platform invoke or COM signatures that pass that delegate out to unmanaged code.</span></span> <span data-ttu-id="8a716-125">Der problematische Delegat wird über einen dieser Aufrufsites übergeben.</span><span class="sxs-lookup"><span data-stu-id="8a716-125">The offending delegate is passed out through one of these call sites.</span></span> <span data-ttu-id="8a716-126">Sie können auch den `gcUnmanagedToManaged`-MDA aktivieren, um vor jedem Rückruf in die CLR eine Garbage Collection zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8a716-126">You can also enable the `gcUnmanagedToManaged` MDA to force a garbage collection before every callback into the runtime.</span></span> <span data-ttu-id="8a716-127">Auf diese Weise wird die durch die Garbage Collection bedingte Ungewissheit beseitigt, indem sichergestellt wird, dass vor dem Rückruf stets eine Garbage Collection erfolgt.</span><span class="sxs-lookup"><span data-stu-id="8a716-127">This will remove the uncertainty introduced by the garbage collection by ensuring that a garbage collection always occurs before the callback.</span></span> <span data-ttu-id="8a716-128">Nachdem Sie ermittelt haben, welcher Delegat durch die Garbage Collection erfasst wurde, ändern Sie den Programmcode so, dass für die Lebensdauer des gemarshallten nicht verwalteten Funktionszeigers ein Verweis auf diesen Delegaten auf der verwalteten Seite verbleibt.</span><span class="sxs-lookup"><span data-stu-id="8a716-128">Once you know what delegate was collected, change your code to keep a reference to that delegate on the managed side for the lifetime of the marshaled unmanaged function pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8a716-129">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="8a716-129">Effect on the Runtime</span></span>  
 <span data-ttu-id="8a716-130">Beim Marshalling von Delegaten als Funktionszeiger wird von der CLR ein Thunk zugeordnet, der für den Übergang vom nicht verwalteten zum verwalteten Code sorgt.</span><span class="sxs-lookup"><span data-stu-id="8a716-130">When delegates are marshaled as function pointers, the runtime allocates a thunk that does the transition from unmanaged to managed.</span></span> <span data-ttu-id="8a716-131">Der nicht verwaltete Code ruft dann diesen Thunk auf, bevor schließlich der verwaltete Delegat aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8a716-131">This thunk is what the unmanaged code actually calls before the managed delegate is finally invoked.</span></span> <span data-ttu-id="8a716-132">Ohne aktivierten `callbackOnCollectedDelegate`-MDA wird der nicht verwaltete Marshallingcode gelöscht, wenn für den Delegaten die Garbage Collection erfolgt.</span><span class="sxs-lookup"><span data-stu-id="8a716-132">Without the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is deleted when the delegate is collected.</span></span> <span data-ttu-id="8a716-133">Mit aktiviertem `callbackOnCollectedDelegate`-MDA wird der nicht verwaltete Marshallingcode nicht sofort gelöscht, wenn für den Delegaten die Garbage Collection erfolgt.</span><span class="sxs-lookup"><span data-stu-id="8a716-133">With the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is not immediately deleted when the delegate is collected.</span></span> <span data-ttu-id="8a716-134">Vielmehr werden standardmäßig die letzten 1.000 Instanzen aufbewahrt und geändert, um bei einem Aufruf den MDA zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8a716-134">Instead, the last 1,000 instances are kept alive by default and changed to activate the MDA when called.</span></span> <span data-ttu-id="8a716-135">Der Thunk wird schließlich gelöscht, nachdem für weitere 1.001 gemarshallte Delegaten die Garbage Collection erfolgte.</span><span class="sxs-lookup"><span data-stu-id="8a716-135">The thunk is eventually deleted after 1,001 more marshaled delegates are collected.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8a716-136">Output</span><span class="sxs-lookup"><span data-stu-id="8a716-136">Output</span></span>  
 <span data-ttu-id="8a716-137">Der MDA meldet den Typnamen des Delegaten, für den vor einem Rückruf mithilfe des entsprechenden nicht verwalteten Funktionszeigers eine Garbage Collection erfolgte.</span><span class="sxs-lookup"><span data-stu-id="8a716-137">The MDA reports the type name of the delegate that was collected before a callback was attempted on its unmanaged function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8a716-138">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8a716-138">Configuration</span></span>  
 <span data-ttu-id="8a716-139">Im folgenden Beispiel sind die Konfigurationsoptionen der Anwendung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8a716-139">The following example shows the application configuration options.</span></span> <span data-ttu-id="8a716-140">Dabei wird als Anzahl der vom MDA aktiv gehaltenen Thunks 1.500 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8a716-140">It sets the number of thunks the MDA keeps alive to 1,500.</span></span> <span data-ttu-id="8a716-141">Der Standardwert für `listSize` beträgt 1.000, der Mindestwert 50 und der Höchstwert 2.000.</span><span class="sxs-lookup"><span data-stu-id="8a716-141">The default `listSize` value is 1,000, the minimum is 50, and the maximum is 2,000.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <callbackOnCollectedDelegate listSize="1500" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="8a716-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8a716-142">Example</span></span>  
 <span data-ttu-id="8a716-143">Im folgenden Beispiel wird eine Situation veranschaulicht, die zum Aktivieren dieses MDA führen kann:</span><span class="sxs-lookup"><span data-stu-id="8a716-143">The following example demonstrates a situation that can activate this MDA:</span></span>  
  
```cpp
// Library.cpp : Defines the unmanaged entry point for the DLL application.  
#include "windows.h"  
#include "stdio.h"  
  
void (__stdcall *g_pfTarget)();  
  
void __stdcall Initialize(void __stdcall pfTarget())  
{  
    g_pfTarget = pfTarget;  
}  
  
void __stdcall Callback()  
{  
    g_pfTarget();  
}
```

```csharp
// C# Client  
using System;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public delegate void DCallback();  
  
    public static void Main()  
    {  
        new Entry();  
        Initialize(Target);  
        GC.Collect();  
        GC.WaitForPendingFinalizers();  
        Callback();  
    }  
  
    public static void Target()  
    {
    }  
  
    [DllImport("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Initialize(DCallback pfDelegate);  
  
    [DllImport ("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Callback();  
  
    ~Entry() { Console.Error.WriteLine("Entry Collected"); }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a716-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a716-144">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="8a716-145">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="8a716-145">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="8a716-146">Interop-Marshalling</span><span class="sxs-lookup"><span data-stu-id="8a716-146">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
- [<span data-ttu-id="8a716-147">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="8a716-147">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)
