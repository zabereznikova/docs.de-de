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
ms.openlocfilehash: 3a6da0e845fa50d090cdf0808b211a5806c40961
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178214"
---
# <a name="_corvalidateimage-function"></a><span data-ttu-id="15965-102">_CorValidateImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="15965-102">_CorValidateImage Function</span></span>
<span data-ttu-id="15965-103">Überprüft Images des verwalteten Moduls, und benachrichtigt das Betriebssystemladeprogramm, nachdem sie geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="15965-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15965-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15965-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15965-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="15965-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="15965-106">[in] Ein Zeiger auf den Startspeicherort des Bildes, der als verwalteter Code überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="15965-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="15965-107">Das Bild muss bereits in den Speicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="15965-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="15965-108">[in] Der Dateiname des Bildes.</span><span class="sxs-lookup"><span data-stu-id="15965-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15965-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="15965-109">Return Value</span></span>  
 <span data-ttu-id="15965-110">Diese Funktion gibt `E_INVALIDARG`die `E_OUTOFMEMORY` `E_UNEXPECTED`Standardwerte `E_FAIL`, , und sowie die folgenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="15965-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="15965-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="15965-111">Return value</span></span>|<span data-ttu-id="15965-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15965-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="15965-113">Das Bild ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="15965-113">The image is invalid.</span></span> <span data-ttu-id="15965-114">Dieser Wert hat den HRESULT 0xC00007BL.</span><span class="sxs-lookup"><span data-stu-id="15965-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="15965-115">Das Bild ist gültig.</span><span class="sxs-lookup"><span data-stu-id="15965-115">The image is valid.</span></span> <span data-ttu-id="15965-116">Dieser Wert hat den HRESULT 0x0000000L.</span><span class="sxs-lookup"><span data-stu-id="15965-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15965-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="15965-117">Remarks</span></span>  
 <span data-ttu-id="15965-118">In Windows XP und neueren Versionen sucht der Betriebssystemlader nach verwalteten Modulen, indem er das COM Descriptor Directory-Bit im COFF-Header (Common Object File Format) untersucht.</span><span class="sxs-lookup"><span data-stu-id="15965-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="15965-119">Ein festgelegtes Bit gibt ein verwaltetes Modul an.</span><span class="sxs-lookup"><span data-stu-id="15965-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="15965-120">Wenn der Lader ein verwaltetes Modul erkennt, lädt er `_CorValidateImage`MsCorEE.dll und ruft auf, die die folgenden Aktionen ausführt:</span><span class="sxs-lookup"><span data-stu-id="15965-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="15965-121">Bestätigt, dass es sich bei dem Abbild um ein gültiges verwaltetes Modul handelt.</span><span class="sxs-lookup"><span data-stu-id="15965-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="15965-122">Ändert den Einstiegspunkt im Bild in einen Einstiegspunkt in der Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="15965-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="15965-123">Ändert bei 64-Bit-Versionen von Windows das im Speicher enthaltene Bild, indem es vom PE32 in das PE32+-Format transformiert wird.</span><span class="sxs-lookup"><span data-stu-id="15965-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="15965-124">Kehrt zum Ladeprogramm zurück, wenn die Images des verwalteten Moduls geladen werden.</span><span class="sxs-lookup"><span data-stu-id="15965-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="15965-125">Bei ausführbaren Images ruft der Betriebssystemlader dann die [_CorExeMain-Funktion](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) auf, unabhängig vom in der ausführbaren Datei angegebenen Einstiegspunkt.</span><span class="sxs-lookup"><span data-stu-id="15965-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="15965-126">Bei DLL-Assemblybildern ruft der Lader die [_CorDllMain-Funktion](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) auf.</span><span class="sxs-lookup"><span data-stu-id="15965-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="15965-127">`_CorExeMain`oder `_CorDllMain` führt die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="15965-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="15965-128">Initialisiert die CLR.</span><span class="sxs-lookup"><span data-stu-id="15965-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="15965-129">Sucht den verwalteten Einstiegspunkt aus dem CLR-Header der Assembly.</span><span class="sxs-lookup"><span data-stu-id="15965-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="15965-130">Beginnt mit der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="15965-130">Begins execution.</span></span>  
  
 <span data-ttu-id="15965-131">Der Loader ruft die [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) Funktion auf, wenn verwaltete Modulabbilder entladen werden.</span><span class="sxs-lookup"><span data-stu-id="15965-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="15965-132">Diese Funktion führt jedoch keine Aktion aus. es kehrt einfach zurück.</span><span class="sxs-lookup"><span data-stu-id="15965-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15965-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="15965-133">Requirements</span></span>  
 <span data-ttu-id="15965-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15965-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15965-135">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="15965-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15965-136">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="15965-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15965-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15965-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15965-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15965-138">See also</span></span>

- [<span data-ttu-id="15965-139">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="15965-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
