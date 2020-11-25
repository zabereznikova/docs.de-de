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
ms.openlocfilehash: 352e1acd1fdd8297754e18b2e8c6448ea723a557
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717030"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="05eef-102">AssemblyOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="05eef-102">AssemblyOptions Enumeration</span></span>

<span data-ttu-id="05eef-103">Listet die Assemblyoptionen auf.</span><span class="sxs-lookup"><span data-stu-id="05eef-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05eef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05eef-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="fields"></a><span data-ttu-id="05eef-105">Felder</span><span class="sxs-lookup"><span data-stu-id="05eef-105">Fields</span></span>  
  
|<span data-ttu-id="05eef-106">Feld</span><span class="sxs-lookup"><span data-stu-id="05eef-106">Field</span></span>|<span data-ttu-id="05eef-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="05eef-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="05eef-108">optassemblytitle</span><span class="sxs-lookup"><span data-stu-id="05eef-108">optAssemTitle</span></span>|<span data-ttu-id="05eef-109">String: stellt den Assemblytitel dar.</span><span class="sxs-lookup"><span data-stu-id="05eef-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="05eef-110">optassemdescription</span><span class="sxs-lookup"><span data-stu-id="05eef-110">optAssemDescription</span></span>|<span data-ttu-id="05eef-111">String: enthält die Beschreibung der Assembly.</span><span class="sxs-lookup"><span data-stu-id="05eef-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="05eef-112">optassemconfig</span><span class="sxs-lookup"><span data-stu-id="05eef-112">optAssemConfig</span></span>|<span data-ttu-id="05eef-113">String: enthält die Assemblykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="05eef-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="05eef-114">optassemos</span><span class="sxs-lookup"><span data-stu-id="05eef-114">optAssemOS</span></span>|<span data-ttu-id="05eef-115">Zeichenfolge codiert als: "dwOSPlatformId. dwOSMajorVersion. dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="05eef-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="05eef-116">optassemprocessor</span><span class="sxs-lookup"><span data-stu-id="05eef-116">optAssemProcessor</span></span>|<span data-ttu-id="05eef-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="05eef-117">ULONG</span></span>|  
|<span data-ttu-id="05eef-118">optassemlocale</span><span class="sxs-lookup"><span data-stu-id="05eef-118">optAssemLocale</span></span>|<span data-ttu-id="05eef-119">String: enthält das assemblygebiets Schema.</span><span class="sxs-lookup"><span data-stu-id="05eef-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="05eef-120">optassemversionsversion</span><span class="sxs-lookup"><span data-stu-id="05eef-120">optAssemVersion</span></span>|<span data-ttu-id="05eef-121">Zeichen folgen codiert als: "Major. Minor. Build. Revision".</span><span class="sxs-lookup"><span data-stu-id="05eef-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="05eef-122">optassemcompany</span><span class="sxs-lookup"><span data-stu-id="05eef-122">optAssemCompany</span></span>|<span data-ttu-id="05eef-123">String: enthält das Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="05eef-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="05eef-124">optassemproduct</span><span class="sxs-lookup"><span data-stu-id="05eef-124">optAssemProduct</span></span>|<span data-ttu-id="05eef-125">String: enthält den Produktnamen.</span><span class="sxs-lookup"><span data-stu-id="05eef-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="05eef-126">optassemproductversion</span><span class="sxs-lookup"><span data-stu-id="05eef-126">optAssemProductVersion</span></span>|<span data-ttu-id="05eef-127">String (auch als InformationalVersion bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="05eef-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="05eef-128">optassemcopyright</span><span class="sxs-lookup"><span data-stu-id="05eef-128">optAssemCopyright</span></span>|<span data-ttu-id="05eef-129">String: enthält Informationen zum Copyright.</span><span class="sxs-lookup"><span data-stu-id="05eef-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="05eef-130">optassemtrademark</span><span class="sxs-lookup"><span data-stu-id="05eef-130">optAssemTrademark</span></span>|<span data-ttu-id="05eef-131">String: enthält die Markeninformationen.</span><span class="sxs-lookup"><span data-stu-id="05eef-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="05eef-132">optassemkeyfile</span><span class="sxs-lookup"><span data-stu-id="05eef-132">optAssemKeyFile</span></span>|<span data-ttu-id="05eef-133">Zeichenfolge (Dateiname).</span><span class="sxs-lookup"><span data-stu-id="05eef-133">String (file name).</span></span>|  
|<span data-ttu-id="05eef-134">optassemkeyname</span><span class="sxs-lookup"><span data-stu-id="05eef-134">optAssemKeyName</span></span>|<span data-ttu-id="05eef-135">Zeichenfolge (der Schlüssel Name).</span><span class="sxs-lookup"><span data-stu-id="05eef-135">String (The key name).</span></span>|  
|<span data-ttu-id="05eef-136">optassemalgid</span><span class="sxs-lookup"><span data-stu-id="05eef-136">optAssemAlgID</span></span>|<span data-ttu-id="05eef-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="05eef-137">ULONG</span></span>|  
|<span data-ttu-id="05eef-138">optassemflags</span><span class="sxs-lookup"><span data-stu-id="05eef-138">optAssemFlags</span></span>|<span data-ttu-id="05eef-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="05eef-139">ULONG</span></span>|  
|<span data-ttu-id="05eef-140">optassemhalfsign</span><span class="sxs-lookup"><span data-stu-id="05eef-140">optAssemHalfSign</span></span>|<span data-ttu-id="05eef-141">Bool (auch als "Delta Sign" bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="05eef-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="05eef-142">optassemfileversion</span><span class="sxs-lookup"><span data-stu-id="05eef-142">optAssemFileVersion</span></span>|<span data-ttu-id="05eef-143">Zeichen folgen codiert als "Major. Minor. Build. Revision"-identisch mit ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="05eef-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="05eef-144">optassemsatellitever</span><span class="sxs-lookup"><span data-stu-id="05eef-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="05eef-145">Zeichen folgen codiert als "Major. Minor. Build. Revision".</span><span class="sxs-lookup"><span data-stu-id="05eef-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="05eef-146">optlastassemsoption</span><span class="sxs-lookup"><span data-stu-id="05eef-146">optLastAssemOption</span></span>|<span data-ttu-id="05eef-147">Ein-Wert für die Anzahl der Elemente.</span><span class="sxs-lookup"><span data-stu-id="05eef-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05eef-148">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="05eef-148">Requirements</span></span>  

 <span data-ttu-id="05eef-149">**Header:** Alink. h</span><span class="sxs-lookup"><span data-stu-id="05eef-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="05eef-150">**Bibliothek**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="05eef-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05eef-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05eef-151">See also</span></span>

- [<span data-ttu-id="05eef-152">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="05eef-152">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
