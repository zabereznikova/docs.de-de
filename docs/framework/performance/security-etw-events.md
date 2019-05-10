---
title: ETW-Sicherheitsereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f2ea19c88ff8b854b09ed372b35bf8c45d994585
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64583651"
---
# <a name="security-etw-events"></a><span data-ttu-id="8fd6c-102">ETW-Sicherheitsereignisse</span><span class="sxs-lookup"><span data-stu-id="8fd6c-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="8fd6c-103">Sicherheitsereignisse werden während der Überprüfung mit starkem Namen und bei der Authenticodeüberprüfung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="8fd6c-104">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="8fd6c-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="8fd6c-105">StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="8fd6c-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [<span data-ttu-id="8fd6c-106">AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="8fd6c-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="8fd6c-107">StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="8fd6c-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="8fd6c-108">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="8fd6c-109">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="8fd6c-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="8fd6c-110">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="8fd6c-110">Keyword for raising the event</span></span>|<span data-ttu-id="8fd6c-111">Ebene</span><span class="sxs-lookup"><span data-stu-id="8fd6c-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="8fd6c-112">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="8fd6c-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="8fd6c-113">Information (4)</span><span class="sxs-lookup"><span data-stu-id="8fd6c-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="8fd6c-114">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="8fd6c-115">event</span><span class="sxs-lookup"><span data-stu-id="8fd6c-115">Event</span></span>|<span data-ttu-id="8fd6c-116">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="8fd6c-116">Event ID</span></span>|<span data-ttu-id="8fd6c-117">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="8fd6c-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="8fd6c-118">181</span><span class="sxs-lookup"><span data-stu-id="8fd6c-118">181</span></span>|<span data-ttu-id="8fd6c-119">Beginn der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="8fd6c-120">182</span><span class="sxs-lookup"><span data-stu-id="8fd6c-120">182</span></span>|<span data-ttu-id="8fd6c-121">Ende der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="8fd6c-122">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="8fd6c-123">Feldname</span><span class="sxs-lookup"><span data-stu-id="8fd6c-123">Field name</span></span>|<span data-ttu-id="8fd6c-124">Datentyp</span><span class="sxs-lookup"><span data-stu-id="8fd6c-124">Data type</span></span>|<span data-ttu-id="8fd6c-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fd6c-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="8fd6c-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="8fd6c-126">VerificationFlags</span></span>|<span data-ttu-id="8fd6c-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8fd6c-127">win:UInt32</span></span>|<span data-ttu-id="8fd6c-128">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-128">The verification flags.</span></span>|  
|<span data-ttu-id="8fd6c-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="8fd6c-129">ErrorCode</span></span>|<span data-ttu-id="8fd6c-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8fd6c-130">win:UInt32</span></span>|<span data-ttu-id="8fd6c-131">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-131">The HResult error code.</span></span>|  
|<span data-ttu-id="8fd6c-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="8fd6c-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="8fd6c-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8fd6c-133">win:UnicodeString</span></span>|<span data-ttu-id="8fd6c-134">Der vollqualifizierte Assemblyname.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="8fd6c-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8fd6c-135">ClrInstanceID</span></span>|<span data-ttu-id="8fd6c-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8fd6c-136">win:UInt16</span></span>|<span data-ttu-id="8fd6c-137">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="8fd6c-138">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="8fd6c-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="8fd6c-139">AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="8fd6c-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="8fd6c-140">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="8fd6c-141">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="8fd6c-141">Keyword for raising the event</span></span>|<span data-ttu-id="8fd6c-142">Ebene</span><span class="sxs-lookup"><span data-stu-id="8fd6c-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="8fd6c-143">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="8fd6c-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="8fd6c-144">Information (4)</span><span class="sxs-lookup"><span data-stu-id="8fd6c-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="8fd6c-145">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="8fd6c-146">event</span><span class="sxs-lookup"><span data-stu-id="8fd6c-146">Event</span></span>|<span data-ttu-id="8fd6c-147">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="8fd6c-147">Event ID</span></span>|<span data-ttu-id="8fd6c-148">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="8fd6c-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="8fd6c-149">183</span><span class="sxs-lookup"><span data-stu-id="8fd6c-149">183</span></span>|<span data-ttu-id="8fd6c-150">Beginn der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="8fd6c-151">184</span><span class="sxs-lookup"><span data-stu-id="8fd6c-151">184</span></span>|<span data-ttu-id="8fd6c-152">Ende der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="8fd6c-153">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="8fd6c-154">Feldname</span><span class="sxs-lookup"><span data-stu-id="8fd6c-154">Field name</span></span>|<span data-ttu-id="8fd6c-155">Datentyp</span><span class="sxs-lookup"><span data-stu-id="8fd6c-155">Data type</span></span>|<span data-ttu-id="8fd6c-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fd6c-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="8fd6c-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="8fd6c-157">VerificationFlags</span></span>|<span data-ttu-id="8fd6c-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8fd6c-158">win:UInt32</span></span>|<span data-ttu-id="8fd6c-159">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-159">The verification flags.</span></span>|  
|<span data-ttu-id="8fd6c-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="8fd6c-160">ErrorCode</span></span>|<span data-ttu-id="8fd6c-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8fd6c-161">win:UInt32</span></span>|<span data-ttu-id="8fd6c-162">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-162">The HResult error code.</span></span>|  
|<span data-ttu-id="8fd6c-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="8fd6c-163">ModulePath</span></span>|<span data-ttu-id="8fd6c-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="8fd6c-164">win:UnicodeString</span></span>|<span data-ttu-id="8fd6c-165">Der Modulpfad.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-165">The module path.</span></span>|  
|<span data-ttu-id="8fd6c-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8fd6c-166">ClrInstanceID</span></span>|<span data-ttu-id="8fd6c-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8fd6c-167">win:UInt16</span></span>|<span data-ttu-id="8fd6c-168">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="8fd6c-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8fd6c-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fd6c-169">See also</span></span>

- [<span data-ttu-id="8fd6c-170">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="8fd6c-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
