---
title: ETW-Sicherheitsereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a19dce496423883e5fed62375c6db8ed5efdb1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949200"
---
# <a name="security-etw-events"></a><span data-ttu-id="0bc63-102">ETW-Sicherheitsereignisse</span><span class="sxs-lookup"><span data-stu-id="0bc63-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="0bc63-103">Sicherheitsereignisse werden während der Überprüfung mit starkem Namen und bei der Authenticodeüberprüfung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0bc63-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="0bc63-104">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="0bc63-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="0bc63-105">StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="0bc63-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [<span data-ttu-id="0bc63-106">AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="0bc63-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="0bc63-107">StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="0bc63-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="0bc63-108">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="0bc63-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="0bc63-109">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="0bc63-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="0bc63-110">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="0bc63-110">Keyword for raising the event</span></span>|<span data-ttu-id="0bc63-111">Ebene</span><span class="sxs-lookup"><span data-stu-id="0bc63-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="0bc63-112">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="0bc63-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="0bc63-113">Information (4)</span><span class="sxs-lookup"><span data-stu-id="0bc63-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="0bc63-114">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="0bc63-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0bc63-115">event</span><span class="sxs-lookup"><span data-stu-id="0bc63-115">Event</span></span>|<span data-ttu-id="0bc63-116">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0bc63-116">Event ID</span></span>|<span data-ttu-id="0bc63-117">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="0bc63-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="0bc63-118">181</span><span class="sxs-lookup"><span data-stu-id="0bc63-118">181</span></span>|<span data-ttu-id="0bc63-119">Beginn der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="0bc63-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="0bc63-120">182</span><span class="sxs-lookup"><span data-stu-id="0bc63-120">182</span></span>|<span data-ttu-id="0bc63-121">Ende der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="0bc63-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="0bc63-122">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="0bc63-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0bc63-123">Feldname</span><span class="sxs-lookup"><span data-stu-id="0bc63-123">Field name</span></span>|<span data-ttu-id="0bc63-124">Datentyp</span><span class="sxs-lookup"><span data-stu-id="0bc63-124">Data type</span></span>|<span data-ttu-id="0bc63-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bc63-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0bc63-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="0bc63-126">VerificationFlags</span></span>|<span data-ttu-id="0bc63-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0bc63-127">win:UInt32</span></span>|<span data-ttu-id="0bc63-128">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="0bc63-128">The verification flags.</span></span>|  
|<span data-ttu-id="0bc63-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="0bc63-129">ErrorCode</span></span>|<span data-ttu-id="0bc63-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0bc63-130">win:UInt32</span></span>|<span data-ttu-id="0bc63-131">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0bc63-131">The HResult error code.</span></span>|  
|<span data-ttu-id="0bc63-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="0bc63-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="0bc63-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="0bc63-133">win:UnicodeString</span></span>|<span data-ttu-id="0bc63-134">Der vollqualifizierte Assemblyname.</span><span class="sxs-lookup"><span data-stu-id="0bc63-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="0bc63-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0bc63-135">ClrInstanceID</span></span>|<span data-ttu-id="0bc63-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0bc63-136">win:UInt16</span></span>|<span data-ttu-id="0bc63-137">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="0bc63-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="0bc63-138">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="0bc63-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="0bc63-139">AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="0bc63-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="0bc63-140">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="0bc63-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0bc63-141">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="0bc63-141">Keyword for raising the event</span></span>|<span data-ttu-id="0bc63-142">Ebene</span><span class="sxs-lookup"><span data-stu-id="0bc63-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="0bc63-143">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="0bc63-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="0bc63-144">Information (4)</span><span class="sxs-lookup"><span data-stu-id="0bc63-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="0bc63-145">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="0bc63-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0bc63-146">event</span><span class="sxs-lookup"><span data-stu-id="0bc63-146">Event</span></span>|<span data-ttu-id="0bc63-147">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0bc63-147">Event ID</span></span>|<span data-ttu-id="0bc63-148">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="0bc63-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="0bc63-149">183</span><span class="sxs-lookup"><span data-stu-id="0bc63-149">183</span></span>|<span data-ttu-id="0bc63-150">Beginn der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="0bc63-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="0bc63-151">184</span><span class="sxs-lookup"><span data-stu-id="0bc63-151">184</span></span>|<span data-ttu-id="0bc63-152">Ende der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="0bc63-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="0bc63-153">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="0bc63-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0bc63-154">Feldname</span><span class="sxs-lookup"><span data-stu-id="0bc63-154">Field name</span></span>|<span data-ttu-id="0bc63-155">Datentyp</span><span class="sxs-lookup"><span data-stu-id="0bc63-155">Data type</span></span>|<span data-ttu-id="0bc63-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bc63-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0bc63-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="0bc63-157">VerificationFlags</span></span>|<span data-ttu-id="0bc63-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0bc63-158">win:UInt32</span></span>|<span data-ttu-id="0bc63-159">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="0bc63-159">The verification flags.</span></span>|  
|<span data-ttu-id="0bc63-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="0bc63-160">ErrorCode</span></span>|<span data-ttu-id="0bc63-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0bc63-161">win:UInt32</span></span>|<span data-ttu-id="0bc63-162">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0bc63-162">The HResult error code.</span></span>|  
|<span data-ttu-id="0bc63-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="0bc63-163">ModulePath</span></span>|<span data-ttu-id="0bc63-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="0bc63-164">win:UnicodeString</span></span>|<span data-ttu-id="0bc63-165">Der Modulpfad.</span><span class="sxs-lookup"><span data-stu-id="0bc63-165">The module path.</span></span>|  
|<span data-ttu-id="0bc63-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0bc63-166">ClrInstanceID</span></span>|<span data-ttu-id="0bc63-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0bc63-167">win:UInt16</span></span>|<span data-ttu-id="0bc63-168">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="0bc63-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0bc63-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bc63-169">See also</span></span>

- [<span data-ttu-id="0bc63-170">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="0bc63-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
