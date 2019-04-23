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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084902"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="5ed2c-102">CreateAssemblyEnum-Funktion</span><span class="sxs-lookup"><span data-stu-id="5ed2c-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="5ed2c-103">Ruft einen Zeiger auf ein [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) -Instanz, die die Objekte in der Assembly mit dem angegebenen auflisten kann [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5ed2c-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ed2c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ed2c-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ed2c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ed2c-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="5ed2c-106">[out] Zeiger auf einen Speicherbereich, der den angeforderten enthält `IAssemblyEnum` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="5ed2c-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="5ed2c-108">`pUnkReserved` ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="5ed2c-109">[in] Die `IAssemblyName` der angeforderten Assembly.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="5ed2c-110">Dieser Name wird verwendet, um die Enumeration zu filtern.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="5ed2c-111">Es kann null, um alle Assemblys im globalen Assemblycache aufgelistet sein.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5ed2c-112">[in] Flags für das Verhalten des Enumerators geändert.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="5ed2c-113">Dieser Parameter enthält genau ein Bit aus dem [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="5ed2c-114">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="5ed2c-115">`pvReserved` ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ed2c-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ed2c-116">Remarks</span></span>  
 <span data-ttu-id="5ed2c-117">Die `dwFlags` Parameter enthält genau ein Bit aus dem `ASM_CACHE_FLAGS` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ed2c-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ed2c-118">Requirements</span></span>  
 <span data-ttu-id="5ed2c-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ed2c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ed2c-120">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="5ed2c-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5ed2c-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5ed2c-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ed2c-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ed2c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ed2c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ed2c-123">See also</span></span>

- [<span data-ttu-id="5ed2c-124">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ed2c-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
- [<span data-ttu-id="5ed2c-125">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ed2c-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="5ed2c-126">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="5ed2c-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
