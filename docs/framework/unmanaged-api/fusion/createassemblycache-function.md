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
ms.openlocfilehash: 5ef100680328e9ad6261bb9188d7509efa9ab479
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108866"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="e81a4-102">CreateAssemblyCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="e81a4-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="e81a4-103">Ruft einen Zeiger auf eine neue [IAssemblyCache](iassemblycache-interface.md) -Instanz ab, die den globalen Assemblycache darstellt.</span><span class="sxs-lookup"><span data-stu-id="e81a4-103">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e81a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e81a4-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e81a4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e81a4-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="e81a4-106">vorgenommen Der zurückgegebene `IAssemblyCache` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="e81a4-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="e81a4-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="e81a4-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e81a4-108">`dwReserved` muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="e81a4-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e81a4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e81a4-109">Requirements</span></span>  
 <span data-ttu-id="e81a4-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e81a4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e81a4-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e81a4-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e81a4-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e81a4-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e81a4-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e81a4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e81a4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e81a4-114">See also</span></span>

- [<span data-ttu-id="e81a4-115">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e81a4-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="e81a4-116">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="e81a4-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="e81a4-117">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="e81a4-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)
