---
title: CreateAssemblyEnum-Funktion
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0c5dabd4145098941e9e8a7e36fa3215c26713d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084902"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="e8d64-102">CreateAssemblyEnum-Funktion</span><span class="sxs-lookup"><span data-stu-id="e8d64-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="e8d64-103">Ruft einen Zeiger auf ein [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) -Instanz, die die Objekte in der Assembly mit dem angegebenen auflisten kann [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e8d64-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8d64-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8d64-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8d64-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8d64-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="e8d64-106">[out] Zeiger auf einen Speicherbereich, der den angeforderten enthält `IAssemblyEnum` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="e8d64-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="e8d64-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8d64-107">[in] Reserved for future extensibility.</span></span> `pUnkReserved` <span data-ttu-id="e8d64-108">ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="e8d64-108">must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="e8d64-109">[in] Die `IAssemblyName` der angeforderten Assembly.</span><span class="sxs-lookup"><span data-stu-id="e8d64-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="e8d64-110">Dieser Name wird verwendet, um die Enumeration zu filtern.</span><span class="sxs-lookup"><span data-stu-id="e8d64-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="e8d64-111">Es kann null, um alle Assemblys im globalen Assemblycache aufgelistet sein.</span><span class="sxs-lookup"><span data-stu-id="e8d64-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e8d64-112">[in] Flags für das Verhalten des Enumerators geändert.</span><span class="sxs-lookup"><span data-stu-id="e8d64-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="e8d64-113">Dieser Parameter enthält genau ein Bit aus dem [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e8d64-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="e8d64-114">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8d64-114">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="e8d64-115">ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="e8d64-115">must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8d64-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8d64-116">Remarks</span></span>  
 <span data-ttu-id="e8d64-117">Die `dwFlags` Parameter enthält genau ein Bit aus dem `ASM_CACHE_FLAGS` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e8d64-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8d64-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8d64-118">Requirements</span></span>  
 <span data-ttu-id="e8d64-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8d64-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8d64-120">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e8d64-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e8d64-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e8d64-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e8d64-122">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e8d64-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e8d64-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8d64-123">See also</span></span>

- [<span data-ttu-id="e8d64-124">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8d64-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
- [<span data-ttu-id="e8d64-125">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8d64-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="e8d64-126">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="e8d64-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
