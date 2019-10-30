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
ms.openlocfilehash: e64a0512e05965b3da2e7486e986ee34ca8a20d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104305"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="bd0c5-102">GetTypeLibInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="bd0c5-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="bd0c5-103">Gibt Informationen über die angegebene Typbibliothek zurück, indem die [TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) -Struktur überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-103">Returns information about the specified type library by examining its [TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd0c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd0c5-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="bd0c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd0c5-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="bd0c5-106">in Der Dateiname der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="bd0c5-107">vorgenommen Die GUID der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="bd0c5-108">vorgenommen Die Lokalisierungs-ID der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="bd0c5-109">vorgenommen Ein [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) -Flag, das das Ziel Betriebssystem für die Typbibliothek identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-109">[out] A [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="bd0c5-110">Allgemeine Werte sind SYS_WIN32 und SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="bd0c5-111">vorgenommen Die Hauptversionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="bd0c5-112">Bei Version *x. y*lautet die Hauptversionsnummer z. b. *x*.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="bd0c5-113">vorgenommen Die neben Versionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="bd0c5-114">Beispielsweise ist für Version *x. y*die neben Versionsnummer *y*.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd0c5-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd0c5-115">Remarks</span></span>  
 <span data-ttu-id="bd0c5-116">Die `GetTypeLibInfo`-Funktion wird von [Tlbexp. exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md)aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="bd0c5-117">Dieses Tool generiert eine Typbibliothek, die die Typen in einer Common Language Runtime-Assembly (CLR) beschreibt.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="bd0c5-118">Wenn ein beliebiger Parameter NULL ist, gibt die Funktion eine `HRESULT` `E_POINTER`zurück.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="bd0c5-119">Andernfalls wird `S_OK` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bd0c5-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd0c5-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd0c5-120">Requirements</span></span>  
 <span data-ttu-id="bd0c5-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd0c5-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd0c5-122">**Header:** TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="bd0c5-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="bd0c5-123">**Bibliothek:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="bd0c5-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="bd0c5-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd0c5-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd0c5-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd0c5-125">See also</span></span>

- [<span data-ttu-id="bd0c5-126">Tlbexp-Hilfsfunktionen</span><span class="sxs-lookup"><span data-stu-id="bd0c5-126">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="bd0c5-127">LoadTypeLibEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="bd0c5-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
