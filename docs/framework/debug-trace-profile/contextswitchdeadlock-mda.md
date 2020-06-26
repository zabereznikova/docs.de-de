---
title: contextSwitchDeadlock-MDA
description: Informieren Sie sich über den contexzwitchdeadlock-MDA (Managed Debugging Assistant) in .net, der aktiviert wird, wenn während eines COM-Kontext Übergangs ein Deadlock erkannt wird.
ms.date: 03/30/2017
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
ms.openlocfilehash: 52db4f2c88bac4e8cac621cca989fa10acb43f94
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416017"
---
# <a name="contextswitchdeadlock-mda"></a><span data-ttu-id="3a576-103">contextSwitchDeadlock-MDA</span><span class="sxs-lookup"><span data-stu-id="3a576-103">contextSwitchDeadlock MDA</span></span>

<span data-ttu-id="3a576-104">Der `contextSwitchDeadlock`-MDA (Managed Debugging Assistant, Assistent für das verwaltete Debuggen) wird aktiviert, wenn während eines versuchten COM-Kontextübergangs ein Deadlock erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="3a576-104">The `contextSwitchDeadlock` managed debugging assistant (MDA) is activated when a deadlock is detected during an attempted COM context transition.</span></span>

## <a name="symptoms"></a><span data-ttu-id="3a576-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="3a576-105">Symptoms</span></span>

<span data-ttu-id="3a576-106">Das häufigste Symptom ist, dass ein Aufruf einer nicht verwalteten COM-Komponente aus verwaltetem Code nicht zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3a576-106">The most common symptom is that a call on an unmanaged COM component from managed code does not return.</span></span>  <span data-ttu-id="3a576-107">Ein weiteres Symptom ist die im Zeitverlauf zunehmende Speicherauslastung.</span><span class="sxs-lookup"><span data-stu-id="3a576-107">Another symptom is memory usage increasing over time.</span></span>

## <a name="cause"></a><span data-ttu-id="3a576-108">Ursache</span><span class="sxs-lookup"><span data-stu-id="3a576-108">Cause</span></span>

<span data-ttu-id="3a576-109">Die wahrscheinlichste Ursache ist, dass ein Thread in einem Singlethread-Apartment (STA) keine Meldungen weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="3a576-109">The most probable cause is that a single-threaded apartment (STA) thread is not pumping messages.</span></span> <span data-ttu-id="3a576-110">Entweder wartet der STA-Thread, ohne Meldungen weiterzuleiten, oder er führt langwierige Operationen aus und lässt keine Weiterleitungen durch die Meldungswarteschlange zu.</span><span class="sxs-lookup"><span data-stu-id="3a576-110">The STA thread is either waiting without pumping messages or is performing lengthy operations and is not allowing the message queue to pump.</span></span>

<span data-ttu-id="3a576-111">Die im Zeitverlauf zunehmende Speicherauslastung wird durch den Finalizerthread verursacht, der versucht, `Release` für eine nicht verwaltete COM-Komponente aufzurufen, von der keine Rückgabe erfolgt.</span><span class="sxs-lookup"><span data-stu-id="3a576-111">Memory usage increasing over time is caused by the finalizer thread attempting to call `Release` on an unmanaged COM component and that component is not returning.</span></span>  <span data-ttu-id="3a576-112">Dadurch wird verhindert, dass der Finalizer andere Objekte freigibt.</span><span class="sxs-lookup"><span data-stu-id="3a576-112">This prevents the finalizer from reclaiming other objects.</span></span>

<span data-ttu-id="3a576-113">Standardmäßig wird STA als Threadingmodell für den Hauptthread von Visual Basic-Konsolenanwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a576-113">By default, the threading model for the main thread of Visual Basic console applications is STA.</span></span> <span data-ttu-id="3a576-114">Dieser MDA wird aktiviert, wenn ein STA-Thread COM-Interoperabilität entweder direkt oder indirekt über die Common Language Runtime oder ein Drittanbieter-Steuerelement verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a576-114">This MDA is activated if an STA thread uses COM interoperability either directly or indirectly through the common language runtime or a third-party control.</span></span>  <span data-ttu-id="3a576-115">Um zu vermeiden, das dieser MDA in einer Visual Basic-Konsolenanwendung aktiviert wird, wenden Sie das <xref:System.MTAThreadAttribute>-Attribut auf die Hauptmethode an, oder ändern Sie die Anwendung so, dass sie Meldungen weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="3a576-115">To avoid activating this MDA in a Visual Basic console application, apply the <xref:System.MTAThreadAttribute> attribute to the main method or modify the application to pump messages.</span></span>

<span data-ttu-id="3a576-116">Unter Umständen wird dieser MDA fälschlicherweise aktiviert, wenn alle folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="3a576-116">It is possible for this MDA to be falsely activated when all of the following conditions are met:</span></span>

- <span data-ttu-id="3a576-117">Eine Anwendung erstellt entweder direkt oder indirekt über Bibliotheken COM-Komponenten von STA-Threads.</span><span class="sxs-lookup"><span data-stu-id="3a576-117">An application creates COM components from STA threads either directly or indirectly through libraries.</span></span>

- <span data-ttu-id="3a576-118">Die Anwendung wurde im Debugger angehalten, und der Benutzer hat entweder die Ausführung der Anwendung fortgesetzt oder einen Ausführungsschritt durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a576-118">The application was stopped in the debugger and the user either continued the application or performed a step operation.</span></span>

- <span data-ttu-id="3a576-119">Nicht verwaltetes Debuggen ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3a576-119">Unmanaged debugging is not enabled.</span></span>

<span data-ttu-id="3a576-120">Um festzustellen, ob der MDA fälschlicherweise aktiviert wurde, deaktivieren Sie alle Haltepunkte, starten Sie die Anwendung neu, und führen Sie sie ohne Unterbrechung aus.</span><span class="sxs-lookup"><span data-stu-id="3a576-120">To determine if the MDA is being falsely activated, disable all breakpoints, restart the application, and allow it to run without stopping.</span></span> <span data-ttu-id="3a576-121">Wenn der MDA nicht aktiviert wird, war die erste Aktivierung wahrscheinlich falsch.</span><span class="sxs-lookup"><span data-stu-id="3a576-121">If the MDA is not activated, it is likely the initial activation was false.</span></span> <span data-ttu-id="3a576-122">Deaktivieren Sie in diesem Fall den MDA, um eine Störung der Debugsitzung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="3a576-122">In this case, disable the MDA to avoid interference with the debugging session.</span></span>

> [!NOTE]
> <span data-ttu-id="3a576-123">Dieser MDA befindet sich in der Standardeinstellung für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3a576-123">This MDA is in the default set for Visual Studio.</span></span> <span data-ttu-id="3a576-124">Weitere Informationen zum Deaktivieren von MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span><span class="sxs-lookup"><span data-stu-id="3a576-124">For information about how to disable MDAs, see [Diagnosing Errors with Managed Debugging Assistants](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span></span>

## <a name="resolution"></a><span data-ttu-id="3a576-125">Lösung</span><span class="sxs-lookup"><span data-stu-id="3a576-125">Resolution</span></span>

<span data-ttu-id="3a576-126">Befolgen Sie die COM-Regeln hinsichtlich der STA-Meldungsweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="3a576-126">Follow COM rules regarding STA message pumping.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="3a576-127">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3a576-127">Effect on the Runtime</span></span>

<span data-ttu-id="3a576-128">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="3a576-128">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="3a576-129">Es werden nur Angaben über COM-Kontexte gemeldet.</span><span class="sxs-lookup"><span data-stu-id="3a576-129">It only reports data about COM contexts.</span></span>

## <a name="output"></a><span data-ttu-id="3a576-130">Output</span><span class="sxs-lookup"><span data-stu-id="3a576-130">Output</span></span>

<span data-ttu-id="3a576-131">Eine Meldung, die den aktuellen Kontext und den Zielkontext beschreibt.</span><span class="sxs-lookup"><span data-stu-id="3a576-131">A message describing the current context and the target context.</span></span>

## <a name="configuration"></a><span data-ttu-id="3a576-132">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3a576-132">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <contextSwitchDeadlock />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="3a576-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a576-133">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="3a576-134">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="3a576-134">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="3a576-135">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="3a576-135">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
