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
ms.openlocfilehash: 55097e38161ea5c76f4e46584241344ec5a52cb9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="interop-etw-events"></a><span data-ttu-id="382eb-102">Interop-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="382eb-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="382eb-103">Interop-Ereignisse erfassen Informationen zur MSIL-Stubgenerierung und -Zwischenspeicherung (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="382eb-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="382eb-104">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="382eb-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="382eb-105">ILStubGenerated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="382eb-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="382eb-106">ILStubCacheHit-Ereignis</span><span class="sxs-lookup"><span data-stu-id="382eb-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="382eb-107">ILStubGenerated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="382eb-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="382eb-108">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="382eb-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="382eb-109">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="382eb-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="382eb-110">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="382eb-110">Keyword for raising the event</span></span>|<span data-ttu-id="382eb-111">Ebene</span><span class="sxs-lookup"><span data-stu-id="382eb-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="382eb-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="382eb-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="382eb-113">Information (4)</span><span class="sxs-lookup"><span data-stu-id="382eb-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="382eb-114">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="382eb-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="382eb-115">Ereignis</span><span class="sxs-lookup"><span data-stu-id="382eb-115">Event</span></span>|<span data-ttu-id="382eb-116">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="382eb-116">Event ID</span></span>|<span data-ttu-id="382eb-117">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="382eb-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="382eb-118">88</span><span class="sxs-lookup"><span data-stu-id="382eb-118">88</span></span>|<span data-ttu-id="382eb-119">Der MSIL-Stub wurde generiert.</span><span class="sxs-lookup"><span data-stu-id="382eb-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="382eb-120">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="382eb-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="382eb-121">Feldname</span><span class="sxs-lookup"><span data-stu-id="382eb-121">Field name</span></span>|<span data-ttu-id="382eb-122">Datentyp</span><span class="sxs-lookup"><span data-stu-id="382eb-122">Data type</span></span>|<span data-ttu-id="382eb-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="382eb-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="382eb-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="382eb-124">ModuleID</span></span>|<span data-ttu-id="382eb-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="382eb-125">win:UInt16</span></span>|<span data-ttu-id="382eb-126">Der Modulbezeichner.</span><span class="sxs-lookup"><span data-stu-id="382eb-126">The module identifier.</span></span>|  
|<span data-ttu-id="382eb-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="382eb-127">StubMethodID</span></span>|<span data-ttu-id="382eb-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="382eb-128">win:UInt64</span></span>|<span data-ttu-id="382eb-129">Der Bezeichner für die Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="382eb-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="382eb-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="382eb-130">StubFlags</span></span>|<span data-ttu-id="382eb-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="382eb-131">win:UInt64</span></span>|<span data-ttu-id="382eb-132">Die Flags für den Stub:</span><span class="sxs-lookup"><span data-stu-id="382eb-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="382eb-133">0x1 – Reverse-Interop.</span><span class="sxs-lookup"><span data-stu-id="382eb-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="382eb-134">0x2 – COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="382eb-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="382eb-135">0x4 – Von „NGen.exe“ generierter Stub.</span><span class="sxs-lookup"><span data-stu-id="382eb-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="382eb-136">0x8 – Delegat.</span><span class="sxs-lookup"><span data-stu-id="382eb-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="382eb-137">0x10 – Variables Argument.</span><span class="sxs-lookup"><span data-stu-id="382eb-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="382eb-138">0x20 – Nicht verwalteter Aufgerufener.</span><span class="sxs-lookup"><span data-stu-id="382eb-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="382eb-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="382eb-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="382eb-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="382eb-140">win:UInt32</span></span>|<span data-ttu-id="382eb-141">Das Token für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="382eb-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="382eb-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="382eb-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="382eb-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="382eb-143">win:UnicodeString</span></span>|<span data-ttu-id="382eb-144">Der Namespace für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="382eb-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="382eb-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="382eb-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="382eb-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="382eb-146">win:UnicodeString</span></span>|<span data-ttu-id="382eb-147">Der Name der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="382eb-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="382eb-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="382eb-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="382eb-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="382eb-149">win:UnicodeString</span></span>|<span data-ttu-id="382eb-150">Die Signatur der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="382eb-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="382eb-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="382eb-151">NativeMethodSignature</span></span>|<span data-ttu-id="382eb-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="382eb-152">win:UnicodeString</span></span>|<span data-ttu-id="382eb-153">Die systemeigene Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="382eb-153">The native method signature.</span></span>|  
|<span data-ttu-id="382eb-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="382eb-154">StubMethodSignature</span></span>|<span data-ttu-id="382eb-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="382eb-155">win:UnicodeString</span></span>|<span data-ttu-id="382eb-156">Die Signatur der Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="382eb-156">The stub method signature.</span></span>|  
|<span data-ttu-id="382eb-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="382eb-157">StubMethodILCode</span></span>|<span data-ttu-id="382eb-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="382eb-158">win:UnicodeString</span></span>|<span data-ttu-id="382eb-159">Der MSIL-Code für die Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="382eb-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="382eb-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="382eb-160">ClrInstanceID</span></span>|<span data-ttu-id="382eb-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="382eb-161">win:UInt16</span></span>|<span data-ttu-id="382eb-162">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="382eb-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="382eb-163">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="382eb-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="382eb-164">ILStubCacheHit-Ereignis</span><span class="sxs-lookup"><span data-stu-id="382eb-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="382eb-165">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="382eb-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="382eb-166">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="382eb-166">Keyword for raising the event</span></span>|<span data-ttu-id="382eb-167">Ebene</span><span class="sxs-lookup"><span data-stu-id="382eb-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="382eb-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="382eb-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="382eb-169">Information (4)</span><span class="sxs-lookup"><span data-stu-id="382eb-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="382eb-170">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="382eb-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="382eb-171">Ereignis</span><span class="sxs-lookup"><span data-stu-id="382eb-171">Event</span></span>|<span data-ttu-id="382eb-172">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="382eb-172">Event ID</span></span>|<span data-ttu-id="382eb-173">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="382eb-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="382eb-174">89</span><span class="sxs-lookup"><span data-stu-id="382eb-174">89</span></span>|<span data-ttu-id="382eb-175">Es wurde auf den MSIL-Cache zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="382eb-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="382eb-176">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="382eb-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="382eb-177">Feldname</span><span class="sxs-lookup"><span data-stu-id="382eb-177">Field name</span></span>|<span data-ttu-id="382eb-178">Datentyp</span><span class="sxs-lookup"><span data-stu-id="382eb-178">Data type</span></span>|<span data-ttu-id="382eb-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="382eb-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="382eb-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="382eb-180">ModuleID</span></span>|<span data-ttu-id="382eb-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="382eb-181">win:UInt16</span></span>|<span data-ttu-id="382eb-182">Der Modulbezeichner.</span><span class="sxs-lookup"><span data-stu-id="382eb-182">The module identifier.</span></span>|  
|<span data-ttu-id="382eb-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="382eb-183">StubMethodID</span></span>|<span data-ttu-id="382eb-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="382eb-184">win:UInt64</span></span>|<span data-ttu-id="382eb-185">Der Bezeichner für die Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="382eb-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="382eb-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="382eb-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="382eb-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="382eb-187">win:UInt32</span></span>|<span data-ttu-id="382eb-188">Das Token für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="382eb-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="382eb-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="382eb-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="382eb-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="382eb-190">win:UnicodeString</span></span>|<span data-ttu-id="382eb-191">Der Namespace für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="382eb-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="382eb-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="382eb-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="382eb-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="382eb-193">win:UnicodeString</span></span>|<span data-ttu-id="382eb-194">Der Name der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="382eb-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="382eb-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="382eb-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="382eb-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="382eb-196">win:UnicodeString</span></span>|<span data-ttu-id="382eb-197">Die Signatur der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="382eb-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="382eb-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="382eb-198">ClrInstanceID</span></span>|<span data-ttu-id="382eb-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="382eb-199">win:UInt16</span></span>|<span data-ttu-id="382eb-200">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="382eb-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="382eb-201">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="382eb-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="382eb-202">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="382eb-202">See Also</span></span>  
 [<span data-ttu-id="382eb-203">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="382eb-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
