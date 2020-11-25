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
ms.openlocfilehash: cd24e672c65769586dc618c21503dbb344566974
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731812"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="190ce-102">ICorDebugManagedCallback::CreateProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="190ce-102">ICorDebugManagedCallback::CreateProcess Method</span></span>

<span data-ttu-id="190ce-103">Benachrichtigt den Debugger, wenn ein Prozess zum ersten Mal angefügt oder gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="190ce-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="190ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="190ce-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="190ce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="190ce-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="190ce-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, der angefügt oder gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="190ce-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="190ce-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="190ce-107">Remarks</span></span>  

 <span data-ttu-id="190ce-108">Diese Methode wird erst aufgerufen, wenn die Common Language Runtime initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="190ce-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="190ce-109">Die meisten [ICorDebug](icordebug-interface.md) -Methoden geben CORDBG_E_NOTREADY vor dem `CreateProcess` Rückruf zurück.</span><span class="sxs-lookup"><span data-stu-id="190ce-109">Most of the [ICorDebug](icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="190ce-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="190ce-110">Requirements</span></span>  

 <span data-ttu-id="190ce-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="190ce-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="190ce-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="190ce-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="190ce-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="190ce-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="190ce-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="190ce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="190ce-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="190ce-115">See also</span></span>

- [<span data-ttu-id="190ce-116">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="190ce-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
