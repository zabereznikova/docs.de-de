---
title: Typsystem-Lauf Zeit Ereignisse
description: Weitere Informationen finden Sie unter .net-Lauf Zeit Ereignisse, die Diagnoseinformationen für das .net-Typsystem erfassen, z. b. typeloadstart und typeloadstoppt.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- type system events (CoreCLR)
- ETW, EventPipe, LTTng type system events (CoreCLR)
ms.openlocfilehash: 8eee89cddb0098da2cb449a4be21945adac725e3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "96592079"
---
# <a name="net-runtime-type-events"></a><span data-ttu-id="2a9fa-103">.NET Runtime-typereignisse</span><span class="sxs-lookup"><span data-stu-id="2a9fa-103">.NET runtime type events</span></span>

<span data-ttu-id="2a9fa-104">Diese Ereignisse sammeln Informationen über das Laden von Typen.</span><span class="sxs-lookup"><span data-stu-id="2a9fa-104">These events collect information relating to loading types.</span></span> <span data-ttu-id="2a9fa-105">Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="2a9fa-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="typeloadstart-event"></a><span data-ttu-id="2a9fa-106">Typeloadstart-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2a9fa-106">TypeLoadStart Event</span></span>

|<span data-ttu-id="2a9fa-107">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2a9fa-107">Keyword for raising the event</span></span>|<span data-ttu-id="2a9fa-108">Ereignis</span><span class="sxs-lookup"><span data-stu-id="2a9fa-108">Event</span></span>|<span data-ttu-id="2a9fa-109">Ebene</span><span class="sxs-lookup"><span data-stu-id="2a9fa-109">Level</span></span>|  
|-----------------------------------|-----------|-----------|  
|<span data-ttu-id="2a9fa-110">`TypeDiagnosticKeyword` (0x8000000000)</span><span class="sxs-lookup"><span data-stu-id="2a9fa-110">`TypeDiagnosticKeyword` (0x8000000000)</span></span>|<span data-ttu-id="2a9fa-111">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2a9fa-111">Informational (4)</span></span>|  

|<span data-ttu-id="2a9fa-112">Ereignis</span><span class="sxs-lookup"><span data-stu-id="2a9fa-112">Event</span></span>|<span data-ttu-id="2a9fa-113">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2a9fa-113">Event ID</span></span>|<span data-ttu-id="2a9fa-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2a9fa-114">Description</span></span>|  
|-----------|--------------|-----------------|  
|`TypeLoadStart`|<span data-ttu-id="2a9fa-115">73</span><span class="sxs-lookup"><span data-stu-id="2a9fa-115">73</span></span>|<span data-ttu-id="2a9fa-116">Ein Typlade Vorgang wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="2a9fa-116">A type load has started.</span></span>|

|<span data-ttu-id="2a9fa-117">Feldname</span><span class="sxs-lookup"><span data-stu-id="2a9fa-117">Field name</span></span>|<span data-ttu-id="2a9fa-118">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2a9fa-118">Data type</span></span>|<span data-ttu-id="2a9fa-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2a9fa-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|<span data-ttu-id="2a9fa-120">ID für den Ladevorgang des Typs.</span><span class="sxs-lookup"><span data-stu-id="2a9fa-120">ID for the type load operation.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a9fa-121">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a9fa-121">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="typeloadstop-event"></a><span data-ttu-id="2a9fa-122">Typeloadhalte-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2a9fa-122">TypeLoadStop Event</span></span>

|<span data-ttu-id="2a9fa-123">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2a9fa-123">Keyword for raising the event</span></span>|<span data-ttu-id="2a9fa-124">Ebene</span><span class="sxs-lookup"><span data-stu-id="2a9fa-124">Level</span></span>|  
|-----------------------------------|-----------|-----------|  
|<span data-ttu-id="2a9fa-125">`TypeDiagnosticKeyword` (0x8000000000)</span><span class="sxs-lookup"><span data-stu-id="2a9fa-125">`TypeDiagnosticKeyword` (0x8000000000)</span></span>|<span data-ttu-id="2a9fa-126">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2a9fa-126">Informational (4)</span></span>|  

|<span data-ttu-id="2a9fa-127">Ereignis</span><span class="sxs-lookup"><span data-stu-id="2a9fa-127">Event</span></span>|<span data-ttu-id="2a9fa-128">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2a9fa-128">Event ID</span></span>|<span data-ttu-id="2a9fa-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2a9fa-129">Description</span></span>|  
|-----------|--------------|-----------------|  
|`TypeLoadStop`|<span data-ttu-id="2a9fa-130">74</span><span class="sxs-lookup"><span data-stu-id="2a9fa-130">74</span></span>|<span data-ttu-id="2a9fa-131">Eine typlast ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2a9fa-131">A type load is finished.</span></span>|

|<span data-ttu-id="2a9fa-132">Feldname</span><span class="sxs-lookup"><span data-stu-id="2a9fa-132">Field name</span></span>|<span data-ttu-id="2a9fa-133">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2a9fa-133">Data type</span></span>|<span data-ttu-id="2a9fa-134">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2a9fa-134">Description</span></span>|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|<span data-ttu-id="2a9fa-135">ID für den Ladevorgang des Typs (entspricht der typeloadstartid des entsprechenden typeloadstart-Ereignisses).</span><span class="sxs-lookup"><span data-stu-id="2a9fa-135">ID for the type load operation (matches the corresponding TypeLoadStart event's TypeLoadStartID).</span></span>|
|`LoadLevel`|`win:UInt16`|<span data-ttu-id="2a9fa-136">Lade Ebene des Typs.</span><span class="sxs-lookup"><span data-stu-id="2a9fa-136">Type load level.</span></span>|
|`TypeID`|`win:UInt64`|<span data-ttu-id="2a9fa-137">Zeiger auf den Typhandle.</span><span class="sxs-lookup"><span data-stu-id="2a9fa-137">Pointer to the type handle.</span></span>|
|`TypeName`|`win:UnicodeString`|<span data-ttu-id="2a9fa-138">Der Name des Typs.</span><span class="sxs-lookup"><span data-stu-id="2a9fa-138">Name of the type.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a9fa-139">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a9fa-139">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
