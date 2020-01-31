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
ms.openlocfilehash: 9d1d6d2f506086dd3204053b0b635da2e7cdc87e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783956"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="8ac9b-102">ICorDebugComObjectValue::GetCachedInterfacePointers-Methode</span><span class="sxs-lookup"><span data-stu-id="8ac9b-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="8ac9b-103">Ruft die unformatierten Schnittstellen Zeiger ab, die auf dem aktuellen Runtime Callable Wrapper (RCW) zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8ac9b-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ac9b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ac9b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ac9b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8ac9b-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="8ac9b-106">in Ein Wert, der angibt, ob die Methode nur Windows-Runtime Schnittstellen (`IInspectable` Schnittstellen) oder alle COM-Schnittstellen zurückgibt, die vom Runtime Callable Wrapper (RCW) zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8ac9b-106">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="8ac9b-107">in Die Anzahl der Objekte, deren Adressen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8ac9b-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8ac9b-108">vorgenommen Ein Zeiger auf die Anzahl der `CORDB_ADDRESS` Werte, die tatsächlich in `ptrs`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8ac9b-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="8ac9b-109">Ein Zeiger auf die Startadresse eines Arrays von `CORDB_ADDRESS`-Werten, die die Adressen von zwischengespeicherten Schnittstellen Objekten enthalten.</span><span class="sxs-lookup"><span data-stu-id="8ac9b-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ac9b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ac9b-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ac9b-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ac9b-111">Requirements</span></span>  
 <span data-ttu-id="8ac9b-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ac9b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ac9b-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ac9b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ac9b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ac9b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ac9b-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ac9b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ac9b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ac9b-116">See also</span></span>

- [<span data-ttu-id="8ac9b-117">ICorDebugComObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ac9b-117">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="8ac9b-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8ac9b-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
