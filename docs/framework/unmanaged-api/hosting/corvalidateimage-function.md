---
title: _CorValidateImage-Funktion
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6f1d76ef5cf36bcbab29a33647520663f822798
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770036"
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="6c389-102">_CorValidateImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="6c389-102">_CorValidateImage Function</span></span>
<span data-ttu-id="6c389-103">Überprüft Images des verwalteten Moduls, und benachrichtigt das Betriebssystemladeprogramm, nachdem sie geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="6c389-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c389-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c389-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c389-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c389-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="6c389-106">[in] Ein Zeiger auf den Anfangsort des Bildes, das als Überprüfen von verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="6c389-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="6c389-107">Das Image muss bereits in den Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="6c389-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="6c389-108">[in] Der Dateiname des Bilds.</span><span class="sxs-lookup"><span data-stu-id="6c389-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c389-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6c389-109">Return Value</span></span>  
 <span data-ttu-id="6c389-110">Diese Funktion gibt die Standardwerte zurück `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, und `E_FAIL`, sowie die folgenden Werte.</span><span class="sxs-lookup"><span data-stu-id="6c389-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="6c389-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6c389-111">Return value</span></span>|<span data-ttu-id="6c389-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c389-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="6c389-113">Das Image ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="6c389-113">The image is invalid.</span></span> <span data-ttu-id="6c389-114">Dieser Wert muss es sich um das HRESULT 0xC000007BL auf.</span><span class="sxs-lookup"><span data-stu-id="6c389-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="6c389-115">Das Image ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="6c389-115">The image is valid.</span></span> <span data-ttu-id="6c389-116">Dieser Wert muss es sich um das HRESULT 0x00000000L auf.</span><span class="sxs-lookup"><span data-stu-id="6c389-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c389-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c389-117">Remarks</span></span>  
 <span data-ttu-id="6c389-118">In Windows XP und höheren Versionen überprüft vom Ladeprogramm des Betriebssystems nach verwalteten Modulen durch untersuchen das Verzeichnis der COM-Deskriptor-Bit in den Header zu common Object File-Format (COFF).</span><span class="sxs-lookup"><span data-stu-id="6c389-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="6c389-119">Ein festgelegtes Bit gibt an, ein verwaltetes Modul.</span><span class="sxs-lookup"><span data-stu-id="6c389-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="6c389-120">Wenn das Ladeprogramm ein verwaltetes Modul erkannt wird, lädt es "Mscoree.dll" und ruft `_CorValidateImage`, die die folgenden Aktionen ausführt:</span><span class="sxs-lookup"><span data-stu-id="6c389-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="6c389-121">Bestätigt, dass das Bild, ein gültiges verwaltetes Modul ist.</span><span class="sxs-lookup"><span data-stu-id="6c389-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="6c389-122">Ändert den Einstiegspunkt in das Abbild an einen Einstiegspunkt in die common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6c389-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="6c389-123">Für 64-Bit-Versionen von Windows ändert das Image im Arbeitsspeicher vom Format PE32 in das Format PE32 + transformieren.</span><span class="sxs-lookup"><span data-stu-id="6c389-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="6c389-124">Benachrichtigt das Ladeprogramm, wenn die Images des verwalteten Moduls geladen werden.</span><span class="sxs-lookup"><span data-stu-id="6c389-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="6c389-125">Für ausführbare Images vom Ladeprogramm des Betriebssystems dann ruft der [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) -Funktion, unabhängig von der Einstiegspunkt in die ausführbare Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="6c389-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="6c389-126">DLL-Assembly-Images, das Ladeprogramm ruft die [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="6c389-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="6c389-127">`_CorExeMain` oder `_CorDllMain` führt folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6c389-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="6c389-128">Initialisiert die CLR.</span><span class="sxs-lookup"><span data-stu-id="6c389-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="6c389-129">Sucht den verwalteten Einstiegspunkt von CLR-Header der Assembly an.</span><span class="sxs-lookup"><span data-stu-id="6c389-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="6c389-130">Beginnt die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="6c389-130">Begins execution.</span></span>  
  
 <span data-ttu-id="6c389-131">Die Aufrufe der Loader die [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) funktionieren, wenn verwaltete Modulimages entladen.</span><span class="sxs-lookup"><span data-stu-id="6c389-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="6c389-132">Diese Funktion führt jedoch keine Maßnahmen; Es gibt nur zurück.</span><span class="sxs-lookup"><span data-stu-id="6c389-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c389-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c389-133">Requirements</span></span>  
 <span data-ttu-id="6c389-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c389-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c389-135">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6c389-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c389-136">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6c389-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c389-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c389-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c389-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c389-138">See also</span></span>

- [<span data-ttu-id="6c389-139">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="6c389-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
