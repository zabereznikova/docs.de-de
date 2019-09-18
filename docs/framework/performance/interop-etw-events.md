---
title: Interop-ETW-Ereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 787c6221b651a53dbb932a5a9d0edea123e1d97d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046439"
---
# <a name="interop-etw-events"></a><span data-ttu-id="bc21a-102">Interop-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="bc21a-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="bc21a-103">Interop-Ereignisse erfassen Informationen zur MSIL-Stubgenerierung und -Zwischenspeicherung (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="bc21a-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="bc21a-104">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="bc21a-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="bc21a-105">ILStubGenerated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="bc21a-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
- [<span data-ttu-id="bc21a-106">ILStubCacheHit-Ereignis</span><span class="sxs-lookup"><span data-stu-id="bc21a-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="bc21a-107">ILStubGenerated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="bc21a-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="bc21a-108">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="bc21a-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="bc21a-109">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="bc21a-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="bc21a-110">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="bc21a-110">Keyword for raising the event</span></span>|<span data-ttu-id="bc21a-111">Ebene</span><span class="sxs-lookup"><span data-stu-id="bc21a-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="bc21a-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="bc21a-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="bc21a-113">Information (4)</span><span class="sxs-lookup"><span data-stu-id="bc21a-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="bc21a-114">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="bc21a-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="bc21a-115">event</span><span class="sxs-lookup"><span data-stu-id="bc21a-115">Event</span></span>|<span data-ttu-id="bc21a-116">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="bc21a-116">Event ID</span></span>|<span data-ttu-id="bc21a-117">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="bc21a-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="bc21a-118">88</span><span class="sxs-lookup"><span data-stu-id="bc21a-118">88</span></span>|<span data-ttu-id="bc21a-119">Der MSIL-Stub wurde generiert.</span><span class="sxs-lookup"><span data-stu-id="bc21a-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="bc21a-120">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="bc21a-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="bc21a-121">Feldname</span><span class="sxs-lookup"><span data-stu-id="bc21a-121">Field name</span></span>|<span data-ttu-id="bc21a-122">Datentyp</span><span class="sxs-lookup"><span data-stu-id="bc21a-122">Data type</span></span>|<span data-ttu-id="bc21a-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc21a-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="bc21a-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="bc21a-124">ModuleID</span></span>|<span data-ttu-id="bc21a-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="bc21a-125">win:UInt16</span></span>|<span data-ttu-id="bc21a-126">Der Modulbezeichner.</span><span class="sxs-lookup"><span data-stu-id="bc21a-126">The module identifier.</span></span>|  
|<span data-ttu-id="bc21a-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="bc21a-127">StubMethodID</span></span>|<span data-ttu-id="bc21a-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="bc21a-128">win:UInt64</span></span>|<span data-ttu-id="bc21a-129">Der Bezeichner für die Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="bc21a-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="bc21a-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="bc21a-130">StubFlags</span></span>|<span data-ttu-id="bc21a-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="bc21a-131">win:UInt64</span></span>|<span data-ttu-id="bc21a-132">Die Flags für den Stub:</span><span class="sxs-lookup"><span data-stu-id="bc21a-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="bc21a-133">0x1 – Reverse-Interop.</span><span class="sxs-lookup"><span data-stu-id="bc21a-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="bc21a-134">0x2 – COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="bc21a-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="bc21a-135">0x4 – Von „NGen.exe“ generierter Stub.</span><span class="sxs-lookup"><span data-stu-id="bc21a-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="bc21a-136">0x8 – Delegat.</span><span class="sxs-lookup"><span data-stu-id="bc21a-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="bc21a-137">0x10-Variablen Argument.</span><span class="sxs-lookup"><span data-stu-id="bc21a-137">0x10 - Variable argument.</span></span><br /><br /> <span data-ttu-id="bc21a-138">0x20 – Nicht verwalteter Aufgerufener.</span><span class="sxs-lookup"><span data-stu-id="bc21a-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="bc21a-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="bc21a-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="bc21a-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="bc21a-140">win:UInt32</span></span>|<span data-ttu-id="bc21a-141">Das Token für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="bc21a-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="bc21a-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="bc21a-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="bc21a-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="bc21a-143">win:UnicodeString</span></span>|<span data-ttu-id="bc21a-144">Der Namespace für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="bc21a-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="bc21a-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="bc21a-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="bc21a-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="bc21a-146">win:UnicodeString</span></span>|<span data-ttu-id="bc21a-147">Der Name der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="bc21a-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="bc21a-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="bc21a-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="bc21a-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="bc21a-149">win:UnicodeString</span></span>|<span data-ttu-id="bc21a-150">Die Signatur der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="bc21a-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="bc21a-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="bc21a-151">NativeMethodSignature</span></span>|<span data-ttu-id="bc21a-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="bc21a-152">win:UnicodeString</span></span>|<span data-ttu-id="bc21a-153">Die systemeigene Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="bc21a-153">The native method signature.</span></span>|  
|<span data-ttu-id="bc21a-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="bc21a-154">StubMethodSignature</span></span>|<span data-ttu-id="bc21a-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="bc21a-155">win:UnicodeString</span></span>|<span data-ttu-id="bc21a-156">Die Signatur der Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="bc21a-156">The stub method signature.</span></span>|  
|<span data-ttu-id="bc21a-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="bc21a-157">StubMethodILCode</span></span>|<span data-ttu-id="bc21a-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="bc21a-158">win:UnicodeString</span></span>|<span data-ttu-id="bc21a-159">Der MSIL-Code für die Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="bc21a-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="bc21a-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="bc21a-160">ClrInstanceID</span></span>|<span data-ttu-id="bc21a-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="bc21a-161">win:UInt16</span></span>|<span data-ttu-id="bc21a-162">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="bc21a-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="bc21a-163">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="bc21a-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="bc21a-164">ILStubCacheHit-Ereignis</span><span class="sxs-lookup"><span data-stu-id="bc21a-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="bc21a-165">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="bc21a-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="bc21a-166">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="bc21a-166">Keyword for raising the event</span></span>|<span data-ttu-id="bc21a-167">Ebene</span><span class="sxs-lookup"><span data-stu-id="bc21a-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="bc21a-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="bc21a-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="bc21a-169">Information (4)</span><span class="sxs-lookup"><span data-stu-id="bc21a-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="bc21a-170">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="bc21a-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="bc21a-171">event</span><span class="sxs-lookup"><span data-stu-id="bc21a-171">Event</span></span>|<span data-ttu-id="bc21a-172">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="bc21a-172">Event ID</span></span>|<span data-ttu-id="bc21a-173">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="bc21a-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="bc21a-174">89</span><span class="sxs-lookup"><span data-stu-id="bc21a-174">89</span></span>|<span data-ttu-id="bc21a-175">Es wurde auf den MSIL-Cache zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="bc21a-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="bc21a-176">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="bc21a-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="bc21a-177">Feldname</span><span class="sxs-lookup"><span data-stu-id="bc21a-177">Field name</span></span>|<span data-ttu-id="bc21a-178">Datentyp</span><span class="sxs-lookup"><span data-stu-id="bc21a-178">Data type</span></span>|<span data-ttu-id="bc21a-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc21a-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="bc21a-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="bc21a-180">ModuleID</span></span>|<span data-ttu-id="bc21a-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="bc21a-181">win:UInt16</span></span>|<span data-ttu-id="bc21a-182">Der Modulbezeichner.</span><span class="sxs-lookup"><span data-stu-id="bc21a-182">The module identifier.</span></span>|  
|<span data-ttu-id="bc21a-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="bc21a-183">StubMethodID</span></span>|<span data-ttu-id="bc21a-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="bc21a-184">win:UInt64</span></span>|<span data-ttu-id="bc21a-185">Der Bezeichner für die Stubmethode.</span><span class="sxs-lookup"><span data-stu-id="bc21a-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="bc21a-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="bc21a-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="bc21a-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="bc21a-187">win:UInt32</span></span>|<span data-ttu-id="bc21a-188">Das Token für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="bc21a-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="bc21a-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="bc21a-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="bc21a-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="bc21a-190">win:UnicodeString</span></span>|<span data-ttu-id="bc21a-191">Der Namespace für die verwaltete Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="bc21a-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="bc21a-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="bc21a-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="bc21a-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="bc21a-193">win:UnicodeString</span></span>|<span data-ttu-id="bc21a-194">Der Name der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="bc21a-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="bc21a-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="bc21a-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="bc21a-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="bc21a-196">win:UnicodeString</span></span>|<span data-ttu-id="bc21a-197">Die Signatur der verwalteten Interop-Methode.</span><span class="sxs-lookup"><span data-stu-id="bc21a-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="bc21a-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="bc21a-198">ClrInstanceID</span></span>|<span data-ttu-id="bc21a-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="bc21a-199">win:UInt16</span></span>|<span data-ttu-id="bc21a-200">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="bc21a-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="bc21a-201">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="bc21a-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="bc21a-202">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc21a-202">See also</span></span>

- [<span data-ttu-id="bc21a-203">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="bc21a-203">CLR ETW Events</span></span>](clr-etw-events.md)
