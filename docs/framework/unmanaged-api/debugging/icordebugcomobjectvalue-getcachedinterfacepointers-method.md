---
title: ICorDebugComObjectValue::GetCachedInterfacePointers-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da0e62250dbef9be93ccee7020e23c3f83e85592
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223269"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="bff6c-102">ICorDebugComObjectValue::GetCachedInterfacePointers-Methode</span><span class="sxs-lookup"><span data-stu-id="bff6c-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="bff6c-103">Ruft den unformatierten Schnittstellenzeiger auf den aktuellen Runtime callable Wrapper (RCW) zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="bff6c-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bff6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bff6c-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bff6c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bff6c-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="bff6c-106">[in] Ein Wert, der angibt, ob nur die Methode zurückkehrt, [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Schnittstellen (`IInspectable` Schnittstellen) oder alle COM-Schnittstellen, die von den Runtime callable Wrapper (RCW) zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="bff6c-106">[in] A value that indicates whether the method will return only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="bff6c-107">[in] Die Anzahl der Objekte, deren Adressen sind, abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bff6c-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="bff6c-108">[out] Ein Zeiger auf die Anzahl der `CORDB_ADDRESS` Rückgabewerte, die tatsächlich `ptrs`.</span><span class="sxs-lookup"><span data-stu-id="bff6c-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="bff6c-109">Ein Zeiger auf die Startadresse eines Arrays von `CORDB_ADDRESS` zwischengespeicherte Werte, die die Adressen der Objekte der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="bff6c-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bff6c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bff6c-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bff6c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bff6c-111">Requirements</span></span>  
 <span data-ttu-id="bff6c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bff6c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bff6c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bff6c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bff6c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bff6c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bff6c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bff6c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bff6c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bff6c-116">See also</span></span>

- [<span data-ttu-id="bff6c-117">ICorDebugComObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bff6c-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="bff6c-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bff6c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
