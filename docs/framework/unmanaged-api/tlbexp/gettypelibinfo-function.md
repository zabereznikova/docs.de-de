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
ms.openlocfilehash: d12cbb66464baba4ee706ccb076764fbf025fc5f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148537"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="cbff1-102">GetTypeLibInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="cbff1-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="cbff1-103">Gibt Informationen über die angegebene Typbibliothek durch Untersuchen der [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) Struktur.</span><span class="sxs-lookup"><span data-stu-id="cbff1-103">Returns information about the specified type library by examining its [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbff1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbff1-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="cbff1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cbff1-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="cbff1-106">[in] Der Dateiname der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="cbff1-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="cbff1-107">[out] Die GUID der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="cbff1-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="cbff1-108">[out] Die Lokalisierungs-ID der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="cbff1-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="cbff1-109">[out] Ein [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) Flag, das das Zielbetriebssystem für die Typbibliothek identifiziert.</span><span class="sxs-lookup"><span data-stu-id="cbff1-109">[out] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="cbff1-110">Häufig verwendete Werte sind SYS_WIN32 und SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="cbff1-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="cbff1-111">[out] Die Hauptversionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="cbff1-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="cbff1-112">Z. B. für Version *x.y*, ist die Hauptversionsnummer *x*.</span><span class="sxs-lookup"><span data-stu-id="cbff1-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="cbff1-113">[out] Die Nebenversionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="cbff1-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="cbff1-114">Z. B. für Version *x.y*, ist die Nummer der Nebenversion *y*.</span><span class="sxs-lookup"><span data-stu-id="cbff1-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbff1-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cbff1-115">Remarks</span></span>  
 <span data-ttu-id="cbff1-116">Die `GetTypeLibInfo` Funktion wird aufgerufen, indem die [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="cbff1-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="cbff1-117">Dieses Tool generiert eine Typbibliothek, die die Typen in einer Assembly der common Language Runtime (CLR) beschreibt.</span><span class="sxs-lookup"><span data-stu-id="cbff1-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="cbff1-118">Wenn alle Parameter null ist, gibt die Funktion eine `HRESULT` von `E_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="cbff1-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="cbff1-119">Andernfalls wird `S_OK`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cbff1-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbff1-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cbff1-120">Requirements</span></span>  
 <span data-ttu-id="cbff1-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbff1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbff1-122">**Header:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="cbff1-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="cbff1-123">**Bibliothek:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="cbff1-123">**Library:** TlbRef.lib</span></span>  
  
 **<span data-ttu-id="cbff1-124">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="cbff1-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cbff1-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbff1-125">See also</span></span>

- [<span data-ttu-id="cbff1-126">Tlbexp-Hilfsfunktionen</span><span class="sxs-lookup"><span data-stu-id="cbff1-126">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="cbff1-127">LoadTypeLibEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="cbff1-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
