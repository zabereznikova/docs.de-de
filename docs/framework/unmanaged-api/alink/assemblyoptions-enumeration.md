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
ms.openlocfilehash: ed45e06297b77ea60304cdcfe1b08e97f9e4c085
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446586"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="8fc5a-102">AssemblyOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8fc5a-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="8fc5a-103">Listet die Assemblyoptionen auf.</span><span class="sxs-lookup"><span data-stu-id="8fc5a-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fc5a-104">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="8fc5a-105">Felder</span><span class="sxs-lookup"><span data-stu-id="8fc5a-105">Fields</span></span>  
  
|<span data-ttu-id="8fc5a-106">Field</span><span class="sxs-lookup"><span data-stu-id="8fc5a-106">Field</span></span>|<span data-ttu-id="8fc5a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fc5a-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8fc5a-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="8fc5a-108">optAssemTitle</span></span>|<span data-ttu-id="8fc5a-109">String: stellt den Assemblytitel dar.</span><span class="sxs-lookup"><span data-stu-id="8fc5a-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="8fc5a-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="8fc5a-110">optAssemDescription</span></span>|<span data-ttu-id="8fc5a-111">String: enthält die Beschreibung der Assembly.</span><span class="sxs-lookup"><span data-stu-id="8fc5a-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="8fc5a-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="8fc5a-112">optAssemConfig</span></span>|<span data-ttu-id="8fc5a-113">String: enthält die Assemblykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="8fc5a-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="8fc5a-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="8fc5a-114">optAssemOS</span></span>|<span data-ttu-id="8fc5a-115">Zeichenfolge codiert als: "dwOSPlatformId. dwOSMajorVersion. dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="8fc5a-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="8fc5a-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="8fc5a-116">optAssemProcessor</span></span>|<span data-ttu-id="8fc5a-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="8fc5a-117">ULONG</span></span>|  
|<span data-ttu-id="8fc5a-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="8fc5a-118">optAssemLocale</span></span>|<span data-ttu-id="8fc5a-119">String: enthält das assemblygebiets Schema.</span><span class="sxs-lookup"><span data-stu-id="8fc5a-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="8fc5a-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="8fc5a-120">optAssemVersion</span></span>|<span data-ttu-id="8fc5a-121">Zeichen folgen codiert als: "Major. Minor. Build. Revision".</span><span class="sxs-lookup"><span data-stu-id="8fc5a-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="8fc5a-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="8fc5a-122">optAssemCompany</span></span>|<span data-ttu-id="8fc5a-123">String: enthält das Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="8fc5a-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="8fc5a-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="8fc5a-124">optAssemProduct</span></span>|<span data-ttu-id="8fc5a-125">String: enthält den Produktnamen.</span><span class="sxs-lookup"><span data-stu-id="8fc5a-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="8fc5a-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="8fc5a-126">optAssemProductVersion</span></span>|<span data-ttu-id="8fc5a-127">String (auch als InformationalVersion bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="8fc5a-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="8fc5a-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="8fc5a-128">optAssemCopyright</span></span>|<span data-ttu-id="8fc5a-129">String: enthält Informationen zum Copyright.</span><span class="sxs-lookup"><span data-stu-id="8fc5a-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="8fc5a-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="8fc5a-130">optAssemTrademark</span></span>|<span data-ttu-id="8fc5a-131">String: enthält die Markeninformationen.</span><span class="sxs-lookup"><span data-stu-id="8fc5a-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="8fc5a-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="8fc5a-132">optAssemKeyFile</span></span>|<span data-ttu-id="8fc5a-133">Zeichenfolge (Dateiname).</span><span class="sxs-lookup"><span data-stu-id="8fc5a-133">String (file name).</span></span>|  
|<span data-ttu-id="8fc5a-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="8fc5a-134">optAssemKeyName</span></span>|<span data-ttu-id="8fc5a-135">Zeichenfolge (der Schlüssel Name).</span><span class="sxs-lookup"><span data-stu-id="8fc5a-135">String (The key name).</span></span>|  
|<span data-ttu-id="8fc5a-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="8fc5a-136">optAssemAlgID</span></span>|<span data-ttu-id="8fc5a-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="8fc5a-137">ULONG</span></span>|  
|<span data-ttu-id="8fc5a-138">optassemflags</span><span class="sxs-lookup"><span data-stu-id="8fc5a-138">optAssemFlags</span></span>|<span data-ttu-id="8fc5a-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="8fc5a-139">ULONG</span></span>|  
|<span data-ttu-id="8fc5a-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="8fc5a-140">optAssemHalfSign</span></span>|<span data-ttu-id="8fc5a-141">Bool (auch als "Delta Sign" bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="8fc5a-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="8fc5a-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="8fc5a-142">optAssemFileVersion</span></span>|<span data-ttu-id="8fc5a-143">Zeichen folgen codiert als "Major. Minor. Build. Revision"-identisch mit ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="8fc5a-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="8fc5a-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="8fc5a-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="8fc5a-145">Zeichen folgen codiert als "Major. Minor. Build. Revision".</span><span class="sxs-lookup"><span data-stu-id="8fc5a-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="8fc5a-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="8fc5a-146">optLastAssemOption</span></span>|<span data-ttu-id="8fc5a-147">Ein-Wert für die Anzahl der Elemente.</span><span class="sxs-lookup"><span data-stu-id="8fc5a-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8fc5a-148">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8fc5a-148">Requirements</span></span>  
 <span data-ttu-id="8fc5a-149">**Header:** Alink. h</span><span class="sxs-lookup"><span data-stu-id="8fc5a-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="8fc5a-150">**Bibliothek**: Alink. dll</span><span class="sxs-lookup"><span data-stu-id="8fc5a-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc5a-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fc5a-151">See also</span></span>

- [<span data-ttu-id="8fc5a-152">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="8fc5a-152">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
