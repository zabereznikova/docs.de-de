---
title: ICorDebugManagedCallback::CreateProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
ms.openlocfilehash: 0e9ed8054711297173e880c9eecb12c3f5bd0a68
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207135"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="31f8a-102">ICorDebugManagedCallback::CreateProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="31f8a-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="31f8a-103">Benachrichtigt den Debugger, wenn ein Prozess zum ersten Mal angefügt oder gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="31f8a-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31f8a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31f8a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31f8a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="31f8a-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="31f8a-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, der angefügt oder gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="31f8a-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31f8a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31f8a-107">Remarks</span></span>  
 <span data-ttu-id="31f8a-108">Diese Methode wird erst aufgerufen, wenn die Common Language Runtime initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="31f8a-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="31f8a-109">Die meisten [ICorDebug](icordebug-interface.md) -Methoden geben CORDBG_E_NOTREADY vor dem `CreateProcess` Rückruf zurück.</span><span class="sxs-lookup"><span data-stu-id="31f8a-109">Most of the [ICorDebug](icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31f8a-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="31f8a-110">Requirements</span></span>  
 <span data-ttu-id="31f8a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31f8a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31f8a-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31f8a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31f8a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31f8a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31f8a-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31f8a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f8a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31f8a-115">See also</span></span>

- [<span data-ttu-id="31f8a-116">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31f8a-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
