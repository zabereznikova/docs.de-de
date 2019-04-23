---
title: ICorDebugProcess3::SetEnableCustomNotification-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8c8725bf21aefa3abf5fc41366d8f983bd686b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175746"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="ee487-102">ICorDebugProcess3::SetEnableCustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="ee487-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="ee487-103">Aktiviert und deaktiviert benutzerdefinierte Debuggerbenachrichtigungen des angegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="ee487-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee487-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee487-104">Syntax</span></span>  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee487-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ee487-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="ee487-106">[in] Der Typ, der angibt, benutzerdefinierte Debuggerbenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="ee487-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="ee487-107">[in] `true` benutzerdefinierte Debuggerbenachrichtigungen; aktivieren `false` um Benachrichtigungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ee487-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="ee487-108">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="ee487-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee487-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee487-109">Remarks</span></span>  
 <span data-ttu-id="ee487-110">Wenn `fEnable` nastaven NA hodnotu `true`, Aufrufe von der <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> Methode Trigger ein [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="ee487-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="ee487-111">Benachrichtigungen sind standardmäßig deaktiviert. aus diesem Grund muss der Debugger alle Benachrichtigungstypen angeben, die es kennt und behandeln möchte.</span><span class="sxs-lookup"><span data-stu-id="ee487-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="ee487-112">Da die [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Klasse bezieht sich durch die Anwendungsdomäne, die der Debugger muss Aufrufen `SetEnableCustomNotification` für jede Anwendungsdomäne, in den Prozess, wenn sie die Benachrichtigung für den gesamten Prozess empfangen möchte.</span><span class="sxs-lookup"><span data-stu-id="ee487-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="ee487-113">Beginnend mit der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], der nur unterstützte Benachrichtigung eine Benachrichtigung threadübergreifenden Abhängigkeit ist.</span><span class="sxs-lookup"><span data-stu-id="ee487-113">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee487-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee487-114">Requirements</span></span>  
 <span data-ttu-id="ee487-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee487-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee487-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee487-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee487-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee487-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee487-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee487-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee487-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee487-119">See also</span></span>

- [<span data-ttu-id="ee487-120">ICorDebugProcess3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee487-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [<span data-ttu-id="ee487-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ee487-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ee487-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ee487-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
