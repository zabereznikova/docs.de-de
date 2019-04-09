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
ms.openlocfilehash: f48c142b2b3742d01a8f796f11d5c9174529a041
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105818"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="ede8c-102">ICorDebugGuidToTypeEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="ede8c-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="ede8c-103">Ruft die angegebene Anzahl von [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Instanzen, die GUIDs, die Typinformationen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="ede8c-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ede8c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ede8c-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ede8c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ede8c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ede8c-106">[in] Die Anzahl der auf den Typ GUID Zuordnen von Objekten abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ede8c-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="ede8c-107">[out] Ein Array von Zeigern, die jeweils auf eine [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) -Objekt, das ordnet eine [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID, die das zugehörige ICorDebugType-Objekt.</span><span class="sxs-lookup"><span data-stu-id="ede8c-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ede8c-108">[out] Ein Zeiger auf die Anzahl der [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) tatsächlich zurückgegebenen Objekte `values`.</span><span class="sxs-lookup"><span data-stu-id="ede8c-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ede8c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ede8c-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ede8c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ede8c-110">Requirements</span></span>  
 **<span data-ttu-id="ede8c-111">Plattformen:</span><span class="sxs-lookup"><span data-stu-id="ede8c-111">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="ede8c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ede8c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ede8c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ede8c-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ede8c-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ede8c-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ede8c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ede8c-115">See also</span></span>

- [<span data-ttu-id="ede8c-116">ICorDebugGuidToTypeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ede8c-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="ede8c-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ede8c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
