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
ms.openlocfilehash: 101151469e2eece20afe289c9d95387ce6dc7c6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672122"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="41c4e-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack-Methode</span><span class="sxs-lookup"><span data-stu-id="41c4e-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>

<span data-ttu-id="41c4e-103">Ruft einen Enumerator für die in einem Ausnahme Objekt eingebettete-Aufzählung ab.</span><span class="sxs-lookup"><span data-stu-id="41c4e-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41c4e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41c4e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41c4e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="41c4e-105">Parameters</span></span>  

 <span data-ttu-id="41c4e-106">ppcallstackaufumum</span><span class="sxs-lookup"><span data-stu-id="41c4e-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="41c4e-107">vorgenommen Ein Zeiger auf die Adresse eines [icordebugexceptionobjectcallstackenum](icordebugexceptionobjectcallstackenum-interface.md) -Schnittstellen Objekts, bei dem es sich um einen Stapel Verfolgungs Enumerator für ein verwaltetes Ausnahme Objekt handelt.</span><span class="sxs-lookup"><span data-stu-id="41c4e-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41c4e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41c4e-108">Remarks</span></span>  

 <span data-ttu-id="41c4e-109">Wenn keine Aufruf Listen Informationen verfügbar sind, gibt die Methode zurück `S_OK` , und [icordebugexceptionobjectcallstackenum](icordebugexceptionobjectcallstackenum-interface.md) ist ein gültiger Enumerator mit einer Länge von 0.</span><span class="sxs-lookup"><span data-stu-id="41c4e-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="41c4e-110">Wenn die Methode keine Stapel Überwachungsinformationen abrufen kann, ist der Rückgabewert, `E_FAIL` und es wird kein Enumerator zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="41c4e-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="41c4e-111">Das [icordebugexceptionobjectcallstackenum](icordebugexceptionobjectcallstackenum-interface.md) -Objekt ist verantwortlich für das Decodieren der Stapel Verfolgungs Daten aus dem- `_stackTrace` Feld des Ausnahme Objekts.</span><span class="sxs-lookup"><span data-stu-id="41c4e-111">The [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41c4e-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="41c4e-112">Requirements</span></span>  

 <span data-ttu-id="41c4e-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41c4e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41c4e-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41c4e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41c4e-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41c4e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41c4e-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41c4e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c4e-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41c4e-117">See also</span></span>

- [<span data-ttu-id="41c4e-118">ICorDebugExceptionObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41c4e-118">ICorDebugExceptionObjectValue Interface</span></span>](icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="41c4e-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="41c4e-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
