---
title: contextSwitchDeadlock-MDA
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
ms.openlocfilehash: e3fc4a2cb35cdcc713ba0ef362071083af08a27b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217561"
---
# <a name="contextswitchdeadlock-mda"></a><span data-ttu-id="6006e-102">contextSwitchDeadlock-MDA</span><span class="sxs-lookup"><span data-stu-id="6006e-102">contextSwitchDeadlock MDA</span></span>

<span data-ttu-id="6006e-103">Der `contextSwitchDeadlock`-MDA (Managed Debugging Assistant, Assistent für das verwaltete Debuggen) wird aktiviert, wenn während eines versuchten COM-Kontextübergangs ein Deadlock erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="6006e-103">The `contextSwitchDeadlock` managed debugging assistant (MDA) is activated when a deadlock is detected during an attempted COM context transition.</span></span>

## <a name="symptoms"></a><span data-ttu-id="6006e-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="6006e-104">Symptoms</span></span>

<span data-ttu-id="6006e-105">Das häufigste Symptom ist, dass ein Aufruf einer nicht verwalteten COM-Komponente aus verwaltetem Code nicht zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6006e-105">The most common symptom is that a call on an unmanaged COM component from managed code does not return.</span></span>  <span data-ttu-id="6006e-106">Ein weiteres Symptom ist die im Zeitverlauf zunehmende Speicherauslastung.</span><span class="sxs-lookup"><span data-stu-id="6006e-106">Another symptom is memory usage increasing over time.</span></span>

## <a name="cause"></a><span data-ttu-id="6006e-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="6006e-107">Cause</span></span>

<span data-ttu-id="6006e-108">Die wahrscheinlichste Ursache ist, dass ein Thread in einem Singlethread-Apartment (STA) keine Meldungen weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="6006e-108">The most probable cause is that a single-threaded apartment (STA) thread is not pumping messages.</span></span> <span data-ttu-id="6006e-109">Entweder wartet der STA-Thread, ohne Meldungen weiterzuleiten, oder er führt langwierige Operationen aus und lässt keine Weiterleitungen durch die Meldungswarteschlange zu.</span><span class="sxs-lookup"><span data-stu-id="6006e-109">The STA thread is either waiting without pumping messages or is performing lengthy operations and is not allowing the message queue to pump.</span></span>

<span data-ttu-id="6006e-110">Die im Zeitverlauf zunehmende Speicherauslastung wird durch den Finalizerthread verursacht, der versucht, `Release` für eine nicht verwaltete COM-Komponente aufzurufen, von der keine Rückgabe erfolgt.</span><span class="sxs-lookup"><span data-stu-id="6006e-110">Memory usage increasing over time is caused by the finalizer thread attempting to call `Release` on an unmanaged COM component and that component is not returning.</span></span>  <span data-ttu-id="6006e-111">Dadurch wird verhindert, dass der Finalizer andere Objekte freigibt.</span><span class="sxs-lookup"><span data-stu-id="6006e-111">This prevents the finalizer from reclaiming other objects.</span></span>

<span data-ttu-id="6006e-112">Standardmäßig wird STA als Threadingmodell für den Hauptthread von Visual Basic-Konsolenanwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="6006e-112">By default, the threading model for the main thread of Visual Basic console applications is STA.</span></span> <span data-ttu-id="6006e-113">Dieser MDA wird aktiviert, wenn ein STA-Thread COM-Interoperabilität entweder direkt oder indirekt über die Common Language Runtime oder ein Drittanbieter-Steuerelement verwendet.</span><span class="sxs-lookup"><span data-stu-id="6006e-113">This MDA is activated if an STA thread uses COM interoperability either directly or indirectly through the common language runtime or a third-party control.</span></span>  <span data-ttu-id="6006e-114">Um zu vermeiden, das dieser MDA in einer Visual Basic-Konsolenanwendung aktiviert wird, wenden Sie das <xref:System.MTAThreadAttribute>-Attribut auf die Hauptmethode an, oder ändern Sie die Anwendung so, dass sie Meldungen weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="6006e-114">To avoid activating this MDA in a Visual Basic console application, apply the <xref:System.MTAThreadAttribute> attribute to the main method or modify the application to pump messages.</span></span>

<span data-ttu-id="6006e-115">Unter Umständen wird dieser MDA fälschlicherweise aktiviert, wenn alle folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="6006e-115">It is possible for this MDA to be falsely activated when all of the following conditions are met:</span></span>

- <span data-ttu-id="6006e-116">Eine Anwendung erstellt entweder direkt oder indirekt über Bibliotheken COM-Komponenten von STA-Threads.</span><span class="sxs-lookup"><span data-stu-id="6006e-116">An application creates COM components from STA threads either directly or indirectly through libraries.</span></span>

- <span data-ttu-id="6006e-117">Die Anwendung wurde im Debugger angehalten, und der Benutzer hat entweder die Ausführung der Anwendung fortgesetzt oder einen Ausführungsschritt durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="6006e-117">The application was stopped in the debugger and the user either continued the application or performed a step operation.</span></span>

- <span data-ttu-id="6006e-118">Nicht verwaltetes Debuggen ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6006e-118">Unmanaged debugging is not enabled.</span></span>

<span data-ttu-id="6006e-119">Um festzustellen, ob der MDA fälschlicherweise aktiviert wurde, deaktivieren Sie alle Haltepunkte, starten Sie die Anwendung neu, und führen Sie sie ohne Unterbrechung aus.</span><span class="sxs-lookup"><span data-stu-id="6006e-119">To determine if the MDA is being falsely activated, disable all breakpoints, restart the application, and allow it to run without stopping.</span></span> <span data-ttu-id="6006e-120">Wenn der MDA nicht aktiviert wird, war die erste Aktivierung wahrscheinlich falsch.</span><span class="sxs-lookup"><span data-stu-id="6006e-120">If the MDA is not activated, it is likely the initial activation was false.</span></span> <span data-ttu-id="6006e-121">Deaktivieren Sie in diesem Fall den MDA, um eine Störung der Debugsitzung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6006e-121">In this case, disable the MDA to avoid interference with the debugging session.</span></span>

> [!NOTE]
> <span data-ttu-id="6006e-122">Dieser MDA befindet sich in der Standardeinstellung für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6006e-122">This MDA is in the default set for Visual Studio.</span></span> <span data-ttu-id="6006e-123">Weitere Informationen zum Deaktivieren von MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span><span class="sxs-lookup"><span data-stu-id="6006e-123">For information about how to disable MDAs, see [Diagnosing Errors with Managed Debugging Assistants](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span></span>

## <a name="resolution"></a><span data-ttu-id="6006e-124">Lösung</span><span class="sxs-lookup"><span data-stu-id="6006e-124">Resolution</span></span>

<span data-ttu-id="6006e-125">Befolgen Sie die COM-Regeln hinsichtlich der STA-Meldungsweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="6006e-125">Follow COM rules regarding STA message pumping.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="6006e-126">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6006e-126">Effect on the Runtime</span></span>

<span data-ttu-id="6006e-127">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="6006e-127">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="6006e-128">Es werden nur Angaben über COM-Kontexte gemeldet.</span><span class="sxs-lookup"><span data-stu-id="6006e-128">It only reports data about COM contexts.</span></span>

## <a name="output"></a><span data-ttu-id="6006e-129">Output</span><span class="sxs-lookup"><span data-stu-id="6006e-129">Output</span></span>

<span data-ttu-id="6006e-130">Eine Meldung, die den aktuellen Kontext und den Zielkontext beschreibt.</span><span class="sxs-lookup"><span data-stu-id="6006e-130">A message describing the current context and the target context.</span></span>

## <a name="configuration"></a><span data-ttu-id="6006e-131">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6006e-131">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <contextSwitchDeadlock />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="6006e-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6006e-132">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="6006e-133">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="6006e-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="6006e-134">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="6006e-134">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
