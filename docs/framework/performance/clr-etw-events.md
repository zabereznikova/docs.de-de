---
title: CLR-ETW-Ereignisse
description: 'Weitere Informationen finden Sie in den Artikeln über Common Language Runtime (CLR) Ereignis Ablauf Verfolgung für Windows (ETW)-Ereignisse. Es gibt zwei Ereignis Anbieter: den Lauf Zeit Anbieter und den rundownanbieter.'
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
ms.openlocfilehash: 22a2f027462d67d5a933972a7420c5f0e38353e5
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309832"
---
# <a name="clr-etw-events"></a><span data-ttu-id="b92b0-104">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b92b0-104">CLR ETW Events</span></span>
<span data-ttu-id="b92b0-105">Die Themen in diesem Abschnitt beschreiben die Ereignisablaufverfolgung für Windows-Ereignisse (ETW).</span><span class="sxs-lookup"><span data-stu-id="b92b0-105">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="b92b0-106">Jedes Ereignis verfügt über ein zugeordnetes Schlüsselwort und die Ebene, die im Thema [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md) beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b92b0-106">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="b92b0-107">Die CLR verfügt über zwei Anbieter für die Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="b92b0-107">The CLR has two providers for the events:</span></span>  
  
- <span data-ttu-id="b92b0-108">Der Laufzeitanbieter löst Ereignisse in Abhängigkeit von den aktivierten Schlüsselwörtern (Ereigniskategorien) aus.</span><span class="sxs-lookup"><span data-stu-id="b92b0-108">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="b92b0-109">Die GUID des CLR-Laufzeitanbieters ist e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span><span class="sxs-lookup"><span data-stu-id="b92b0-109">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
- <span data-ttu-id="b92b0-110">Der Rundownanbieter, der für spezielle Zwecke genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b92b0-110">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="b92b0-111">Die GUID des CLR-Rundownanbieters ist A669021C-C450-4609-A035-5AF59AF4DF18.</span><span class="sxs-lookup"><span data-stu-id="b92b0-111">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="b92b0-112">Weitere Informationen zu den Anbietern finden Sie unter [CLR-ETW-Anbieter](clr-etw-providers.md).</span><span class="sxs-lookup"><span data-stu-id="b92b0-112">For more information about the providers, see [CLR ETW Providers](clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b92b0-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b92b0-113">In This Section</span></span>  
 [<span data-ttu-id="b92b0-114">Laufzeitinformationsereignisse</span><span class="sxs-lookup"><span data-stu-id="b92b0-114">Runtime Information Events</span></span>](runtime-information-etw-events.md)  
 <span data-ttu-id="b92b0-115">Erfasst Informationen über die Laufzeit, einschließlich der SKU, der Versionsnummer, der Art der Aktivierung der Laufzeit, der Befehlszeilenparameter, mit denen sie gestartet wurde, der GUID (wenn zutreffend) und weiterer wichtiger Informationen.</span><span class="sxs-lookup"><span data-stu-id="b92b0-115">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="b92b0-116">ExceptionThrown_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b92b0-116">Exception Thrown_V1 Event</span></span>](exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="b92b0-117">Erfasst Informationen über Ausnahmen, die ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="b92b0-117">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="b92b0-118">Konfliktereignisse</span><span class="sxs-lookup"><span data-stu-id="b92b0-118">Contention Events</span></span>](contention-etw-events.md)  
 <span data-ttu-id="b92b0-119">Erfasst Informationen über Konflikte bezüglich Überwachungssperren oder nativen Sperren, die von der Laufzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b92b0-119">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="b92b0-120">Threadpoolereignisse</span><span class="sxs-lookup"><span data-stu-id="b92b0-120">Thread Pool Events</span></span>](thread-pool-etw-events.md)  
 <span data-ttu-id="b92b0-121">Erfasst Informationen zu den Arbeitsthreadpools und den I/O-Threadpools.</span><span class="sxs-lookup"><span data-stu-id="b92b0-121">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="b92b0-122">Ladeprogrammereignisse</span><span class="sxs-lookup"><span data-stu-id="b92b0-122">Loader Events</span></span>](loader-etw-events.md)  
 <span data-ttu-id="b92b0-123">Erfasst Informationen zum Laden und Entladen von Anwendungsdomänen, Assemblys und Modulen.</span><span class="sxs-lookup"><span data-stu-id="b92b0-123">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="b92b0-124">Methodenereignisse</span><span class="sxs-lookup"><span data-stu-id="b92b0-124">Method Events</span></span>](method-etw-events.md)  
 <span data-ttu-id="b92b0-125">Erfasst Informationen über CLR-Methoden für die Symbolauflösung.</span><span class="sxs-lookup"><span data-stu-id="b92b0-125">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="b92b0-126">Garbage Collection-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b92b0-126">Garbage Collection Events</span></span>](garbage-collection-etw-events.md)  
 <span data-ttu-id="b92b0-127">Erfasst Informationen zur Garbage Collection, und hilft Ihnen bei der Diagnose und beim Debuggen.</span><span class="sxs-lookup"><span data-stu-id="b92b0-127">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="b92b0-128">JIT-Ablaufverfolgungsereignisse</span><span class="sxs-lookup"><span data-stu-id="b92b0-128">JIT Tracing Events</span></span>](jit-tracing-etw-events.md)  
 <span data-ttu-id="b92b0-129">Erfasst Informationen über JIT-Inlining und Endeaufrufe.</span><span class="sxs-lookup"><span data-stu-id="b92b0-129">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="b92b0-130">Interop-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b92b0-130">Interop Events</span></span>](interop-etw-events.md)  
 <span data-ttu-id="b92b0-131">Erfasst Informationen über die Stubgenerierung und Zwischenspeicherung der Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="b92b0-131">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="b92b0-132">ARM-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b92b0-132">ARM Events</span></span>](application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="b92b0-133">Erfasst detaillierte Diagnoseinformationen über den Status einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="b92b0-133">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="b92b0-134">Sicherheitsereignisse</span><span class="sxs-lookup"><span data-stu-id="b92b0-134">Security Events</span></span>](security-etw-events.md)  
 <span data-ttu-id="b92b0-135">Erfasst Informationen über starke Namen und Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="b92b0-135">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="b92b0-136">Stapelereignis</span><span class="sxs-lookup"><span data-stu-id="b92b0-136">Stack Event</span></span>](stack-etw-event.md)  
 <span data-ttu-id="b92b0-137">Erfasst Informationen, die mit anderen Ereignissen zur Generierung von Stackablaufverfolgungen verwendet werden, nachdem ein Ereignis eingetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b92b0-137">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b92b0-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b92b0-138">See also</span></span>

- [<span data-ttu-id="b92b0-139">Verbessertes Debugging und Leistungsoptimierung mit ETW</span><span class="sxs-lookup"><span data-stu-id="b92b0-139">Improve Debugging And Performance Tuning With ETW</span></span>](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)
- [<span data-ttu-id="b92b0-140">Steuern der Protokollierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b92b0-140">Controlling .NET Framework Logging</span></span>](controlling-logging.md)
- [<span data-ttu-id="b92b0-141">CLR-ETW-Anbieter</span><span class="sxs-lookup"><span data-stu-id="b92b0-141">CLR ETW Providers</span></span>](clr-etw-providers.md)
- [<span data-ttu-id="b92b0-142">CLR-ETW-Schlüsselwörter und -Ebenen</span><span class="sxs-lookup"><span data-stu-id="b92b0-142">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)
- [<span data-ttu-id="b92b0-143">ETW-Ereignisse in der Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="b92b0-143">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
