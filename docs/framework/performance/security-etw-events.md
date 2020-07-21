---
title: ETW-Sicherheitsereignisse
description: Informieren Sie sich über Sicherheits-ETW-Ereignisse, die bei der Überprüfung starker Namen und bei der authenticodeüberprüfung in .net ausgelöst werden
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: 2fd2d450223cd16a7791b8f6c67afe6bcb954eb3
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474214"
---
# <a name="security-etw-events"></a><span data-ttu-id="30a55-103">ETW-Sicherheitsereignisse</span><span class="sxs-lookup"><span data-stu-id="30a55-103">Security ETW Events</span></span>

<span data-ttu-id="30a55-104">Sicherheitsereignisse werden während der Überprüfung mit starkem Namen und bei der Authenticodeüberprüfung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="30a55-104">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="30a55-105">StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="30a55-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="30a55-106">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="30a55-106">The following table shows the keyword and level.</span></span> <span data-ttu-id="30a55-107">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="30a55-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="30a55-108">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="30a55-108">Keyword for raising the event</span></span>|<span data-ttu-id="30a55-109">Ebene</span><span class="sxs-lookup"><span data-stu-id="30a55-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="30a55-110">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="30a55-110">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="30a55-111">Information (4)</span><span class="sxs-lookup"><span data-stu-id="30a55-111">Informational(4)</span></span>|  
  
 <span data-ttu-id="30a55-112">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="30a55-112">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="30a55-113">Ereignis</span><span class="sxs-lookup"><span data-stu-id="30a55-113">Event</span></span>|<span data-ttu-id="30a55-114">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="30a55-114">Event ID</span></span>|<span data-ttu-id="30a55-115">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="30a55-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="30a55-116">181</span><span class="sxs-lookup"><span data-stu-id="30a55-116">181</span></span>|<span data-ttu-id="30a55-117">Beginn der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="30a55-117">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="30a55-118">182</span><span class="sxs-lookup"><span data-stu-id="30a55-118">182</span></span>|<span data-ttu-id="30a55-119">Ende der Überprüfung mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="30a55-119">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="30a55-120">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="30a55-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="30a55-121">Feldname</span><span class="sxs-lookup"><span data-stu-id="30a55-121">Field name</span></span>|<span data-ttu-id="30a55-122">Datentyp</span><span class="sxs-lookup"><span data-stu-id="30a55-122">Data type</span></span>|<span data-ttu-id="30a55-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="30a55-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="30a55-124">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="30a55-124">VerificationFlags</span></span>|<span data-ttu-id="30a55-125">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30a55-125">win:UInt32</span></span>|<span data-ttu-id="30a55-126">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="30a55-126">The verification flags.</span></span>|  
|<span data-ttu-id="30a55-127">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="30a55-127">ErrorCode</span></span>|<span data-ttu-id="30a55-128">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30a55-128">win:UInt32</span></span>|<span data-ttu-id="30a55-129">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="30a55-129">The HResult error code.</span></span>|  
|<span data-ttu-id="30a55-130">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="30a55-130">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="30a55-131">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="30a55-131">win:UnicodeString</span></span>|<span data-ttu-id="30a55-132">Der vollqualifizierte Assemblyname.</span><span class="sxs-lookup"><span data-stu-id="30a55-132">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="30a55-133">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30a55-133">ClrInstanceID</span></span>|<span data-ttu-id="30a55-134">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30a55-134">win:UInt16</span></span>|<span data-ttu-id="30a55-135">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="30a55-135">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="30a55-136">AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="30a55-136">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="30a55-137">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="30a55-137">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="30a55-138">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="30a55-138">Keyword for raising the event</span></span>|<span data-ttu-id="30a55-139">Ebene</span><span class="sxs-lookup"><span data-stu-id="30a55-139">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="30a55-140">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="30a55-140">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="30a55-141">Information (4)</span><span class="sxs-lookup"><span data-stu-id="30a55-141">Informational(4)</span></span>|  
  
 <span data-ttu-id="30a55-142">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="30a55-142">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="30a55-143">Ereignis</span><span class="sxs-lookup"><span data-stu-id="30a55-143">Event</span></span>|<span data-ttu-id="30a55-144">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="30a55-144">Event ID</span></span>|<span data-ttu-id="30a55-145">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="30a55-145">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="30a55-146">183</span><span class="sxs-lookup"><span data-stu-id="30a55-146">183</span></span>|<span data-ttu-id="30a55-147">Beginn der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="30a55-147">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="30a55-148">184</span><span class="sxs-lookup"><span data-stu-id="30a55-148">184</span></span>|<span data-ttu-id="30a55-149">Ende der Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="30a55-149">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="30a55-150">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="30a55-150">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="30a55-151">Feldname</span><span class="sxs-lookup"><span data-stu-id="30a55-151">Field name</span></span>|<span data-ttu-id="30a55-152">Datentyp</span><span class="sxs-lookup"><span data-stu-id="30a55-152">Data type</span></span>|<span data-ttu-id="30a55-153">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="30a55-153">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="30a55-154">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="30a55-154">VerificationFlags</span></span>|<span data-ttu-id="30a55-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30a55-155">win:UInt32</span></span>|<span data-ttu-id="30a55-156">Die Überprüfungsflags.</span><span class="sxs-lookup"><span data-stu-id="30a55-156">The verification flags.</span></span>|  
|<span data-ttu-id="30a55-157">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="30a55-157">ErrorCode</span></span>|<span data-ttu-id="30a55-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30a55-158">win:UInt32</span></span>|<span data-ttu-id="30a55-159">Der HResult-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="30a55-159">The HResult error code.</span></span>|  
|<span data-ttu-id="30a55-160">ModulePath</span><span class="sxs-lookup"><span data-stu-id="30a55-160">ModulePath</span></span>|<span data-ttu-id="30a55-161">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="30a55-161">win:UnicodeString</span></span>|<span data-ttu-id="30a55-162">Der Modulpfad.</span><span class="sxs-lookup"><span data-stu-id="30a55-162">The module path.</span></span>|  
|<span data-ttu-id="30a55-163">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30a55-163">ClrInstanceID</span></span>|<span data-ttu-id="30a55-164">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30a55-164">win:UInt16</span></span>|<span data-ttu-id="30a55-165">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="30a55-165">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30a55-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30a55-166">See also</span></span>

- [<span data-ttu-id="30a55-167">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="30a55-167">CLR ETW Events</span></span>](clr-etw-events.md)
