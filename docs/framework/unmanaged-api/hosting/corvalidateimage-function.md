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
ms.openlocfilehash: 426b39aa3d1ada5ae44565a742b70681a7bcf6d3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493434"
---
# <a name="_corvalidateimage-function"></a><span data-ttu-id="c0097-102">_CorValidateImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="c0097-102">_CorValidateImage Function</span></span>
<span data-ttu-id="c0097-103">Überprüft Images des verwalteten Moduls, und benachrichtigt das Betriebssystemladeprogramm, nachdem sie geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="c0097-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0097-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0097-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0097-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0097-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="c0097-106">in Ein Zeiger auf die Startposition des Bilds, das als verwalteter Code validiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0097-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="c0097-107">Das Image muss bereits in den Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="c0097-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="c0097-108">in Der Dateiname des Bilds.</span><span class="sxs-lookup"><span data-stu-id="c0097-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0097-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c0097-109">Return Value</span></span>  
 <span data-ttu-id="c0097-110">Diese Funktion gibt die Standardwerte,, `E_INVALIDARG` `E_OUTOFMEMORY` und sowie `E_UNEXPECTED` `E_FAIL` die folgenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="c0097-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="c0097-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c0097-111">Return value</span></span>|<span data-ttu-id="c0097-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c0097-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="c0097-113">Das Bild ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="c0097-113">The image is invalid.</span></span> <span data-ttu-id="c0097-114">Dieser Wert weist das HRESULT 0xC000007BL auf.</span><span class="sxs-lookup"><span data-stu-id="c0097-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="c0097-115">Das Bild ist gültig.</span><span class="sxs-lookup"><span data-stu-id="c0097-115">The image is valid.</span></span> <span data-ttu-id="c0097-116">Dieser Wert hat das HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="c0097-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0097-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c0097-117">Remarks</span></span>  
 <span data-ttu-id="c0097-118">In Windows XP und höheren Versionen überprüft das Betriebssystem-Lade Modul die verwalteten Module, indem er das com-deskriptorverzeichnisbit im COFF-Header (Common Object File Format) untersucht.</span><span class="sxs-lookup"><span data-stu-id="c0097-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="c0097-119">Ein festgelegtes Bit gibt ein verwaltetes Modul an.</span><span class="sxs-lookup"><span data-stu-id="c0097-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="c0097-120">Wenn das Lade Modul ein verwaltetes Modul erkennt, lädt es Mscoree. dll und ruft auf `_CorValidateImage` , was die folgenden Aktionen ausführt:</span><span class="sxs-lookup"><span data-stu-id="c0097-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="c0097-121">Bestätigt, dass das Image ein gültiges verwaltetes Modul ist.</span><span class="sxs-lookup"><span data-stu-id="c0097-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="c0097-122">Ändert den Einstiegspunkt im Bild in einen Einstiegspunkt in der Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c0097-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="c0097-123">Bei 64-Bit-Versionen von Windows ändert das Bild, das sich im Arbeitsspeicher befindet, indem es von das Format PE32 in das Format PE32 + Format transformiert wird.</span><span class="sxs-lookup"><span data-stu-id="c0097-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="c0097-124">Kehrt zum Lade Modul zurück, wenn die Images des verwalteten Moduls geladen werden.</span><span class="sxs-lookup"><span data-stu-id="c0097-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="c0097-125">Bei ausführbaren Images Ruft das Betriebssystem-Lade Programm dann die [_CorExeMain](corexemain-function.md) -Funktion auf, unabhängig vom Einstiegspunkt, der in der ausführbaren Datei angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c0097-125">For executable images, the operating system loader then calls the [_CorExeMain](corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="c0097-126">Bei dll-assemblyimages Ruft das Lade Modul die [_CorDllMain](cordllmain-function.md) -Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="c0097-126">For DLL assembly images, the loader calls the [_CorDllMain](cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="c0097-127">`_CorExeMain`oder `_CorDllMain` führt die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c0097-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="c0097-128">Initialisiert die CLR.</span><span class="sxs-lookup"><span data-stu-id="c0097-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="c0097-129">Der verwaltete Einstiegspunkt wird aus dem CLR-Header der Assembly lokalisiert.</span><span class="sxs-lookup"><span data-stu-id="c0097-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="c0097-130">Startet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="c0097-130">Begins execution.</span></span>  
  
 <span data-ttu-id="c0097-131">Das Lade Modul ruft die [_CorImageUnloading](corimageunloading-function.md) -Funktion auf, wenn verwaltete Modul Images entladen werden.</span><span class="sxs-lookup"><span data-stu-id="c0097-131">The loader calls the [_CorImageUnloading](corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="c0097-132">Diese Funktion führt jedoch keine Aktion aus. Er gibt nur zurück.</span><span class="sxs-lookup"><span data-stu-id="c0097-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0097-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c0097-133">Requirements</span></span>  
 <span data-ttu-id="c0097-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0097-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0097-135">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c0097-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0097-136">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c0097-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0097-137">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0097-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0097-138">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="c0097-138">See also</span></span>

- [<span data-ttu-id="c0097-139">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="c0097-139">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
