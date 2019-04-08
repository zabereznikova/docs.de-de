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
ms.openlocfilehash: db0e794953578fccd08428b730b3d7951e13bee3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074078"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="a158f-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack-Methode</span><span class="sxs-lookup"><span data-stu-id="a158f-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="a158f-103">Ruft einen Enumerator ab, um die Aufrufliste, die in einem Ausnahmeobjekt eingebettet.</span><span class="sxs-lookup"><span data-stu-id="a158f-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a158f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a158f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a158f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a158f-105">Parameters</span></span>  
 <span data-ttu-id="a158f-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="a158f-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="a158f-107">[out] Ein Zeiger auf die Adresse einer [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) Schnittstellenobjekts, das ein Stapel-Trace-Enumerator für ein verwaltetes Exception-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="a158f-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a158f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a158f-108">Remarks</span></span>  
 <span data-ttu-id="a158f-109">Wenn keine Informationen in der Aufrufliste verfügbar ist, gibt die Methode `S_OK`, und [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) ist ein gültiger Enumerator mit einer Länge von 0.</span><span class="sxs-lookup"><span data-stu-id="a158f-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="a158f-110">Wenn die Methode kann nicht zum Abrufen von Informationen der ausnahmestapelüberwachung ist, wird der Rückgabewert ist `E_FAIL` und kein Enumerator zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a158f-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="a158f-111">Die [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) -Objekt ist verantwortlich für das Decodieren von Daten der stapelüberwachung aus der `_stackTrace` Feld des Ausnahmeobjekts.</span><span class="sxs-lookup"><span data-stu-id="a158f-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a158f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a158f-112">Requirements</span></span>  
 <span data-ttu-id="a158f-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a158f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a158f-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a158f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a158f-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a158f-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a158f-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a158f-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a158f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a158f-117">See also</span></span>

- [<span data-ttu-id="a158f-118">ICorDebugExceptionObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a158f-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="a158f-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a158f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
