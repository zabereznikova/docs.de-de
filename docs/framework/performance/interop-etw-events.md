---
title: Interop-ETW-Ereignisse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5670eb910406626096f776d3b4192e2d58d7ce1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="interop-etw-events"></a><span data-ttu-id="f5097-102">Interop-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f5097-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="f5097-103">Interop-Ereignisse erfassen Informationen zur MSIL-Stubgenerierung und -Zwischenspeicherung (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="f5097-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="f5097-104">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="f5097-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="f5097-105">ILStubGenerated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="f5097-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="f5097-106">ILStubCacheHit-Ereignis</span><span class="sxs-lookup"><span data-stu-id="f5097-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="f5097-107">ILStubGenerated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="f5097-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="f5097-108">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="f5097-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="f5097-109">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="f5097-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="f5097-110">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="f5097-110">Keyword for raising the event</span></span>|<span data-ttu-id="f5097-111">Ebene</span><span class="sxs-lookup"><span data-stu-id="f5097-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f5097-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="f5097-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="f5097-113">Information (4)</span><span class="sxs-lookup"><span data-stu-id="f5097-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="f5097-114">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="f5097-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f5097-115">Ereignis</span><span class="sxs-lookup"><span data-stu-id="f5097-115">Event</span></span>|<span data-ttu-id="f5097-116">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f5097-116">Event ID</span></span>|<span data-ttu-id="f5097-117">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="f5097-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="f5097-118">88</span><span class="sxs-lookup"><span data-stu-id="f5097-118">88</span></span>|<span data-ttu-id="f5097-119">Der MSIL-Stub wurde generiert.</span><span class="sxs-lookup"><span data-stu-id="f5097-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="f5097-120">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="f5097-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f5097-121">Feldname</span><span class="sxs-lookup"><span data-stu-id="f5097-121">Field name</span></span>|<span data-ttu-id="f5097-122">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f5097-122">Data type</span></span>|<span data-ttu-id="f5097-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5097-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f5097-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="f5097-124">ModuleID</span></span>|<span data-ttu-id="f5097-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f5097-125">win:UInt16</span></span>|<span data-ttu-id="f5097-126">Der Modulbezeichner.</span><span class="sxs-lookup"><span data-stu-id="f5097-126">The module identifier.</span></span>|  
|<span data-ttu-id="f5097-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="f5097-127">StubMethodID</span></span>|<span data-ttu-id="f5097-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f5097-128">win:UInt64</span></span>|<span data-ttu-id="f5097-129">Der Bezeichner für die Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="f5097-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="f5097-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="f5097-130">StubFlags</span></span>|<span data-ttu-id="f5097-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f5097-131">win:UInt64</span></span>|<span data-ttu-id="f5097-132">Die Flags für den Stub:</span><span class="sxs-lookup"><span data-stu-id="f5097-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="f5097-133">0x1 – Reverse-Interop.</span><span class="sxs-lookup"><span data-stu-id="f5097-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="f5097-134">0x2 – COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="f5097-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="f5097-135">0x4 – Von „NGen.exe“ generierter Stub.</span><span class="sxs-lookup"><span data-stu-id="f5097-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="f5097-136">0x8 – Delegat.</span><span class="sxs-lookup"><span data-stu-id="f5097-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="f5097-137">0x10 – Variables Argument.</span><span class="sxs-lookup"><span data-stu-id="f5097-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="f5097-138">0x20 – Nicht verwalteter Aufgerufener.</span><span class="sxs-lookup"><span data-stu-id="f5097-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="f5097-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="f5097-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="f5097-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f5097-140">win:UInt32</span></span>|<span data-ttu-id="f5097-141">Das Token für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="f5097-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="f5097-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="f5097-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="f5097-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f5097-143">win:UnicodeString</span></span>|<span data-ttu-id="f5097-144">Der Namespace für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="f5097-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="f5097-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="f5097-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="f5097-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f5097-146">win:UnicodeString</span></span>|<span data-ttu-id="f5097-147">Der Name der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="f5097-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="f5097-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="f5097-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="f5097-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f5097-149">win:UnicodeString</span></span>|<span data-ttu-id="f5097-150">Die Signatur der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="f5097-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="f5097-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="f5097-151">NativeMethodSignature</span></span>|<span data-ttu-id="f5097-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f5097-152">win:UnicodeString</span></span>|<span data-ttu-id="f5097-153">Die systemeigene Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="f5097-153">The native method signature.</span></span>|  
|<span data-ttu-id="f5097-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="f5097-154">StubMethodSignature</span></span>|<span data-ttu-id="f5097-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f5097-155">win:UnicodeString</span></span>|<span data-ttu-id="f5097-156">Die Signatur der Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="f5097-156">The stub method signature.</span></span>|  
|<span data-ttu-id="f5097-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="f5097-157">StubMethodILCode</span></span>|<span data-ttu-id="f5097-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f5097-158">win:UnicodeString</span></span>|<span data-ttu-id="f5097-159">Der MSIL-Code für die Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="f5097-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="f5097-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f5097-160">ClrInstanceID</span></span>|<span data-ttu-id="f5097-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f5097-161">win:UInt16</span></span>|<span data-ttu-id="f5097-162">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f5097-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f5097-163">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="f5097-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="f5097-164">ILStubCacheHit-Ereignis</span><span class="sxs-lookup"><span data-stu-id="f5097-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="f5097-165">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="f5097-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f5097-166">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="f5097-166">Keyword for raising the event</span></span>|<span data-ttu-id="f5097-167">Ebene</span><span class="sxs-lookup"><span data-stu-id="f5097-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f5097-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="f5097-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="f5097-169">Information (4)</span><span class="sxs-lookup"><span data-stu-id="f5097-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="f5097-170">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="f5097-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f5097-171">Ereignis</span><span class="sxs-lookup"><span data-stu-id="f5097-171">Event</span></span>|<span data-ttu-id="f5097-172">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f5097-172">Event ID</span></span>|<span data-ttu-id="f5097-173">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="f5097-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="f5097-174">89</span><span class="sxs-lookup"><span data-stu-id="f5097-174">89</span></span>|<span data-ttu-id="f5097-175">Es wurde auf den MSIL-Cache zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="f5097-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="f5097-176">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="f5097-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f5097-177">Feldname</span><span class="sxs-lookup"><span data-stu-id="f5097-177">Field name</span></span>|<span data-ttu-id="f5097-178">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f5097-178">Data type</span></span>|<span data-ttu-id="f5097-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5097-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f5097-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="f5097-180">ModuleID</span></span>|<span data-ttu-id="f5097-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f5097-181">win:UInt16</span></span>|<span data-ttu-id="f5097-182">Der Modulbezeichner.</span><span class="sxs-lookup"><span data-stu-id="f5097-182">The module identifier.</span></span>|  
|<span data-ttu-id="f5097-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="f5097-183">StubMethodID</span></span>|<span data-ttu-id="f5097-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f5097-184">win:UInt64</span></span>|<span data-ttu-id="f5097-185">Der Bezeichner für die Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="f5097-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="f5097-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="f5097-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="f5097-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f5097-187">win:UInt32</span></span>|<span data-ttu-id="f5097-188">Das Token für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="f5097-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="f5097-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="f5097-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="f5097-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f5097-190">win:UnicodeString</span></span>|<span data-ttu-id="f5097-191">Der Namespace für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="f5097-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="f5097-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="f5097-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="f5097-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f5097-193">win:UnicodeString</span></span>|<span data-ttu-id="f5097-194">Der Name der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="f5097-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="f5097-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="f5097-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="f5097-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f5097-196">win:UnicodeString</span></span>|<span data-ttu-id="f5097-197">Die Signatur der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="f5097-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="f5097-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f5097-198">ClrInstanceID</span></span>|<span data-ttu-id="f5097-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f5097-199">win:UInt16</span></span>|<span data-ttu-id="f5097-200">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f5097-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f5097-201">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="f5097-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="f5097-202">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5097-202">See Also</span></span>  
 [<span data-ttu-id="f5097-203">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f5097-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
