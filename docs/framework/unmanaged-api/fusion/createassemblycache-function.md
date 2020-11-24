---
title: CreateAssemblyCache-Funktion
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
ms.openlocfilehash: 3197c650b4f167e7a5043270797d2c4a62413d8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683198"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="0ad3d-102">CreateAssemblyCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="0ad3d-102">CreateAssemblyCache Function</span></span>

<span data-ttu-id="0ad3d-103">Ruft einen Zeiger auf eine neue [IAssemblyCache](iassemblycache-interface.md) -Instanz ab, die den globalen Assemblycache darstellt.</span><span class="sxs-lookup"><span data-stu-id="0ad3d-103">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ad3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ad3d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ad3d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ad3d-105">Parameters</span></span>  

 `ppAsmCache`  
 <span data-ttu-id="0ad3d-106">vorgenommen Der zurückgegebene `IAssemblyCache` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="0ad3d-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="0ad3d-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="0ad3d-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="0ad3d-108">`dwReserved` muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="0ad3d-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad3d-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0ad3d-109">Requirements</span></span>  

 <span data-ttu-id="0ad3d-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ad3d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad3d-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="0ad3d-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0ad3d-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0ad3d-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0ad3d-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad3d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad3d-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ad3d-114">See also</span></span>

- [<span data-ttu-id="0ad3d-115">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ad3d-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="0ad3d-116">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="0ad3d-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="0ad3d-117">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="0ad3d-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)
