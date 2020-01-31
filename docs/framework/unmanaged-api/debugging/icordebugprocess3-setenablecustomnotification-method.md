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
ms.openlocfilehash: f2f365f3fe1568f2dd3bad677dd77a13946002e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792469"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="4e9a7-102">ICorDebugProcess3::SetEnableCustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="4e9a7-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="4e9a7-103">Aktiviert und deaktiviert benutzerdefinierte Debugger-Benachrichtigungen vom angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="4e9a7-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e9a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e9a7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e9a7-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4e9a7-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="4e9a7-106">in Der Typ, der benutzerdefinierte debuggerbenachrichtigungen angibt.</span><span class="sxs-lookup"><span data-stu-id="4e9a7-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="4e9a7-107">[in] `true`, um benutzerdefinierte Debugger-Benachrichtigungen zu aktivieren. `false`, um Benachrichtigungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4e9a7-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="4e9a7-108">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="4e9a7-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e9a7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e9a7-109">Remarks</span></span>  
 <span data-ttu-id="4e9a7-110">Wenn `fEnable` auf `true`festgelegt ist, wird durch Aufrufe der <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType>-Methode ein [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) -Rückruf auslöst.</span><span class="sxs-lookup"><span data-stu-id="4e9a7-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="4e9a7-111">Benachrichtigungen sind standardmäßig deaktiviert. Daher muss der Debugger alle Benachrichtigungs Typen angeben, die er kennt und verarbeiten soll.</span><span class="sxs-lookup"><span data-stu-id="4e9a7-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="4e9a7-112">Da die [ICorDebugClass](icordebug-interface.md) -Klasse durch die Anwendungsdomäne begrenzt ist, muss der Debugger `SetEnableCustomNotification` für jede Anwendungsdomäne im Prozess aufrufen, wenn die Benachrichtigung über den gesamten Prozess empfangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e9a7-112">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="4e9a7-113">Ab .NET Framework 4 ist die einzige unterstützte Benachrichtigung eine Thread übergreifende Abhängigkeits Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="4e9a7-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e9a7-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e9a7-114">Requirements</span></span>  
 <span data-ttu-id="4e9a7-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e9a7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e9a7-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e9a7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e9a7-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e9a7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e9a7-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e9a7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e9a7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e9a7-119">See also</span></span>

- [<span data-ttu-id="4e9a7-120">ICorDebugProcess3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e9a7-120">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="4e9a7-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4e9a7-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4e9a7-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4e9a7-122">Debugging</span></span>](index.md)
