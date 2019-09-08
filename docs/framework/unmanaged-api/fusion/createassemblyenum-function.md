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
ms.openlocfilehash: 1db72c44b53b5abff9aee35094abc1e0e577fad4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795384"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="d50ba-102">CreateAssemblyEnum-Funktion</span><span class="sxs-lookup"><span data-stu-id="d50ba-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="d50ba-103">Ruft einen Zeiger auf eine [IAssemblyEnum](iassemblyenum-interface.md) -Instanz ab, die die Objekte in der Assembly mit dem angegebenen [IAssemblyName](iassemblyname-interface.md)auflisten kann.</span><span class="sxs-lookup"><span data-stu-id="d50ba-103">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d50ba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d50ba-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d50ba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d50ba-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="d50ba-106">vorgenommen Ein Zeiger auf einen Speicherort, der den `IAssemblyEnum` angeforderten Zeiger enthält.</span><span class="sxs-lookup"><span data-stu-id="d50ba-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="d50ba-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="d50ba-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="d50ba-108">`pUnkReserved`muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="d50ba-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="d50ba-109">in Der `IAssemblyName` der angeforderten Assembly.</span><span class="sxs-lookup"><span data-stu-id="d50ba-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="d50ba-110">Dieser Name wird verwendet, um die-Enumeration zu filtern.</span><span class="sxs-lookup"><span data-stu-id="d50ba-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="d50ba-111">Es kann NULL sein, um alle Assemblys im globalen Assemblycache aufzuzählen.</span><span class="sxs-lookup"><span data-stu-id="d50ba-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d50ba-112">in Flags zum Ändern des Verhaltens des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="d50ba-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="d50ba-113">Dieser Parameter enthält genau ein Bit aus der [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="d50ba-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="d50ba-114">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="d50ba-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="d50ba-115">`pvReserved`muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="d50ba-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d50ba-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d50ba-116">Remarks</span></span>  
 <span data-ttu-id="d50ba-117">Der `dwFlags` -Parameter enthält genau ein Bit aus `ASM_CACHE_FLAGS` der-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="d50ba-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d50ba-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d50ba-118">Requirements</span></span>  
 <span data-ttu-id="d50ba-119">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d50ba-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d50ba-120">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d50ba-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d50ba-121">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d50ba-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d50ba-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d50ba-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d50ba-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d50ba-123">See also</span></span>

- [<span data-ttu-id="d50ba-124">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d50ba-124">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="d50ba-125">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d50ba-125">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="d50ba-126">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="d50ba-126">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
