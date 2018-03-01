---
title: ICorDebugThread4::GetCurrentCustomDebuggerNotification-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a408e011a2eff6a10a6ce1db03a6282c45044a37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="2f901-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="2f901-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>
<span data-ttu-id="2f901-103">Ruft die aktuellen [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) Objekt für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="2f901-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f901-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f901-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCustomDebuggerNotification(  
    [out] ICorDebugValue **ppNotificationObject  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f901-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2f901-105">Parameters</span></span>  
 `ppNOtificationObject`  
 <span data-ttu-id="2f901-106">[out] Ein Zeiger auf die aktuelle `ICorDebugManagedCallback3::CustomNotification` Objekt für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="2f901-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f901-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f901-107">Remarks</span></span>  
 <span data-ttu-id="2f901-108">Der Wert der `ppNotificationObject` ist null, wenn die Methode nicht heraus aufgerufen wird ein `ICorDebugManagedCallback3::CustomNotification` Rückruf, oder wenn keine aktuelle Benachrichtigungsobjekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2f901-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f901-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f901-109">Requirements</span></span>  
 <span data-ttu-id="2f901-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f901-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f901-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f901-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f901-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f901-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f901-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f901-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f901-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f901-114">See Also</span></span>  
 [<span data-ttu-id="2f901-115">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f901-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="2f901-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2f901-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="2f901-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2f901-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
