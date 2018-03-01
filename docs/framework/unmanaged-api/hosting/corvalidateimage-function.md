---
title: _CorValidateImage-Funktion
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
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03deb62a84a1e9c6cee898fe0023c34b8c538ece
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="48d61-102">_CorValidateImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="48d61-102">_CorValidateImage Function</span></span>
<span data-ttu-id="48d61-103">Überprüft Images des verwalteten Moduls, und benachrichtigt das Betriebssystemladeprogramm, nachdem sie geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="48d61-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d61-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48d61-104">Syntax</span></span>  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48d61-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="48d61-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="48d61-106">[in] Ein Zeiger auf die Startposition des Bilds als überprüfen zu verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="48d61-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="48d61-107">Das Bild muss bereits in den Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="48d61-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="48d61-108">[in] Der Dateiname des Bilds.</span><span class="sxs-lookup"><span data-stu-id="48d61-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48d61-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="48d61-109">Return Value</span></span>  
 <span data-ttu-id="48d61-110">Diese Funktion gibt die Standardwerte `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, und `E_FAIL`, sowie die folgenden Werte.</span><span class="sxs-lookup"><span data-stu-id="48d61-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="48d61-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="48d61-111">Return value</span></span>|<span data-ttu-id="48d61-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48d61-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="48d61-113">Das Bild ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="48d61-113">The image is invalid.</span></span> <span data-ttu-id="48d61-114">Dieser Wert hat den HRESULT 0xC000007BL auf.</span><span class="sxs-lookup"><span data-stu-id="48d61-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="48d61-115">Das Bild ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="48d61-115">The image is valid.</span></span> <span data-ttu-id="48d61-116">Dieser Wert hat den HRESULT 0x00000000L auf.</span><span class="sxs-lookup"><span data-stu-id="48d61-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48d61-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48d61-117">Remarks</span></span>  
 <span data-ttu-id="48d61-118">In Windows XP und höheren Versionen überprüft vom Ladeprogramm des Betriebssystems nach verwalteten Modulen durch untersuchen das Verzeichnis der COM-Deskriptor Bit im Header common Object-Datei-Format (COFF).</span><span class="sxs-lookup"><span data-stu-id="48d61-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="48d61-119">Ein festgelegtes Bit gibt ein verwaltetes Modul an.</span><span class="sxs-lookup"><span data-stu-id="48d61-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="48d61-120">Wenn das Ladeprogramm eine verwaltete Module erkennt, lädt es "Mscoree.dll" und Aufrufe `_CorValidateImage`, die folgenden Aktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="48d61-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
-   <span data-ttu-id="48d61-121">Bestätigt, dass das Bild ein gültiges verwaltetes Modul ist.</span><span class="sxs-lookup"><span data-stu-id="48d61-121">Confirms that the image is a valid managed module.</span></span>  
  
-   <span data-ttu-id="48d61-122">Ändert den Einstiegspunkt in das Image auf einen Einstiegspunkt in die common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="48d61-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
-   <span data-ttu-id="48d61-123">Für 64-Bit-Versionen von Windows ändert das Image im Arbeitsspeicher vom Format PE32 in das Format PE32 + transformiert.</span><span class="sxs-lookup"><span data-stu-id="48d61-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
-   <span data-ttu-id="48d61-124">Benachrichtigt das Ladeprogramm, wenn die Images der verwalteten Module geladen werden.</span><span class="sxs-lookup"><span data-stu-id="48d61-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="48d61-125">Für ausführbare Images vom Ladeprogramm des Betriebssystems dann ruft der [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) -Funktion, unabhängig von den Einstiegspunkt in die ausführbare Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="48d61-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="48d61-126">Für DLL-Assembly-Images, das Ladeprogramm ruft die [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="48d61-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="48d61-127">`_CorExeMain`oder `_CorDllMain` führt die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="48d61-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
-   <span data-ttu-id="48d61-128">Initialisiert die CLR.</span><span class="sxs-lookup"><span data-stu-id="48d61-128">Initializes the CLR.</span></span>  
  
-   <span data-ttu-id="48d61-129">Sucht den verwalteten Einstiegspunkt aus der Assembly aneinander gehängt CLR-Header.</span><span class="sxs-lookup"><span data-stu-id="48d61-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
-   <span data-ttu-id="48d61-130">Beginnt die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="48d61-130">Begins execution.</span></span>  
  
 <span data-ttu-id="48d61-131">Ruft die Ladeprogramm der [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) funktionieren bei verwalteten Images des Moduls entladen werden.</span><span class="sxs-lookup"><span data-stu-id="48d61-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="48d61-132">Diese Funktion ist jedoch keine Aktion ausgeführt; Es gibt nur zurück.</span><span class="sxs-lookup"><span data-stu-id="48d61-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48d61-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48d61-133">Requirements</span></span>  
 <span data-ttu-id="48d61-134">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48d61-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48d61-135">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="48d61-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48d61-136">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="48d61-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="48d61-137">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48d61-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d61-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48d61-138">See Also</span></span>  
 [<span data-ttu-id="48d61-139">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="48d61-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
