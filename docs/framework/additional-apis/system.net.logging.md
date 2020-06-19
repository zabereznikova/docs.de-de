---
title: Logging-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Logging
- System.Net.Logging.Associate
- System.Net.Logging.Enter
- System.Net.Logging.Exception
- System.Net.Logging.Exit
- System.Net.Logging.get_Http
- System.Net.Logging.get_On
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ad85fdd41252ed147eb5fe1a9db029db046d720c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990475"
---
# <a name="logging-class"></a><span data-ttu-id="ba79d-102">Logging-Klasse</span><span class="sxs-lookup"><span data-stu-id="ba79d-102">Logging class</span></span>

<span data-ttu-id="ba79d-103">Bietet Funktionen für die Ablauf Verfolgungs Protokollierung</span><span class="sxs-lookup"><span data-stu-id="ba79d-103">Provides trace logging functionality.</span></span>

```csharp
internal class Logging
```

> [!WARNING]
> <span data-ttu-id="ba79d-104">Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba79d-104">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ba79d-105">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="ba79d-105">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="associate-method"></a><span data-ttu-id="ba79d-106">Methode zuordnen</span><span class="sxs-lookup"><span data-stu-id="ba79d-106">Associate method</span></span>

<span data-ttu-id="ba79d-107">Protokolliert Informationen, die zwei-Objekten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ba79d-107">Logs information that two objects are associated with each other.</span></span>

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-108">Parameters</span></span>

- <span data-ttu-id="ba79d-109">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-109">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-110">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-110">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-111">`objA` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ba79d-111">`objA` <xref:System.Object></span></span>

  <span data-ttu-id="ba79d-112">Das Objekt, das zugeordnet werden soll `objB` .</span><span class="sxs-lookup"><span data-stu-id="ba79d-112">The object to associate with `objB`.</span></span>

- <span data-ttu-id="ba79d-113">`objB` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ba79d-113">`objB` <xref:System.Object></span></span>

  <span data-ttu-id="ba79d-114">Das Objekt, das zugeordnet werden soll `objA` .</span><span class="sxs-lookup"><span data-stu-id="ba79d-114">The object to associate with `objA`.</span></span>

## <a name="entertracesource-object-string-string-method"></a><span data-ttu-id="ba79d-115">Enter (TraceSource, Object, String, String)-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-115">Enter(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="ba79d-116">Protokolliert den Eingang einer Methode.</span><span class="sxs-lookup"><span data-stu-id="ba79d-116">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-117">Parameters</span></span>

- <span data-ttu-id="ba79d-118">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-118">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-119">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-119">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-120">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ba79d-120">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="ba79d-121">Das-Objekt, für das die-Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba79d-121">The object that the method was called on.</span></span>

- <span data-ttu-id="ba79d-122">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-122">`method` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-123">Die Methode, die eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-123">The method that is being entered.</span></span>

- <span data-ttu-id="ba79d-124">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-124">`param` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-125">Die Parameter, die an die-Methode übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="ba79d-125">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-object-string-object-method"></a><span data-ttu-id="ba79d-126">Enter (TraceSource, Object, String, Object)-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-126">Enter(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="ba79d-127">Protokolliert den Eingang einer Methode.</span><span class="sxs-lookup"><span data-stu-id="ba79d-127">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-128">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-128">Parameters</span></span>

- <span data-ttu-id="ba79d-129">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-129">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-130">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-130">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-131">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ba79d-131">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="ba79d-132">Das-Objekt, für das die-Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba79d-132">The object that the method was called on.</span></span>

- <span data-ttu-id="ba79d-133">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-133">`method` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-134">Die Methode, die eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-134">The method that is being entered.</span></span>

- <span data-ttu-id="ba79d-135">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ba79d-135">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="ba79d-136">Die Parameter, die an die-Methode übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="ba79d-136">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-string-method"></a><span data-ttu-id="ba79d-137">Enter (TraceSource, String, String, String)-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-137">Enter(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="ba79d-138">Protokolliert den Eingang einer Methode.</span><span class="sxs-lookup"><span data-stu-id="ba79d-138">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-139">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-139">Parameters</span></span>

- <span data-ttu-id="ba79d-140">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-140">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-141">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-141">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-142">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-142">`obj` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-143">Das-Objekt, für das die-Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba79d-143">The object that the method was called on.</span></span>

- <span data-ttu-id="ba79d-144">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-144">`method` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-145">Die Methode, die eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-145">The method that is being entered.</span></span>

- <span data-ttu-id="ba79d-146">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-146">`param` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-147">Die Parameter, die an die-Methode übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="ba79d-147">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-object-method"></a><span data-ttu-id="ba79d-148">Enter (TraceSource, String, String, Object)-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-148">Enter(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="ba79d-149">Protokolliert den Eingang einer Methode.</span><span class="sxs-lookup"><span data-stu-id="ba79d-149">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-150">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-150">Parameters</span></span>

- <span data-ttu-id="ba79d-151">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-151">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-152">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-152">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-153">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-153">`obj` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-154">Das-Objekt, für das die-Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba79d-154">The object that the method was called on.</span></span>

- <span data-ttu-id="ba79d-155">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-155">`method` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-156">Die Methode, die eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-156">The method that is being entered.</span></span>

- <span data-ttu-id="ba79d-157">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ba79d-157">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="ba79d-158">Die Parameter, die an die-Methode übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="ba79d-158">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-method"></a><span data-ttu-id="ba79d-159">Enter (TraceSource, String, String)-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-159">Enter(TraceSource, string, string) method</span></span>

<span data-ttu-id="ba79d-160">Protokolliert den Eingang einer Methode.</span><span class="sxs-lookup"><span data-stu-id="ba79d-160">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-161">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-161">Parameters</span></span>

- <span data-ttu-id="ba79d-162">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-162">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-163">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-163">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-164">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-164">`method` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-165">Die Methode, die eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-165">The method that is being entered.</span></span>

- <span data-ttu-id="ba79d-166">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-166">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-167">Die Parameter, die an die-Methode übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="ba79d-167">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-method"></a><span data-ttu-id="ba79d-168">Enter (TraceSource, String)-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-168">Enter(TraceSource, string) method</span></span>

<span data-ttu-id="ba79d-169">Protokolliert den Eingang einer Methode.</span><span class="sxs-lookup"><span data-stu-id="ba79d-169">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-170">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-170">Parameters</span></span>

- <span data-ttu-id="ba79d-171">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-171">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-172">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-172">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-173">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-173">`msg` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-174">Die Eingangs Nachricht, die an der Ablauf Verfolgungs Quelle protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-174">The entrance message to log to the trace source.</span></span>

## <a name="exception-method"></a><span data-ttu-id="ba79d-175">Exception-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-175">Exception method</span></span>

<span data-ttu-id="ba79d-176">Protokolliert eine Ausnahme und stellt den Einzug wieder her.</span><span class="sxs-lookup"><span data-stu-id="ba79d-176">Logs an exception and restores indentation.</span></span>

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-177">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-177">Parameters</span></span>

- <span data-ttu-id="ba79d-178">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-178">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-179">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-179">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-180">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ba79d-180">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="ba79d-181">Das-Objekt, für das die Methode, die eine Ausnahme ausgelöst hat, aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba79d-181">The object that the method that threw an exception was called on.</span></span>

- <span data-ttu-id="ba79d-182">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-182">`method` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-183">Die Methode, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="ba79d-183">The method that threw the exception.</span></span>

- <span data-ttu-id="ba79d-184">`e` <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="ba79d-184">`e` <xref:System.Exception></span></span>

  <span data-ttu-id="ba79d-185">Die ausgelöste Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="ba79d-185">The exception that was thrown.</span></span>

## <a name="exittracesource-object-string-object-method"></a><span data-ttu-id="ba79d-186">Exit (TraceSource, Object, String, Object)-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-186">Exit(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="ba79d-187">Protokolle werden aus einer Funktion beendet.</span><span class="sxs-lookup"><span data-stu-id="ba79d-187">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-188">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-188">Parameters</span></span>

- <span data-ttu-id="ba79d-189">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-189">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-190">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-190">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-191">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ba79d-191">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="ba79d-192">Das-Objekt, für das die-Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba79d-192">The object that the method was called on.</span></span>

- <span data-ttu-id="ba79d-193">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-193">`method` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-194">Die Methode, die beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-194">The method that is being exited.</span></span>

- <span data-ttu-id="ba79d-195">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ba79d-195">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="ba79d-196">Der Wert, der von der-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-196">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-object-method"></a><span data-ttu-id="ba79d-197">Exit (TraceSource, String, String, Object)-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-197">Exit(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="ba79d-198">Protokolle werden aus einer Funktion beendet.</span><span class="sxs-lookup"><span data-stu-id="ba79d-198">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-199">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-199">Parameters</span></span>

- <span data-ttu-id="ba79d-200">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-200">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-201">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-201">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-202">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-202">`obj` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-203">Das-Objekt, für das die-Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba79d-203">The object that the method was called on.</span></span>

- <span data-ttu-id="ba79d-204">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-204">`method` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-205">Die Methode, die beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-205">The method that is being exited.</span></span>

- <span data-ttu-id="ba79d-206">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ba79d-206">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="ba79d-207">Der Wert, der von der-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-207">The value that's being returned by the method.</span></span>

## <a name="exittracesource-object-string-string-method"></a><span data-ttu-id="ba79d-208">Exit (TraceSource, Object, String, String)-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-208">Exit(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="ba79d-209">Protokolle werden aus einer Funktion beendet.</span><span class="sxs-lookup"><span data-stu-id="ba79d-209">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-210">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-210">Parameters</span></span>

- <span data-ttu-id="ba79d-211">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-211">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-212">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-212">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-213">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ba79d-213">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="ba79d-214">Das-Objekt, für das die-Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba79d-214">The object that the method was called on.</span></span>

- <span data-ttu-id="ba79d-215">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-215">`method` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-216">Die Methode, die beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-216">The method that is being exited.</span></span>

- <span data-ttu-id="ba79d-217">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-217">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-218">Der Wert, der von der-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-218">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-string-method"></a><span data-ttu-id="ba79d-219">Exit (TraceSource, String, String, String)-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-219">Exit(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="ba79d-220">Protokolle werden aus einer Funktion beendet.</span><span class="sxs-lookup"><span data-stu-id="ba79d-220">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-221">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-221">Parameters</span></span>

- <span data-ttu-id="ba79d-222">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-222">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-223">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-223">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-224">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-224">`obj` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-225">Das-Objekt, für das die-Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba79d-225">The object that the method was called on.</span></span>

- <span data-ttu-id="ba79d-226">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-226">`method` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-227">Die Methode, die beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-227">The method that is being exited.</span></span>

- <span data-ttu-id="ba79d-228">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-228">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-229">Der Wert, der von der-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-229">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-method"></a><span data-ttu-id="ba79d-230">Exit (TraceSource, String, String)-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-230">Exit(TraceSource, string, string) method</span></span>

<span data-ttu-id="ba79d-231">Protokolle werden aus einer Funktion beendet.</span><span class="sxs-lookup"><span data-stu-id="ba79d-231">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-232">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-232">Parameters</span></span>

- <span data-ttu-id="ba79d-233">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-233">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-234">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-234">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-235">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-235">`method` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-236">Die Methode, die beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba79d-236">The method that is being exited.</span></span>

- <span data-ttu-id="ba79d-237">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-237">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-238">Die Parameter, die an die Methode, die beendet wird, übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="ba79d-238">The parameters that were passed to the method that's being exited.</span></span>

## <a name="exittracesource-string-method"></a><span data-ttu-id="ba79d-239">Exit (TraceSource, String)-Methode</span><span class="sxs-lookup"><span data-stu-id="ba79d-239">Exit(TraceSource, string) method</span></span>

<span data-ttu-id="ba79d-240">Protokolle werden aus einer Funktion beendet.</span><span class="sxs-lookup"><span data-stu-id="ba79d-240">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="ba79d-241">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba79d-241">Parameters</span></span>

- <span data-ttu-id="ba79d-242">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ba79d-242">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ba79d-243">Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-243">The trace source to log the event to.</span></span>

- <span data-ttu-id="ba79d-244">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ba79d-244">`msg` <xref:System.String></span></span>

  <span data-ttu-id="ba79d-245">Die Exit-Meldung, die an die Ablauf Verfolgungs Quelle protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba79d-245">The exit message to log to the trace source.</span></span>

## <a name="http-property"></a><span data-ttu-id="ba79d-246">Http-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ba79d-246">Http property</span></span>

<span data-ttu-id="ba79d-247">Ruft die Ablauf Verfolgungs Quelle für "System .net. http" ab.</span><span class="sxs-lookup"><span data-stu-id="ba79d-247">Gets the trace source for "System.Net.Http".</span></span>

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a><span data-ttu-id="ba79d-248">Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="ba79d-248">Property value</span></span>

<xref:System.Diagnostics.TraceSource>\
<span data-ttu-id="ba79d-249">Die Ablauf Verfolgungs Quelle für "System .net. http" oder, `null` Wenn die Protokollierung nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ba79d-249">The trace source for "System.Net.Http", or `null` if logging is not enabled.</span></span>

## <a name="on-property"></a><span data-ttu-id="ba79d-250">On-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ba79d-250">On property</span></span>

<span data-ttu-id="ba79d-251">Ruft einen Wert ab, der angibt, ob die Protokollierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ba79d-251">Gets a value that indicates whether logging is enabled.</span></span>

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a><span data-ttu-id="ba79d-252">Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="ba79d-252">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="ba79d-253">`true`, wenn die Protokollierung aktiviert ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="ba79d-253">`true` if logging is enabled; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="ba79d-254">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ba79d-254">Requirements</span></span>

<span data-ttu-id="ba79d-255">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="ba79d-255">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="ba79d-256">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="ba79d-256">**Assembly:** System (in System.dll)</span></span>
