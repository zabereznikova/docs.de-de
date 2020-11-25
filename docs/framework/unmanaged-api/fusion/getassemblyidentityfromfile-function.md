---
title: GetAssemblyIdentityFromFile-Funktion
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
ms.openlocfilehash: 9580dd3bc5a7279549e8deadac95d35a33da74f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724480"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="fe5f3-102">GetAssemblyIdentityFromFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="fe5f3-102">GetAssemblyIdentityFromFile Function</span></span>

<span data-ttu-id="fe5f3-103">Ruft einen Zeiger auf ein- `IUnknown` Objekt mit dem angegebenen `IID` in der Assembly am angegebenen Dateipfad ab.</span><span class="sxs-lookup"><span data-stu-id="fe5f3-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe5f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe5f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe5f3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fe5f3-105">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="fe5f3-106">in Ein gültiger Pfad zur angeforderten Assembly.</span><span class="sxs-lookup"><span data-stu-id="fe5f3-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="fe5f3-107">in Der der- `IID` Schnittstelle, die zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe5f3-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="fe5f3-108">vorgenommen Der zurückgegebene Schnittstellen Zeiger.</span><span class="sxs-lookup"><span data-stu-id="fe5f3-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe5f3-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fe5f3-109">Requirements</span></span>  

 <span data-ttu-id="fe5f3-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe5f3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe5f3-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fe5f3-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fe5f3-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe5f3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe5f3-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe5f3-113">See also</span></span>

- [<span data-ttu-id="fe5f3-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="fe5f3-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="fe5f3-115">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="fe5f3-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
