---
title: Interop-ETW-Ereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 38db390b8fad9cd36dacf33f9647b0272eddc4a0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616408"
---
# <a name="interop-etw-events"></a><span data-ttu-id="34eb7-102">Interop-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="34eb7-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="34eb7-103">Interop-Ereignisse erfassen Informationen zur MSIL-Stubgenerierung und -Zwischenspeicherung (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="34eb7-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="34eb7-104">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="34eb7-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="34eb7-105">ILStubGenerated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="34eb7-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
- [<span data-ttu-id="34eb7-106">ILStubCacheHit-Ereignis</span><span class="sxs-lookup"><span data-stu-id="34eb7-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="34eb7-107">ILStubGenerated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="34eb7-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="34eb7-108">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="34eb7-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="34eb7-109">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="34eb7-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="34eb7-110">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="34eb7-110">Keyword for raising the event</span></span>|<span data-ttu-id="34eb7-111">Ebene</span><span class="sxs-lookup"><span data-stu-id="34eb7-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="34eb7-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="34eb7-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="34eb7-113">Information (4)</span><span class="sxs-lookup"><span data-stu-id="34eb7-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="34eb7-114">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="34eb7-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="34eb7-115">event</span><span class="sxs-lookup"><span data-stu-id="34eb7-115">Event</span></span>|<span data-ttu-id="34eb7-116">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="34eb7-116">Event ID</span></span>|<span data-ttu-id="34eb7-117">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="34eb7-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="34eb7-118">88</span><span class="sxs-lookup"><span data-stu-id="34eb7-118">88</span></span>|<span data-ttu-id="34eb7-119">Der MSIL-Stub wurde generiert.</span><span class="sxs-lookup"><span data-stu-id="34eb7-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="34eb7-120">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="34eb7-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="34eb7-121">Feldname</span><span class="sxs-lookup"><span data-stu-id="34eb7-121">Field name</span></span>|<span data-ttu-id="34eb7-122">Datentyp</span><span class="sxs-lookup"><span data-stu-id="34eb7-122">Data type</span></span>|<span data-ttu-id="34eb7-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34eb7-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="34eb7-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="34eb7-124">ModuleID</span></span>|<span data-ttu-id="34eb7-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="34eb7-125">win:UInt16</span></span>|<span data-ttu-id="34eb7-126">Der Modulbezeichner.</span><span class="sxs-lookup"><span data-stu-id="34eb7-126">The module identifier.</span></span>|  
|<span data-ttu-id="34eb7-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="34eb7-127">StubMethodID</span></span>|<span data-ttu-id="34eb7-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="34eb7-128">win:UInt64</span></span>|<span data-ttu-id="34eb7-129">Der Bezeichner für die Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="34eb7-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="34eb7-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="34eb7-130">StubFlags</span></span>|<span data-ttu-id="34eb7-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="34eb7-131">win:UInt64</span></span>|<span data-ttu-id="34eb7-132">Die Flags für den Stub:</span><span class="sxs-lookup"><span data-stu-id="34eb7-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="34eb7-133">0x1 – Reverse-Interop.</span><span class="sxs-lookup"><span data-stu-id="34eb7-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="34eb7-134">0x2 – COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="34eb7-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="34eb7-135">0x4 – Von „NGen.exe“ generierter Stub.</span><span class="sxs-lookup"><span data-stu-id="34eb7-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="34eb7-136">0x8 – Delegat.</span><span class="sxs-lookup"><span data-stu-id="34eb7-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="34eb7-137">0x10 – Variables Argument.</span><span class="sxs-lookup"><span data-stu-id="34eb7-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="34eb7-138">0x20 – Nicht verwalteter Aufgerufener.</span><span class="sxs-lookup"><span data-stu-id="34eb7-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="34eb7-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="34eb7-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="34eb7-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="34eb7-140">win:UInt32</span></span>|<span data-ttu-id="34eb7-141">Das Token für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="34eb7-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="34eb7-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="34eb7-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="34eb7-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="34eb7-143">win:UnicodeString</span></span>|<span data-ttu-id="34eb7-144">Der Namespace für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="34eb7-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="34eb7-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="34eb7-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="34eb7-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="34eb7-146">win:UnicodeString</span></span>|<span data-ttu-id="34eb7-147">Der Name der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="34eb7-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="34eb7-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="34eb7-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="34eb7-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="34eb7-149">win:UnicodeString</span></span>|<span data-ttu-id="34eb7-150">Die Signatur der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="34eb7-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="34eb7-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="34eb7-151">NativeMethodSignature</span></span>|<span data-ttu-id="34eb7-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="34eb7-152">win:UnicodeString</span></span>|<span data-ttu-id="34eb7-153">Die systemeigene Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="34eb7-153">The native method signature.</span></span>|  
|<span data-ttu-id="34eb7-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="34eb7-154">StubMethodSignature</span></span>|<span data-ttu-id="34eb7-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="34eb7-155">win:UnicodeString</span></span>|<span data-ttu-id="34eb7-156">Die Signatur der Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="34eb7-156">The stub method signature.</span></span>|  
|<span data-ttu-id="34eb7-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="34eb7-157">StubMethodILCode</span></span>|<span data-ttu-id="34eb7-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="34eb7-158">win:UnicodeString</span></span>|<span data-ttu-id="34eb7-159">Der MSIL-Code für die Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="34eb7-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="34eb7-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="34eb7-160">ClrInstanceID</span></span>|<span data-ttu-id="34eb7-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="34eb7-161">win:UInt16</span></span>|<span data-ttu-id="34eb7-162">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="34eb7-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="34eb7-163">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="34eb7-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="34eb7-164">ILStubCacheHit-Ereignis</span><span class="sxs-lookup"><span data-stu-id="34eb7-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="34eb7-165">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="34eb7-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="34eb7-166">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="34eb7-166">Keyword for raising the event</span></span>|<span data-ttu-id="34eb7-167">Ebene</span><span class="sxs-lookup"><span data-stu-id="34eb7-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="34eb7-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="34eb7-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="34eb7-169">Information (4)</span><span class="sxs-lookup"><span data-stu-id="34eb7-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="34eb7-170">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="34eb7-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="34eb7-171">event</span><span class="sxs-lookup"><span data-stu-id="34eb7-171">Event</span></span>|<span data-ttu-id="34eb7-172">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="34eb7-172">Event ID</span></span>|<span data-ttu-id="34eb7-173">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="34eb7-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="34eb7-174">89</span><span class="sxs-lookup"><span data-stu-id="34eb7-174">89</span></span>|<span data-ttu-id="34eb7-175">Es wurde auf den MSIL-Cache zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="34eb7-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="34eb7-176">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="34eb7-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="34eb7-177">Feldname</span><span class="sxs-lookup"><span data-stu-id="34eb7-177">Field name</span></span>|<span data-ttu-id="34eb7-178">Datentyp</span><span class="sxs-lookup"><span data-stu-id="34eb7-178">Data type</span></span>|<span data-ttu-id="34eb7-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34eb7-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="34eb7-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="34eb7-180">ModuleID</span></span>|<span data-ttu-id="34eb7-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="34eb7-181">win:UInt16</span></span>|<span data-ttu-id="34eb7-182">Der Modulbezeichner.</span><span class="sxs-lookup"><span data-stu-id="34eb7-182">The module identifier.</span></span>|  
|<span data-ttu-id="34eb7-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="34eb7-183">StubMethodID</span></span>|<span data-ttu-id="34eb7-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="34eb7-184">win:UInt64</span></span>|<span data-ttu-id="34eb7-185">Der Bezeichner für die Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="34eb7-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="34eb7-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="34eb7-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="34eb7-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="34eb7-187">win:UInt32</span></span>|<span data-ttu-id="34eb7-188">Das Token für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="34eb7-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="34eb7-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="34eb7-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="34eb7-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="34eb7-190">win:UnicodeString</span></span>|<span data-ttu-id="34eb7-191">Der Namespace für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="34eb7-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="34eb7-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="34eb7-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="34eb7-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="34eb7-193">win:UnicodeString</span></span>|<span data-ttu-id="34eb7-194">Der Name der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="34eb7-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="34eb7-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="34eb7-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="34eb7-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="34eb7-196">win:UnicodeString</span></span>|<span data-ttu-id="34eb7-197">Die Signatur der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="34eb7-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="34eb7-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="34eb7-198">ClrInstanceID</span></span>|<span data-ttu-id="34eb7-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="34eb7-199">win:UInt16</span></span>|<span data-ttu-id="34eb7-200">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="34eb7-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="34eb7-201">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="34eb7-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="34eb7-202">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34eb7-202">See also</span></span>

- [<span data-ttu-id="34eb7-203">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="34eb7-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
