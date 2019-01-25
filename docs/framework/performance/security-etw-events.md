---
title: ETW-Sicherheitsereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5cd5e660778b852cfee84359bb4d7253ca8f118d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608075"
---
# <a name="security-etw-events"></a><span data-ttu-id="a2ee3-102">ETW-Sicherheitsereignisse</span><span class="sxs-lookup"><span data-stu-id="a2ee3-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="a2ee3-103">Sicherheitsereignisse werden während der Überprüfung mit starkem Namen und bei der Authenticodeüberprüfung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="a2ee3-104">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="a2ee3-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="a2ee3-105">StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a2ee3-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="a2ee3-106">AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a2ee3-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="a2ee3-107">StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a2ee3-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="a2ee3-108">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="a2ee3-109">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="a2ee3-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a2ee3-110">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a2ee3-110">Keyword for raising the event</span></span>|<span data-ttu-id="a2ee3-111">Ebene</span><span class="sxs-lookup"><span data-stu-id="a2ee3-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a2ee3-112">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="a2ee3-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="a2ee3-113">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a2ee3-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="a2ee3-114">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a2ee3-115">Ereignis</span><span class="sxs-lookup"><span data-stu-id="a2ee3-115">Event</span></span>|<span data-ttu-id="a2ee3-116">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a2ee3-116">Event ID</span></span>|<span data-ttu-id="a2ee3-117">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a2ee3-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="a2ee3-118">181</span><span class="sxs-lookup"><span data-stu-id="a2ee3-118">181</span></span>|<span data-ttu-id="a2ee3-119">Beginn der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="a2ee3-120">182</span><span class="sxs-lookup"><span data-stu-id="a2ee3-120">182</span></span>|<span data-ttu-id="a2ee3-121">Ende der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="a2ee3-122">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a2ee3-123">Feldname</span><span class="sxs-lookup"><span data-stu-id="a2ee3-123">Field name</span></span>|<span data-ttu-id="a2ee3-124">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a2ee3-124">Data type</span></span>|<span data-ttu-id="a2ee3-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2ee3-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a2ee3-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="a2ee3-126">VerificationFlags</span></span>|<span data-ttu-id="a2ee3-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a2ee3-127">win:UInt32</span></span>|<span data-ttu-id="a2ee3-128">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-128">The verification flags.</span></span>|  
|<span data-ttu-id="a2ee3-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="a2ee3-129">ErrorCode</span></span>|<span data-ttu-id="a2ee3-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a2ee3-130">win:UInt32</span></span>|<span data-ttu-id="a2ee3-131">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-131">The HResult error code.</span></span>|  
|<span data-ttu-id="a2ee3-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="a2ee3-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="a2ee3-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a2ee3-133">win:UnicodeString</span></span>|<span data-ttu-id="a2ee3-134">Der vollqualifizierte Assemblyname.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="a2ee3-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a2ee3-135">ClrInstanceID</span></span>|<span data-ttu-id="a2ee3-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a2ee3-136">win:UInt16</span></span>|<span data-ttu-id="a2ee3-137">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a2ee3-138">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a2ee3-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="a2ee3-139">AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a2ee3-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="a2ee3-140">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a2ee3-141">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a2ee3-141">Keyword for raising the event</span></span>|<span data-ttu-id="a2ee3-142">Ebene</span><span class="sxs-lookup"><span data-stu-id="a2ee3-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a2ee3-143">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="a2ee3-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="a2ee3-144">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a2ee3-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="a2ee3-145">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a2ee3-146">Ereignis</span><span class="sxs-lookup"><span data-stu-id="a2ee3-146">Event</span></span>|<span data-ttu-id="a2ee3-147">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a2ee3-147">Event ID</span></span>|<span data-ttu-id="a2ee3-148">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a2ee3-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="a2ee3-149">183</span><span class="sxs-lookup"><span data-stu-id="a2ee3-149">183</span></span>|<span data-ttu-id="a2ee3-150">Beginn der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="a2ee3-151">184</span><span class="sxs-lookup"><span data-stu-id="a2ee3-151">184</span></span>|<span data-ttu-id="a2ee3-152">Ende der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="a2ee3-153">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a2ee3-154">Feldname</span><span class="sxs-lookup"><span data-stu-id="a2ee3-154">Field name</span></span>|<span data-ttu-id="a2ee3-155">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a2ee3-155">Data type</span></span>|<span data-ttu-id="a2ee3-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2ee3-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a2ee3-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="a2ee3-157">VerificationFlags</span></span>|<span data-ttu-id="a2ee3-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a2ee3-158">win:UInt32</span></span>|<span data-ttu-id="a2ee3-159">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-159">The verification flags.</span></span>|  
|<span data-ttu-id="a2ee3-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="a2ee3-160">ErrorCode</span></span>|<span data-ttu-id="a2ee3-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a2ee3-161">win:UInt32</span></span>|<span data-ttu-id="a2ee3-162">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-162">The HResult error code.</span></span>|  
|<span data-ttu-id="a2ee3-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="a2ee3-163">ModulePath</span></span>|<span data-ttu-id="a2ee3-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a2ee3-164">win:UnicodeString</span></span>|<span data-ttu-id="a2ee3-165">Der Modulpfad.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-165">The module path.</span></span>|  
|<span data-ttu-id="a2ee3-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a2ee3-166">ClrInstanceID</span></span>|<span data-ttu-id="a2ee3-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a2ee3-167">win:UInt16</span></span>|<span data-ttu-id="a2ee3-168">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a2ee3-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2ee3-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2ee3-169">See also</span></span>
- [<span data-ttu-id="a2ee3-170">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a2ee3-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
