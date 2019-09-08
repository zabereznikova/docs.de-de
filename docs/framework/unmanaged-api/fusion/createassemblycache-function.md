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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c855d6f85c3cbfa6d81a1fbce3ef5b83abb3f583
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795411"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="29257-102">CreateAssemblyCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="29257-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="29257-103">Ruft einen Zeiger auf eine neue [IAssemblyCache](iassemblycache-interface.md) -Instanz ab, die den globalen Assemblycache darstellt.</span><span class="sxs-lookup"><span data-stu-id="29257-103">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29257-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="29257-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="29257-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="29257-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="29257-106">vorgenommen Der zurück `IAssemblyCache` gegebene Zeiger.</span><span class="sxs-lookup"><span data-stu-id="29257-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="29257-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="29257-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="29257-108">`dwReserved`muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="29257-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29257-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="29257-109">Requirements</span></span>  
 <span data-ttu-id="29257-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29257-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29257-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="29257-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="29257-112">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="29257-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="29257-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29257-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29257-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29257-114">See also</span></span>

- [<span data-ttu-id="29257-115">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29257-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="29257-116">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="29257-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="29257-117">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="29257-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)
