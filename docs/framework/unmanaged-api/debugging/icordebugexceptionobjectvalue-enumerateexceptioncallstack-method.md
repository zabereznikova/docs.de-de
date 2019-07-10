---
title: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a58a62dbcd69d1847ab5a0b0109fe4eea53a4f3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754224"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="b60a2-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack-Methode</span><span class="sxs-lookup"><span data-stu-id="b60a2-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="b60a2-103">Ruft einen Enumerator ab, um die Aufrufliste, die in einem Ausnahmeobjekt eingebettet.</span><span class="sxs-lookup"><span data-stu-id="b60a2-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b60a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b60a2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b60a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b60a2-105">Parameters</span></span>  
 <span data-ttu-id="b60a2-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="b60a2-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="b60a2-107">[out] Ein Zeiger auf die Adresse einer [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) Schnittstellenobjekts, das ein Stapel-Trace-Enumerator für ein verwaltetes Exception-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="b60a2-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b60a2-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b60a2-108">Remarks</span></span>  
 <span data-ttu-id="b60a2-109">Wenn keine Informationen in der Aufrufliste verfügbar ist, gibt die Methode `S_OK`, und [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) ist ein gültiger Enumerator mit einer Länge von 0.</span><span class="sxs-lookup"><span data-stu-id="b60a2-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="b60a2-110">Wenn die Methode kann nicht zum Abrufen von Informationen der ausnahmestapelüberwachung ist, wird der Rückgabewert ist `E_FAIL` und kein Enumerator zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b60a2-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="b60a2-111">Die [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) -Objekt ist verantwortlich für das Decodieren von Daten der stapelüberwachung aus der `_stackTrace` Feld des Ausnahmeobjekts.</span><span class="sxs-lookup"><span data-stu-id="b60a2-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b60a2-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b60a2-112">Requirements</span></span>  
 <span data-ttu-id="b60a2-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b60a2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b60a2-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b60a2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b60a2-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b60a2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b60a2-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b60a2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60a2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b60a2-117">See also</span></span>

- [<span data-ttu-id="b60a2-118">ICorDebugExceptionObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b60a2-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="b60a2-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b60a2-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
