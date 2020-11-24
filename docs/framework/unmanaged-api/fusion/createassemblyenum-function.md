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
ms.openlocfilehash: b7e3696121475885f5061bd96eb6905d7ccae734
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683172"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="902d7-102">CreateAssemblyEnum-Funktion</span><span class="sxs-lookup"><span data-stu-id="902d7-102">CreateAssemblyEnum Function</span></span>

<span data-ttu-id="902d7-103">Ruft einen Zeiger auf eine [IAssemblyEnum](iassemblyenum-interface.md) -Instanz ab, die die Objekte in der Assembly mit dem angegebenen [IAssemblyName](iassemblyname-interface.md)auflisten kann.</span><span class="sxs-lookup"><span data-stu-id="902d7-103">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="902d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="902d7-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="902d7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="902d7-105">Parameters</span></span>  

 `pEnum`  
 <span data-ttu-id="902d7-106">vorgenommen Ein Zeiger auf einen Speicherort, der den angeforderten `IAssemblyEnum` Zeiger enthält.</span><span class="sxs-lookup"><span data-stu-id="902d7-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="902d7-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="902d7-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="902d7-108">`pUnkReserved` muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="902d7-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="902d7-109">in Der der `IAssemblyName` angeforderten Assembly.</span><span class="sxs-lookup"><span data-stu-id="902d7-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="902d7-110">Dieser Name wird verwendet, um die-Enumeration zu filtern.</span><span class="sxs-lookup"><span data-stu-id="902d7-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="902d7-111">Es kann NULL sein, um alle Assemblys im globalen Assemblycache aufzuzählen.</span><span class="sxs-lookup"><span data-stu-id="902d7-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="902d7-112">in Flags zum Ändern des Verhaltens des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="902d7-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="902d7-113">Dieser Parameter enthält genau ein Bit aus der [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="902d7-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="902d7-114">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="902d7-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="902d7-115">`pvReserved` muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="902d7-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="902d7-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="902d7-116">Remarks</span></span>  

 <span data-ttu-id="902d7-117">Der- `dwFlags` Parameter enthält genau ein Bit aus der- `ASM_CACHE_FLAGS` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="902d7-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="902d7-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="902d7-118">Requirements</span></span>  

 <span data-ttu-id="902d7-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="902d7-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="902d7-120">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="902d7-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="902d7-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="902d7-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="902d7-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="902d7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="902d7-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="902d7-123">See also</span></span>

- [<span data-ttu-id="902d7-124">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="902d7-124">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="902d7-125">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="902d7-125">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="902d7-126">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="902d7-126">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
