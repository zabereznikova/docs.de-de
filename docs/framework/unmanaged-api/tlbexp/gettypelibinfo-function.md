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
ms.openlocfilehash: d8ea7df9396e9199d04ad5609daa9d2b01761f36
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798892"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="9a328-102">GetTypeLibInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="9a328-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="9a328-103">Gibt Informationen über die angegebene Typbibliothek zurück, indem die [TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) -Struktur überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="9a328-103">Returns information about the specified type library by examining its [TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a328-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a328-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a328-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a328-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="9a328-106">in Der Dateiname der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="9a328-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="9a328-107">vorgenommen Die GUID der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="9a328-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="9a328-108">vorgenommen Die Lokalisierungs-ID der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="9a328-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="9a328-109">vorgenommen Ein [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) -Flag, das das Ziel Betriebssystem für die Typbibliothek identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9a328-109">[out] A [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="9a328-110">Allgemeine Werte sind SYS_WIN32 und SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="9a328-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="9a328-111">vorgenommen Die Hauptversionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="9a328-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="9a328-112">Bei Version *x. y*lautet die Hauptversionsnummer z. b. *x*.</span><span class="sxs-lookup"><span data-stu-id="9a328-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="9a328-113">vorgenommen Die neben Versionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="9a328-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="9a328-114">Beispielsweise ist für Version *x. y*die neben Versionsnummer *y*.</span><span class="sxs-lookup"><span data-stu-id="9a328-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a328-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a328-115">Remarks</span></span>  
 <span data-ttu-id="9a328-116">Die `GetTypeLibInfo` -Funktion wird von [Tlbexp. exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md)aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9a328-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="9a328-117">Dieses Tool generiert eine Typbibliothek, die die Typen in einer Common Language Runtime-Assembly (CLR) beschreibt.</span><span class="sxs-lookup"><span data-stu-id="9a328-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="9a328-118">Wenn ein beliebiger Parameter NULL ist, gibt die `HRESULT` Funktion `E_POINTER`einen von zurück.</span><span class="sxs-lookup"><span data-stu-id="9a328-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="9a328-119">Andernfalls wird `S_OK`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9a328-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a328-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a328-120">Requirements</span></span>  
 <span data-ttu-id="9a328-121">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a328-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a328-122">**Header:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="9a328-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="9a328-123">**Fern** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="9a328-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="9a328-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a328-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a328-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a328-125">See also</span></span>

- [<span data-ttu-id="9a328-126">Tlbexp-Hilfsfunktionen</span><span class="sxs-lookup"><span data-stu-id="9a328-126">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="9a328-127">LoadTypeLibEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="9a328-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
