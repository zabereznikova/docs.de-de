---
title: ICorDebugThread4::GetCurrentCustomDebuggerNotification-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f626ff6e562bd9bc94440f31e9470a45cc32cfbd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216326"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="f0d20-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="f0d20-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="f0d20-103">Ruft die aktuelle [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) Objekt für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="f0d20-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="f0d20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0d20-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="f0d20-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0d20-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="f0d20-106">[out] Ein Zeiger auf die aktuelle `ICorDebugManagedCallback3::CustomNotification` Objekt für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="f0d20-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0d20-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0d20-107">Remarks</span></span>

<span data-ttu-id="f0d20-108">Der Wert des `ppNotificationObject` ist null, wenn die Methode nicht, innerhalb aufgerufen wird einer `ICorDebugManagedCallback3::CustomNotification` Rückruf, oder wenn keine aktuelle Benachrichtigungsobjekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f0d20-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0d20-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0d20-109">Requirements</span></span>

<span data-ttu-id="f0d20-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0d20-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="f0d20-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0d20-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="f0d20-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0d20-112">**Library:** CorGuids.lib</span></span>

**<span data-ttu-id="f0d20-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f0d20-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a><span data-ttu-id="f0d20-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0d20-114">See also</span></span>

- [<span data-ttu-id="f0d20-115">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0d20-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="f0d20-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f0d20-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f0d20-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f0d20-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
