---
title: ETW-Sicherheitsereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1dad042595608a805f978673858acaa5c01130f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974877"
---
# <a name="security-etw-events"></a><span data-ttu-id="9735d-102">ETW-Sicherheitsereignisse</span><span class="sxs-lookup"><span data-stu-id="9735d-102">Security ETW Events</span></span>

<span data-ttu-id="9735d-103">Sicherheitsereignisse werden während der Überprüfung mit starkem Namen und bei der Authenticodeüberprüfung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9735d-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="9735d-104">StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="9735d-104">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="9735d-105">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="9735d-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="9735d-106">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="9735d-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="9735d-107">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9735d-107">Keyword for raising the event</span></span>|<span data-ttu-id="9735d-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9735d-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="9735d-109">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="9735d-109">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="9735d-110">Information (4)</span><span class="sxs-lookup"><span data-stu-id="9735d-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="9735d-111">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="9735d-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="9735d-112">event</span><span class="sxs-lookup"><span data-stu-id="9735d-112">Event</span></span>|<span data-ttu-id="9735d-113">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="9735d-113">Event ID</span></span>|<span data-ttu-id="9735d-114">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="9735d-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="9735d-115">181</span><span class="sxs-lookup"><span data-stu-id="9735d-115">181</span></span>|<span data-ttu-id="9735d-116">Beginn der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="9735d-116">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="9735d-117">182</span><span class="sxs-lookup"><span data-stu-id="9735d-117">182</span></span>|<span data-ttu-id="9735d-118">Ende der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="9735d-118">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="9735d-119">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="9735d-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="9735d-120">Feldname</span><span class="sxs-lookup"><span data-stu-id="9735d-120">Field name</span></span>|<span data-ttu-id="9735d-121">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9735d-121">Data type</span></span>|<span data-ttu-id="9735d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9735d-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="9735d-123">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="9735d-123">VerificationFlags</span></span>|<span data-ttu-id="9735d-124">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="9735d-124">win:UInt32</span></span>|<span data-ttu-id="9735d-125">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="9735d-125">The verification flags.</span></span>|  
|<span data-ttu-id="9735d-126">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="9735d-126">ErrorCode</span></span>|<span data-ttu-id="9735d-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="9735d-127">win:UInt32</span></span>|<span data-ttu-id="9735d-128">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9735d-128">The HResult error code.</span></span>|  
|<span data-ttu-id="9735d-129">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="9735d-129">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="9735d-130">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9735d-130">win:UnicodeString</span></span>|<span data-ttu-id="9735d-131">Der vollqualifizierte Assemblyname.</span><span class="sxs-lookup"><span data-stu-id="9735d-131">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="9735d-132">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="9735d-132">ClrInstanceID</span></span>|<span data-ttu-id="9735d-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9735d-133">win:UInt16</span></span>|<span data-ttu-id="9735d-134">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="9735d-134">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="9735d-135">AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="9735d-135">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="9735d-136">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="9735d-136">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="9735d-137">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9735d-137">Keyword for raising the event</span></span>|<span data-ttu-id="9735d-138">Ebene</span><span class="sxs-lookup"><span data-stu-id="9735d-138">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="9735d-139">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="9735d-139">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="9735d-140">Information (4)</span><span class="sxs-lookup"><span data-stu-id="9735d-140">Informational(4)</span></span>|  
  
 <span data-ttu-id="9735d-141">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="9735d-141">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="9735d-142">event</span><span class="sxs-lookup"><span data-stu-id="9735d-142">Event</span></span>|<span data-ttu-id="9735d-143">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="9735d-143">Event ID</span></span>|<span data-ttu-id="9735d-144">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="9735d-144">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="9735d-145">183</span><span class="sxs-lookup"><span data-stu-id="9735d-145">183</span></span>|<span data-ttu-id="9735d-146">Beginn der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="9735d-146">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="9735d-147">184</span><span class="sxs-lookup"><span data-stu-id="9735d-147">184</span></span>|<span data-ttu-id="9735d-148">Ende der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="9735d-148">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="9735d-149">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="9735d-149">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="9735d-150">Feldname</span><span class="sxs-lookup"><span data-stu-id="9735d-150">Field name</span></span>|<span data-ttu-id="9735d-151">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9735d-151">Data type</span></span>|<span data-ttu-id="9735d-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9735d-152">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="9735d-153">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="9735d-153">VerificationFlags</span></span>|<span data-ttu-id="9735d-154">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="9735d-154">win:UInt32</span></span>|<span data-ttu-id="9735d-155">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="9735d-155">The verification flags.</span></span>|  
|<span data-ttu-id="9735d-156">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="9735d-156">ErrorCode</span></span>|<span data-ttu-id="9735d-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="9735d-157">win:UInt32</span></span>|<span data-ttu-id="9735d-158">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9735d-158">The HResult error code.</span></span>|  
|<span data-ttu-id="9735d-159">ModulePath</span><span class="sxs-lookup"><span data-stu-id="9735d-159">ModulePath</span></span>|<span data-ttu-id="9735d-160">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9735d-160">win:UnicodeString</span></span>|<span data-ttu-id="9735d-161">Der Modulpfad.</span><span class="sxs-lookup"><span data-stu-id="9735d-161">The module path.</span></span>|  
|<span data-ttu-id="9735d-162">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="9735d-162">ClrInstanceID</span></span>|<span data-ttu-id="9735d-163">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9735d-163">win:UInt16</span></span>|<span data-ttu-id="9735d-164">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="9735d-164">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9735d-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9735d-165">See also</span></span>

- [<span data-ttu-id="9735d-166">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="9735d-166">CLR ETW Events</span></span>](clr-etw-events.md)
