---
title: GetTypeLibInfo-Funktion
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56a9b97f37240e385dbd1788bafea62578d687a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457866"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="1ec88-102">GetTypeLibInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="1ec88-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="1ec88-103">Gibt Informationen zu der angegebenen Typbibliothek durch Untersuchen der [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) Struktur.</span><span class="sxs-lookup"><span data-stu-id="1ec88-103">Returns information about the specified type library by examining its [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ec88-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ec88-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ec88-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ec88-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="1ec88-106">[in] Der Dateiname der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="1ec88-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="1ec88-107">[out] Die GUID der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="1ec88-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="1ec88-108">[out] Die Lokalisierungs-ID der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="1ec88-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="1ec88-109">[out] Ein [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) Flag, das das Zielbetriebssystem für die Typbibliothek identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1ec88-109">[out] A [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="1ec88-110">Häufig verwendete Werte sind SYS_WIN32 und SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="1ec88-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="1ec88-111">[out] Die Hauptversionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="1ec88-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="1ec88-112">Z. B. für Version *x.y*, ist die Hauptversionsnummer *x*.</span><span class="sxs-lookup"><span data-stu-id="1ec88-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="1ec88-113">[out] Die Nebenversionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="1ec88-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="1ec88-114">Z. B. für Version *x.y*, ist die Nummer der Nebenversion *y*.</span><span class="sxs-lookup"><span data-stu-id="1ec88-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ec88-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ec88-115">Remarks</span></span>  
 <span data-ttu-id="1ec88-116">Die `GetTypeLibInfo` Funktion wird aufgerufen, indem Sie die [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="1ec88-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="1ec88-117">Dieses Tool generiert eine Typbibliothek, die die Typen in einer Assembly der common Language Runtime (CLR) beschreibt.</span><span class="sxs-lookup"><span data-stu-id="1ec88-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="1ec88-118">Wenn ein der Parameter null ist, gibt die Funktion ein `HRESULT` von `E_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="1ec88-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="1ec88-119">Andernfalls wird zurückgegeben `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="1ec88-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ec88-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1ec88-120">Requirements</span></span>  
 <span data-ttu-id="1ec88-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ec88-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ec88-122">**Header:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="1ec88-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="1ec88-123">**Bibliothek:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="1ec88-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="1ec88-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ec88-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ec88-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ec88-125">See Also</span></span>  
 [<span data-ttu-id="1ec88-126">Tlbexp-Hilfsfunktionen</span><span class="sxs-lookup"><span data-stu-id="1ec88-126">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="1ec88-127">[LoadTypeLibEx-Funktion](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)</span><span class="sxs-lookup"><span data-stu-id="1ec88-127">[LoadTypeLibEx Function](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)</span></span>
