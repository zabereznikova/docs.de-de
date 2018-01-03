---
title: ETW-Sicherheitsereignisse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: abf6e6896267b6d1c8449b020230381923f38f1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="security-etw-events"></a><span data-ttu-id="46e7b-102">ETW-Sicherheitsereignisse</span><span class="sxs-lookup"><span data-stu-id="46e7b-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="46e7b-103">Sicherheitsereignisse werden während der Überprüfung mit starkem Namen und bei der Authenticodeüberprüfung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="46e7b-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="46e7b-104">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="46e7b-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="46e7b-105">StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="46e7b-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="46e7b-106">AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="46e7b-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="46e7b-107">StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="46e7b-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="46e7b-108">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="46e7b-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="46e7b-109">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="46e7b-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="46e7b-110">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="46e7b-110">Keyword for raising the event</span></span>|<span data-ttu-id="46e7b-111">Ebene</span><span class="sxs-lookup"><span data-stu-id="46e7b-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="46e7b-112">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="46e7b-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="46e7b-113">Information (4)</span><span class="sxs-lookup"><span data-stu-id="46e7b-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="46e7b-114">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="46e7b-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="46e7b-115">Ereignis</span><span class="sxs-lookup"><span data-stu-id="46e7b-115">Event</span></span>|<span data-ttu-id="46e7b-116">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="46e7b-116">Event ID</span></span>|<span data-ttu-id="46e7b-117">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="46e7b-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="46e7b-118">181</span><span class="sxs-lookup"><span data-stu-id="46e7b-118">181</span></span>|<span data-ttu-id="46e7b-119">Beginn der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="46e7b-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="46e7b-120">182</span><span class="sxs-lookup"><span data-stu-id="46e7b-120">182</span></span>|<span data-ttu-id="46e7b-121">Ende der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="46e7b-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="46e7b-122">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="46e7b-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="46e7b-123">Feldname</span><span class="sxs-lookup"><span data-stu-id="46e7b-123">Field name</span></span>|<span data-ttu-id="46e7b-124">Datentyp</span><span class="sxs-lookup"><span data-stu-id="46e7b-124">Data type</span></span>|<span data-ttu-id="46e7b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46e7b-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="46e7b-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="46e7b-126">VerificationFlags</span></span>|<span data-ttu-id="46e7b-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="46e7b-127">win:UInt32</span></span>|<span data-ttu-id="46e7b-128">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="46e7b-128">The verification flags.</span></span>|  
|<span data-ttu-id="46e7b-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="46e7b-129">ErrorCode</span></span>|<span data-ttu-id="46e7b-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="46e7b-130">win:UInt32</span></span>|<span data-ttu-id="46e7b-131">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="46e7b-131">The HResult error code.</span></span>|  
|<span data-ttu-id="46e7b-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="46e7b-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="46e7b-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="46e7b-133">win:UnicodeString</span></span>|<span data-ttu-id="46e7b-134">Der vollqualifizierte Assemblyname.</span><span class="sxs-lookup"><span data-stu-id="46e7b-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="46e7b-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="46e7b-135">ClrInstanceID</span></span>|<span data-ttu-id="46e7b-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="46e7b-136">win:UInt16</span></span>|<span data-ttu-id="46e7b-137">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="46e7b-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="46e7b-138">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="46e7b-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="46e7b-139">AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="46e7b-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="46e7b-140">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="46e7b-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="46e7b-141">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="46e7b-141">Keyword for raising the event</span></span>|<span data-ttu-id="46e7b-142">Ebene</span><span class="sxs-lookup"><span data-stu-id="46e7b-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="46e7b-143">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="46e7b-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="46e7b-144">Information (4)</span><span class="sxs-lookup"><span data-stu-id="46e7b-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="46e7b-145">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="46e7b-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="46e7b-146">Ereignis</span><span class="sxs-lookup"><span data-stu-id="46e7b-146">Event</span></span>|<span data-ttu-id="46e7b-147">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="46e7b-147">Event ID</span></span>|<span data-ttu-id="46e7b-148">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="46e7b-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="46e7b-149">183</span><span class="sxs-lookup"><span data-stu-id="46e7b-149">183</span></span>|<span data-ttu-id="46e7b-150">Beginn der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="46e7b-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="46e7b-151">184</span><span class="sxs-lookup"><span data-stu-id="46e7b-151">184</span></span>|<span data-ttu-id="46e7b-152">Ende der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="46e7b-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="46e7b-153">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="46e7b-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="46e7b-154">Feldname</span><span class="sxs-lookup"><span data-stu-id="46e7b-154">Field name</span></span>|<span data-ttu-id="46e7b-155">Datentyp</span><span class="sxs-lookup"><span data-stu-id="46e7b-155">Data type</span></span>|<span data-ttu-id="46e7b-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46e7b-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="46e7b-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="46e7b-157">VerificationFlags</span></span>|<span data-ttu-id="46e7b-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="46e7b-158">win:UInt32</span></span>|<span data-ttu-id="46e7b-159">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="46e7b-159">The verification flags.</span></span>|  
|<span data-ttu-id="46e7b-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="46e7b-160">ErrorCode</span></span>|<span data-ttu-id="46e7b-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="46e7b-161">win:UInt32</span></span>|<span data-ttu-id="46e7b-162">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="46e7b-162">The HResult error code.</span></span>|  
|<span data-ttu-id="46e7b-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="46e7b-163">ModulePath</span></span>|<span data-ttu-id="46e7b-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="46e7b-164">win:UnicodeString</span></span>|<span data-ttu-id="46e7b-165">Der Modulpfad.</span><span class="sxs-lookup"><span data-stu-id="46e7b-165">The module path.</span></span>|  
|<span data-ttu-id="46e7b-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="46e7b-166">ClrInstanceID</span></span>|<span data-ttu-id="46e7b-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="46e7b-167">win:UInt16</span></span>|<span data-ttu-id="46e7b-168">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="46e7b-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46e7b-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46e7b-169">See Also</span></span>  
 [<span data-ttu-id="46e7b-170">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="46e7b-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
