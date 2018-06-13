---
title: ICorDebugGuidToTypeEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c156be3af49ac99f040360bda9f60f21a9ad66b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416217"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="86614-102">ICorDebugGuidToTypeEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="86614-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="86614-103">Ruft die angegebene Anzahl von [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Instanzen, die GUIDs für die Typinformationen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="86614-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86614-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="86614-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86614-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="86614-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="86614-106">[in] Die Anzahl der auf den Typ GUID Zuordnungsobjekte abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="86614-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="86614-107">[out] Ein Array von Zeigern, die jeweils auf eine [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) -Objekt, das ordnet eine [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID, um das zugehörige ICorDebugType-Objekt.</span><span class="sxs-lookup"><span data-stu-id="86614-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="86614-108">[out] Ein Zeiger auf die Anzahl der [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) tatsächlich zurückgegebenen Objekte `values`.</span><span class="sxs-lookup"><span data-stu-id="86614-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86614-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86614-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86614-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="86614-110">Requirements</span></span>  
 <span data-ttu-id="86614-111">**Plattformen:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86614-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="86614-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86614-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86614-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86614-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86614-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86614-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86614-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86614-115">See Also</span></span>  
 [<span data-ttu-id="86614-116">ICorDebugGuidToTypeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="86614-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 [<span data-ttu-id="86614-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="86614-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
