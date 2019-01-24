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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: feb8e5c56ee6ea766cd5f1d10af42699777db453
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654887"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="ad8b3-102">GetAssemblyIdentityFromFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="ad8b3-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="ad8b3-103">Ruft einen Zeiger auf ein `IUnknown` Objekt mit dem angegebenen `IID` in der Assembly im angegebenen Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="ad8b3-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad8b3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad8b3-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad8b3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ad8b3-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="ad8b3-106">[in] Ein gültiger Pfad auf die angeforderte Assembly.</span><span class="sxs-lookup"><span data-stu-id="ad8b3-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="ad8b3-107">[in] Die `IID` der zurückzugebenden Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ad8b3-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="ad8b3-108">[out] Der zurückgegebene Schnittstellenzeiger.</span><span class="sxs-lookup"><span data-stu-id="ad8b3-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad8b3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ad8b3-109">Requirements</span></span>  
 <span data-ttu-id="ad8b3-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad8b3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad8b3-111">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ad8b3-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ad8b3-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad8b3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad8b3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad8b3-113">See also</span></span>
- [<span data-ttu-id="ad8b3-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="ad8b3-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="ad8b3-115">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="ad8b3-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
