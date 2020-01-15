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
ms.openlocfilehash: 4f05eb2e6ef31cf1993a623c38bb177f7e3c297e
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935653"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="ba5b1-102">GetTypeLibInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="ba5b1-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="ba5b1-103">Gibt Informationen über die angegebene Typbibliothek zurück, indem die [TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) -Struktur überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-103">Returns information about the specified type library by examining its [TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba5b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba5b1-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ba5b1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ba5b1-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="ba5b1-106">in Der Dateiname der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="ba5b1-107">vorgenommen Die GUID der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="ba5b1-108">vorgenommen Die Lokalisierungs-ID der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="ba5b1-109">vorgenommen Ein [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) -Flag, das das Ziel Betriebssystem für die Typbibliothek identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-109">[out] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="ba5b1-110">Allgemeine Werte sind SYS_WIN32 und SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="ba5b1-111">vorgenommen Die Hauptversionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="ba5b1-112">Bei Version *x. y*lautet die Hauptversionsnummer z. b. *x*.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="ba5b1-113">vorgenommen Die neben Versionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="ba5b1-114">Beispielsweise ist für Version *x. y*die neben Versionsnummer *y*.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba5b1-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba5b1-115">Remarks</span></span>  
 <span data-ttu-id="ba5b1-116">Die `GetTypeLibInfo`-Funktion wird von [Tlbexp. exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md)aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="ba5b1-117">Dieses Tool generiert eine Typbibliothek, die die Typen in einer Common Language Runtime-Assembly (CLR) beschreibt.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="ba5b1-118">Wenn ein beliebiger Parameter NULL ist, gibt die Funktion eine `HRESULT` `E_POINTER`zurück.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="ba5b1-119">Andernfalls wird `S_OK` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba5b1-120">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ba5b1-120">Requirements</span></span>  
 <span data-ttu-id="ba5b1-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba5b1-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba5b1-122">**Header:** TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="ba5b1-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="ba5b1-123">**Bibliothek:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="ba5b1-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="ba5b1-124">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba5b1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba5b1-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba5b1-125">See also</span></span>

- [<span data-ttu-id="ba5b1-126">Tlbexp-Hilfsfunktionen</span><span class="sxs-lookup"><span data-stu-id="ba5b1-126">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="ba5b1-127">LoadTypeLibEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="ba5b1-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
