---
title: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 861d2ad5f9ce0fcc11ea7b1743cd369235cbd878
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="2cc81-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack-Methode</span><span class="sxs-lookup"><span data-stu-id="2cc81-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="2cc81-103">Ruft einen Enumerator ab, um die Aufrufliste, die in einem Ausnahmeobjekt eingebettet.</span><span class="sxs-lookup"><span data-stu-id="2cc81-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cc81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cc81-104">Syntax</span></span>  
  
```  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cc81-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2cc81-105">Parameters</span></span>  
 <span data-ttu-id="2cc81-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="2cc81-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="2cc81-107">[out] Ein Zeiger auf die Adresse des ein [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) Schnittstellenobjekts, das einen Stapel-Trace-Enumerator für die einem verwalteten Ausnahmeobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="2cc81-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cc81-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cc81-108">Remarks</span></span>  
 <span data-ttu-id="2cc81-109">Wenn keine Aufruflisteninformationen verfügbar ist, gibt die Methode `S_OK`, und [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) ist ein gültiger Enumerator mit einer Länge von 0.</span><span class="sxs-lookup"><span data-stu-id="2cc81-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="2cc81-110">Wenn die Methode nicht Stapelüberwachungsinformationen abrufen kann, ist der Rückgabewert `E_FAIL` und kein Enumerator wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2cc81-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="2cc81-111">Die [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) -Objekt ist verantwortlich für die Stack-Ablaufverfolgungsdaten aus Decodieren der `_stackTrace` Feld des Ausnahmeobjekts.</span><span class="sxs-lookup"><span data-stu-id="2cc81-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cc81-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2cc81-112">Requirements</span></span>  
 <span data-ttu-id="2cc81-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cc81-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cc81-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cc81-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cc81-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cc81-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cc81-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cc81-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc81-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cc81-117">See Also</span></span>  
 [<span data-ttu-id="2cc81-118">ICorDebugExceptionObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cc81-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 [<span data-ttu-id="2cc81-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2cc81-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
