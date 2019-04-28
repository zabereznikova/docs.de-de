---
title: AssemblyOptions-Enumeration
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 293787d7798768ff2b4e2fb8fec9ed201fdb85ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790103"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="fd0eb-102">AssemblyOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fd0eb-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="fd0eb-103">Listet die Assemblyoptionen.</span><span class="sxs-lookup"><span data-stu-id="fd0eb-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd0eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd0eb-104">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="fd0eb-105">Felder</span><span class="sxs-lookup"><span data-stu-id="fd0eb-105">Fields</span></span>  
  
|<span data-ttu-id="fd0eb-106">Feld</span><span class="sxs-lookup"><span data-stu-id="fd0eb-106">Field</span></span>|<span data-ttu-id="fd0eb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd0eb-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fd0eb-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="fd0eb-108">optAssemTitle</span></span>|<span data-ttu-id="fd0eb-109">Zeichenfolge – den Assemblytitel darstellt.</span><span class="sxs-lookup"><span data-stu-id="fd0eb-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="fd0eb-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="fd0eb-110">optAssemDescription</span></span>|<span data-ttu-id="fd0eb-111">Zeichenfolge – die Beschreibung der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="fd0eb-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="fd0eb-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="fd0eb-112">optAssemConfig</span></span>|<span data-ttu-id="fd0eb-113">Zeichenfolge – enthält die Assemblykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="fd0eb-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="fd0eb-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="fd0eb-114">optAssemOS</span></span>|<span data-ttu-id="fd0eb-115">-Codierte Zeichenfolge: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="fd0eb-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="fd0eb-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="fd0eb-116">optAssemProcessor</span></span>|<span data-ttu-id="fd0eb-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="fd0eb-117">ULONG</span></span>|  
|<span data-ttu-id="fd0eb-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="fd0eb-118">optAssemLocale</span></span>|<span data-ttu-id="fd0eb-119">Zeichenfolge – das Gebietsschema der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="fd0eb-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="fd0eb-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="fd0eb-120">optAssemVersion</span></span>|<span data-ttu-id="fd0eb-121">Zeichenfolge – gibt an, codiert als: "Major.Minor.Build.Revision".</span><span class="sxs-lookup"><span data-stu-id="fd0eb-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="fd0eb-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="fd0eb-122">optAssemCompany</span></span>|<span data-ttu-id="fd0eb-123">Zeichenfolge – das Unternehmen enthält.</span><span class="sxs-lookup"><span data-stu-id="fd0eb-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="fd0eb-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="fd0eb-124">optAssemProduct</span></span>|<span data-ttu-id="fd0eb-125">Zeichenfolge – der Name des Produkts enthält.</span><span class="sxs-lookup"><span data-stu-id="fd0eb-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="fd0eb-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="fd0eb-126">optAssemProductVersion</span></span>|<span data-ttu-id="fd0eb-127">Zeichenfolge (auch bekannt als InformationalVersion bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="fd0eb-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="fd0eb-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="fd0eb-128">optAssemCopyright</span></span>|<span data-ttu-id="fd0eb-129">Zeichenfolge – die copyright-Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="fd0eb-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="fd0eb-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="fd0eb-130">optAssemTrademark</span></span>|<span data-ttu-id="fd0eb-131">Zeichenfolge – die Markeninformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="fd0eb-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="fd0eb-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="fd0eb-132">optAssemKeyFile</span></span>|<span data-ttu-id="fd0eb-133">Zeichenfolge (Dateiname).</span><span class="sxs-lookup"><span data-stu-id="fd0eb-133">String (file name).</span></span>|  
|<span data-ttu-id="fd0eb-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="fd0eb-134">optAssemKeyName</span></span>|<span data-ttu-id="fd0eb-135">Zeichenfolge (wichtigsten Name).</span><span class="sxs-lookup"><span data-stu-id="fd0eb-135">String (The key name).</span></span>|  
|<span data-ttu-id="fd0eb-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="fd0eb-136">optAssemAlgID</span></span>|<span data-ttu-id="fd0eb-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="fd0eb-137">ULONG</span></span>|  
|<span data-ttu-id="fd0eb-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="fd0eb-138">optAssemFlags</span></span>|<span data-ttu-id="fd0eb-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="fd0eb-139">ULONG</span></span>|  
|<span data-ttu-id="fd0eb-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="fd0eb-140">optAssemHalfSign</span></span>|<span data-ttu-id="fd0eb-141">"Bool" (auch als DelaySign bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="fd0eb-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="fd0eb-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="fd0eb-142">optAssemFileVersion</span></span>|<span data-ttu-id="fd0eb-143">Zeichenfolge – als "Hauptversion.Nebenversion.Build.Revision"--identisch mit ProductVersion codiert.</span><span class="sxs-lookup"><span data-stu-id="fd0eb-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="fd0eb-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="fd0eb-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="fd0eb-145">Zeichenfolge – als "Hauptversion.Nebenversion.Build.Revision" codiert.</span><span class="sxs-lookup"><span data-stu-id="fd0eb-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="fd0eb-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="fd0eb-146">optLastAssemOption</span></span>|<span data-ttu-id="fd0eb-147">Ein Zähler, der die Anzahl der Elemente.</span><span class="sxs-lookup"><span data-stu-id="fd0eb-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fd0eb-148">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd0eb-148">Requirements</span></span>  
 <span data-ttu-id="fd0eb-149">**Header:** alink.h</span><span class="sxs-lookup"><span data-stu-id="fd0eb-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="fd0eb-150">**Bibliothek**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="fd0eb-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd0eb-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd0eb-151">See also</span></span>

- [<span data-ttu-id="fd0eb-152">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="fd0eb-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
