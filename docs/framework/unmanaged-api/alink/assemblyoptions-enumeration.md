---
title: AssemblyOptions-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6ad4f9e02ed0d22009fcb8a5ac078231f2cb22e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="c80f8-102">AssemblyOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c80f8-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="c80f8-103">Listet die Assemblyoptionen.</span><span class="sxs-lookup"><span data-stu-id="c80f8-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c80f8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c80f8-104">Syntax</span></span>  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="c80f8-105">Felder</span><span class="sxs-lookup"><span data-stu-id="c80f8-105">Fields</span></span>  
  
|<span data-ttu-id="c80f8-106">Feld</span><span class="sxs-lookup"><span data-stu-id="c80f8-106">Field</span></span>|<span data-ttu-id="c80f8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c80f8-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c80f8-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="c80f8-108">optAssemTitle</span></span>|<span data-ttu-id="c80f8-109">Zeichenfolge – der Assemblytitel darstellt.</span><span class="sxs-lookup"><span data-stu-id="c80f8-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="c80f8-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="c80f8-110">optAssemDescription</span></span>|<span data-ttu-id="c80f8-111">Zeichenfolge – enthält die Beschreibung der Assembly.</span><span class="sxs-lookup"><span data-stu-id="c80f8-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="c80f8-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="c80f8-112">optAssemConfig</span></span>|<span data-ttu-id="c80f8-113">Zeichenfolge – enthält die Assemblykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="c80f8-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="c80f8-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="c80f8-114">optAssemOS</span></span>|<span data-ttu-id="c80f8-115">-Codierte Zeichenfolge: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="c80f8-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="c80f8-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="c80f8-116">optAssemProcessor</span></span>|<span data-ttu-id="c80f8-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="c80f8-117">ULONG</span></span>|  
|<span data-ttu-id="c80f8-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="c80f8-118">optAssemLocale</span></span>|<span data-ttu-id="c80f8-119">Zeichenfolge – das Gebietsschema der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="c80f8-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="c80f8-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="c80f8-120">optAssemVersion</span></span>|<span data-ttu-id="c80f8-121">-Codierte Zeichenfolge: "Major.Minor.Build.Revision".</span><span class="sxs-lookup"><span data-stu-id="c80f8-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="c80f8-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="c80f8-122">optAssemCompany</span></span>|<span data-ttu-id="c80f8-123">Zeichenfolge – enthält das Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="c80f8-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="c80f8-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="c80f8-124">optAssemProduct</span></span>|<span data-ttu-id="c80f8-125">Zeichenfolge – der Name des Produkts enthält.</span><span class="sxs-lookup"><span data-stu-id="c80f8-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="c80f8-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="c80f8-126">optAssemProductVersion</span></span>|<span data-ttu-id="c80f8-127">Zeichenfolge (auch bekannt als InformationalVersion bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="c80f8-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="c80f8-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="c80f8-128">optAssemCopyright</span></span>|<span data-ttu-id="c80f8-129">Zeichenfolge – enthält die copyright-Informationen.</span><span class="sxs-lookup"><span data-stu-id="c80f8-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="c80f8-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="c80f8-130">optAssemTrademark</span></span>|<span data-ttu-id="c80f8-131">Zeichenfolge – enthält die Markeninformationen.</span><span class="sxs-lookup"><span data-stu-id="c80f8-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="c80f8-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="c80f8-132">optAssemKeyFile</span></span>|<span data-ttu-id="c80f8-133">Zeichenfolge (Dateiname).</span><span class="sxs-lookup"><span data-stu-id="c80f8-133">String (file name).</span></span>|  
|<span data-ttu-id="c80f8-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="c80f8-134">optAssemKeyName</span></span>|<span data-ttu-id="c80f8-135">Zeichenfolge (Schlüsselname).</span><span class="sxs-lookup"><span data-stu-id="c80f8-135">String (The key name).</span></span>|  
|<span data-ttu-id="c80f8-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="c80f8-136">optAssemAlgID</span></span>|<span data-ttu-id="c80f8-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="c80f8-137">ULONG</span></span>|  
|<span data-ttu-id="c80f8-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="c80f8-138">optAssemFlags</span></span>|<span data-ttu-id="c80f8-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="c80f8-139">ULONG</span></span>|  
|<span data-ttu-id="c80f8-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="c80f8-140">optAssemHalfSign</span></span>|<span data-ttu-id="c80f8-141">Bool (auch als DelaySign bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="c80f8-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="c80f8-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="c80f8-142">optAssemFileVersion</span></span>|<span data-ttu-id="c80f8-143">Codierte "Major.Minor.Build.Revision"--identisch mit ProductVersion - Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c80f8-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="c80f8-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="c80f8-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="c80f8-145">Zeichenfolge – codiert als "Major.Minor.Build.Revision".</span><span class="sxs-lookup"><span data-stu-id="c80f8-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="c80f8-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="c80f8-146">optLastAssemOption</span></span>|<span data-ttu-id="c80f8-147">Ein Leistungsindikator, der die Anzahl von Elementen.</span><span class="sxs-lookup"><span data-stu-id="c80f8-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c80f8-148">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c80f8-148">Requirements</span></span>  
 <span data-ttu-id="c80f8-149">**Header:** alink.h</span><span class="sxs-lookup"><span data-stu-id="c80f8-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="c80f8-150">**Bibliothek**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="c80f8-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c80f8-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c80f8-151">See Also</span></span>  
 [<span data-ttu-id="c80f8-152">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="c80f8-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
