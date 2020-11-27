---
title: ETW-Sicherheitsereignisse
description: Informieren Sie sich über Sicherheits-ETW-Ereignisse, die bei der Überprüfung starker Namen und bei der authenticodeüberprüfung in .net ausgelöst werden
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: 4402bf5690a53ce518077268a3e20a95aeb14e8a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272513"
---
# <a name="security-etw-events"></a><span data-ttu-id="57174-103">ETW-Sicherheitsereignisse</span><span class="sxs-lookup"><span data-stu-id="57174-103">Security ETW Events</span></span>

<span data-ttu-id="57174-104">Sicherheitsereignisse werden während der Überprüfung mit starkem Namen und bei der Authenticodeüberprüfung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="57174-104">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="57174-105">StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="57174-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  

 <span data-ttu-id="57174-106">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="57174-106">The following table shows the keyword and level.</span></span> <span data-ttu-id="57174-107">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="57174-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="57174-108">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="57174-108">Keyword for raising the event</span></span>|<span data-ttu-id="57174-109">Ebene</span><span class="sxs-lookup"><span data-stu-id="57174-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="57174-110">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="57174-110">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="57174-111">Information (4)</span><span class="sxs-lookup"><span data-stu-id="57174-111">Informational(4)</span></span>|  
  
 <span data-ttu-id="57174-112">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="57174-112">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="57174-113">Ereignis</span><span class="sxs-lookup"><span data-stu-id="57174-113">Event</span></span>|<span data-ttu-id="57174-114">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="57174-114">Event ID</span></span>|<span data-ttu-id="57174-115">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="57174-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="57174-116">181</span><span class="sxs-lookup"><span data-stu-id="57174-116">181</span></span>|<span data-ttu-id="57174-117">Beginn der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="57174-117">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="57174-118">182</span><span class="sxs-lookup"><span data-stu-id="57174-118">182</span></span>|<span data-ttu-id="57174-119">Ende der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="57174-119">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="57174-120">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="57174-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="57174-121">Feldname</span><span class="sxs-lookup"><span data-stu-id="57174-121">Field name</span></span>|<span data-ttu-id="57174-122">Datentyp</span><span class="sxs-lookup"><span data-stu-id="57174-122">Data type</span></span>|<span data-ttu-id="57174-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="57174-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="57174-124">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="57174-124">VerificationFlags</span></span>|<span data-ttu-id="57174-125">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="57174-125">win:UInt32</span></span>|<span data-ttu-id="57174-126">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="57174-126">The verification flags.</span></span>|  
|<span data-ttu-id="57174-127">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="57174-127">ErrorCode</span></span>|<span data-ttu-id="57174-128">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="57174-128">win:UInt32</span></span>|<span data-ttu-id="57174-129">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="57174-129">The HResult error code.</span></span>|  
|<span data-ttu-id="57174-130">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="57174-130">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="57174-131">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="57174-131">win:UnicodeString</span></span>|<span data-ttu-id="57174-132">Der vollqualifizierte Assemblyname.</span><span class="sxs-lookup"><span data-stu-id="57174-132">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="57174-133">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="57174-133">ClrInstanceID</span></span>|<span data-ttu-id="57174-134">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="57174-134">win:UInt16</span></span>|<span data-ttu-id="57174-135">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="57174-135">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="57174-136">AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="57174-136">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  

 <span data-ttu-id="57174-137">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="57174-137">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="57174-138">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="57174-138">Keyword for raising the event</span></span>|<span data-ttu-id="57174-139">Ebene</span><span class="sxs-lookup"><span data-stu-id="57174-139">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="57174-140">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="57174-140">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="57174-141">Information (4)</span><span class="sxs-lookup"><span data-stu-id="57174-141">Informational(4)</span></span>|  
  
 <span data-ttu-id="57174-142">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="57174-142">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="57174-143">Ereignis</span><span class="sxs-lookup"><span data-stu-id="57174-143">Event</span></span>|<span data-ttu-id="57174-144">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="57174-144">Event ID</span></span>|<span data-ttu-id="57174-145">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="57174-145">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="57174-146">183</span><span class="sxs-lookup"><span data-stu-id="57174-146">183</span></span>|<span data-ttu-id="57174-147">Beginn der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="57174-147">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="57174-148">184</span><span class="sxs-lookup"><span data-stu-id="57174-148">184</span></span>|<span data-ttu-id="57174-149">Ende der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="57174-149">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="57174-150">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="57174-150">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="57174-151">Feldname</span><span class="sxs-lookup"><span data-stu-id="57174-151">Field name</span></span>|<span data-ttu-id="57174-152">Datentyp</span><span class="sxs-lookup"><span data-stu-id="57174-152">Data type</span></span>|<span data-ttu-id="57174-153">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="57174-153">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="57174-154">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="57174-154">VerificationFlags</span></span>|<span data-ttu-id="57174-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="57174-155">win:UInt32</span></span>|<span data-ttu-id="57174-156">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="57174-156">The verification flags.</span></span>|  
|<span data-ttu-id="57174-157">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="57174-157">ErrorCode</span></span>|<span data-ttu-id="57174-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="57174-158">win:UInt32</span></span>|<span data-ttu-id="57174-159">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="57174-159">The HResult error code.</span></span>|  
|<span data-ttu-id="57174-160">ModulePath</span><span class="sxs-lookup"><span data-stu-id="57174-160">ModulePath</span></span>|<span data-ttu-id="57174-161">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="57174-161">win:UnicodeString</span></span>|<span data-ttu-id="57174-162">Der Modulpfad.</span><span class="sxs-lookup"><span data-stu-id="57174-162">The module path.</span></span>|  
|<span data-ttu-id="57174-163">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="57174-163">ClrInstanceID</span></span>|<span data-ttu-id="57174-164">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="57174-164">win:UInt16</span></span>|<span data-ttu-id="57174-165">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="57174-165">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57174-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57174-166">See also</span></span>

- [<span data-ttu-id="57174-167">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="57174-167">CLR ETW Events</span></span>](clr-etw-events.md)
