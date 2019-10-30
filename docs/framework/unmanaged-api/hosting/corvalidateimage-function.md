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
ms.openlocfilehash: 42da5bb761ba8ce388bd41d46e8fdc4561ad0290
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136882"
---
# <a name="_corvalidateimage-function"></a><span data-ttu-id="36f85-102">_CorValidateImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="36f85-102">_CorValidateImage Function</span></span>
<span data-ttu-id="36f85-103">Überprüft Images des verwalteten Moduls, und benachrichtigt das Betriebssystemladeprogramm, nachdem sie geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="36f85-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36f85-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="36f85-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36f85-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="36f85-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="36f85-106">in Ein Zeiger auf die Startposition des Bilds, das als verwalteter Code validiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="36f85-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="36f85-107">Das Image muss bereits in den Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="36f85-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="36f85-108">in Der Dateiname des Bilds.</span><span class="sxs-lookup"><span data-stu-id="36f85-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36f85-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="36f85-109">Return Value</span></span>  
 <span data-ttu-id="36f85-110">Diese Funktion gibt die Standardwerte `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`und `E_FAIL`sowie die folgenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="36f85-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="36f85-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="36f85-111">Return value</span></span>|<span data-ttu-id="36f85-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36f85-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="36f85-113">Das Bild ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="36f85-113">The image is invalid.</span></span> <span data-ttu-id="36f85-114">Dieser Wert weist das HRESULT 0xC000007BL auf.</span><span class="sxs-lookup"><span data-stu-id="36f85-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="36f85-115">Das Bild ist gültig.</span><span class="sxs-lookup"><span data-stu-id="36f85-115">The image is valid.</span></span> <span data-ttu-id="36f85-116">Dieser Wert hat das HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="36f85-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36f85-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36f85-117">Remarks</span></span>  
 <span data-ttu-id="36f85-118">In Windows XP und höheren Versionen überprüft das Betriebssystem-Lade Modul die verwalteten Module, indem er das com-deskriptorverzeichnisbit im COFF-Header (Common Object File Format) untersucht.</span><span class="sxs-lookup"><span data-stu-id="36f85-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="36f85-119">Ein festgelegtes Bit gibt ein verwaltetes Modul an.</span><span class="sxs-lookup"><span data-stu-id="36f85-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="36f85-120">Wenn das Lade Modul ein verwaltetes Modul erkennt, lädt es Mscoree. dll und ruft `_CorValidateImage`auf, das die folgenden Aktionen ausführt:</span><span class="sxs-lookup"><span data-stu-id="36f85-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="36f85-121">Bestätigt, dass das Image ein gültiges verwaltetes Modul ist.</span><span class="sxs-lookup"><span data-stu-id="36f85-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="36f85-122">Ändert den Einstiegspunkt im Bild in einen Einstiegspunkt in der Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="36f85-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="36f85-123">Bei 64-Bit-Versionen von Windows ändert das Bild, das sich im Arbeitsspeicher befindet, indem es von das Format PE32 in das Format PE32 + Format transformiert wird.</span><span class="sxs-lookup"><span data-stu-id="36f85-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="36f85-124">Kehrt zum Lade Modul zurück, wenn die Images des verwalteten Moduls geladen werden.</span><span class="sxs-lookup"><span data-stu-id="36f85-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="36f85-125">Bei ausführbaren Images Ruft das Betriebssystem-Lade Programm dann die [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) -Funktion auf, unabhängig vom Einstiegspunkt, der in der ausführbaren Datei angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="36f85-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="36f85-126">Bei dll-assemblyimages Ruft das Lade Modul die [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) -Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="36f85-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="36f85-127">`_CorExeMain` oder `_CorDllMain` führt die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="36f85-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="36f85-128">Initialisiert die CLR.</span><span class="sxs-lookup"><span data-stu-id="36f85-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="36f85-129">Der verwaltete Einstiegspunkt wird aus dem CLR-Header der Assembly lokalisiert.</span><span class="sxs-lookup"><span data-stu-id="36f85-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="36f85-130">Startet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="36f85-130">Begins execution.</span></span>  
  
 <span data-ttu-id="36f85-131">Das Lade Modul ruft die [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) -Funktion auf, wenn verwaltete Modul Images entladen werden.</span><span class="sxs-lookup"><span data-stu-id="36f85-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="36f85-132">Diese Funktion führt jedoch keine Aktion aus. Er gibt nur zurück.</span><span class="sxs-lookup"><span data-stu-id="36f85-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36f85-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36f85-133">Requirements</span></span>  
 <span data-ttu-id="36f85-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36f85-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36f85-135">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="36f85-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36f85-136">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="36f85-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36f85-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36f85-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36f85-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36f85-138">See also</span></span>

- [<span data-ttu-id="36f85-139">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="36f85-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
