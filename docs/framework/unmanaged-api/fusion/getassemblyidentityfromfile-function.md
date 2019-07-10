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
ms.openlocfilehash: 581c675cfb69503e6366471a469ffed1a2d13b1a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745231"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="5c5c3-102">GetAssemblyIdentityFromFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="5c5c3-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="5c5c3-103">Ruft einen Zeiger auf ein `IUnknown` Objekt mit dem angegebenen `IID` in der Assembly im angegebenen Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="5c5c3-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c5c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c5c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c5c3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5c5c3-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="5c5c3-106">[in] Ein gültiger Pfad auf die angeforderte Assembly.</span><span class="sxs-lookup"><span data-stu-id="5c5c3-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="5c5c3-107">[in] Die `IID` der zurückzugebenden Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5c5c3-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="5c5c3-108">[out] Der zurückgegebene Schnittstellenzeiger.</span><span class="sxs-lookup"><span data-stu-id="5c5c3-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c5c3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5c5c3-109">Requirements</span></span>  
 <span data-ttu-id="5c5c3-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c5c3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c5c3-111">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="5c5c3-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5c5c3-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c5c3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c5c3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c5c3-113">See also</span></span>

- [<span data-ttu-id="5c5c3-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="5c5c3-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="5c5c3-115">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="5c5c3-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
