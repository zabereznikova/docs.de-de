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
ms.openlocfilehash: c98084b179d27e97ecb3bb34525967d41f8ad1cb
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489611"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="108f0-102">ICorDebugProcess3::SetEnableCustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="108f0-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="108f0-103">Aktiviert und deaktiviert benutzerdefinierte Debuggerbenachrichtigungen des angegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="108f0-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="108f0-104">Syntax</span></span>  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="108f0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="108f0-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="108f0-106">[in] Der Typ, der angibt, benutzerdefinierte Debuggerbenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="108f0-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="108f0-107">[in] `true` benutzerdefinierte Debuggerbenachrichtigungen; aktivieren `false` um Benachrichtigungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="108f0-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="108f0-108">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="108f0-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="108f0-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="108f0-109">Remarks</span></span>  
 <span data-ttu-id="108f0-110">Wenn `fEnable` nastaven NA hodnotu `true`, Aufrufe von der <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> Methode Trigger ein [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="108f0-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="108f0-111">Benachrichtigungen sind standardmäßig deaktiviert. aus diesem Grund muss der Debugger alle Benachrichtigungstypen angeben, die es kennt und behandeln möchte.</span><span class="sxs-lookup"><span data-stu-id="108f0-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="108f0-112">Da die [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Klasse bezieht sich durch die Anwendungsdomäne, die der Debugger muss Aufrufen `SetEnableCustomNotification` für jede Anwendungsdomäne, in den Prozess, wenn sie die Benachrichtigung für den gesamten Prozess empfangen möchte.</span><span class="sxs-lookup"><span data-stu-id="108f0-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="108f0-113">Ab .NET Framework 4 ist die einzige unterstützte Benachrichtigung eine Benachrichtigung threadübergreifenden Abhängigkeit.</span><span class="sxs-lookup"><span data-stu-id="108f0-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="108f0-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="108f0-114">Requirements</span></span>  
 <span data-ttu-id="108f0-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="108f0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="108f0-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="108f0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="108f0-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="108f0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="108f0-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="108f0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="108f0-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="108f0-119">See also</span></span>

- [<span data-ttu-id="108f0-120">ICorDebugProcess3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="108f0-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [<span data-ttu-id="108f0-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="108f0-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="108f0-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="108f0-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
