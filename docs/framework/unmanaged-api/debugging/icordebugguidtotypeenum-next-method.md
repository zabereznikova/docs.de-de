---
title: ICorDebugGuidToTypeEnum::Next-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGuidToTypeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3bcfbcfb85fc5eb1d58142af4e7d825162e9861b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="fcd2d-102">ICorDebugGuidToTypeEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="fcd2d-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="fcd2d-103">Ruft die angegebene Anzahl von [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Instanzen, die GUIDs für die Typinformationen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fcd2d-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcd2d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcd2d-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fcd2d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fcd2d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="fcd2d-106">[in] Die Anzahl der auf den Typ GUID Zuordnungsobjekte abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fcd2d-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="fcd2d-107">[out] Ein Array von Zeigern, die jeweils auf eine [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) -Objekt, das ordnet eine [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID, um das zugehörige ICorDebugType-Objekt.</span><span class="sxs-lookup"><span data-stu-id="fcd2d-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="fcd2d-108">[out] Ein Zeiger auf die Anzahl der [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) tatsächlich zurückgegebenen Objekte `values`.</span><span class="sxs-lookup"><span data-stu-id="fcd2d-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcd2d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcd2d-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcd2d-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fcd2d-110">Requirements</span></span>  
 <span data-ttu-id="fcd2d-111">**Plattformen:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd2d-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="fcd2d-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcd2d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcd2d-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcd2d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcd2d-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd2d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd2d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcd2d-115">See Also</span></span>  
 [<span data-ttu-id="fcd2d-116">ICorDebugGuidToTypeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcd2d-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 [<span data-ttu-id="fcd2d-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fcd2d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
