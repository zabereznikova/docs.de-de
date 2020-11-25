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
ms.openlocfilehash: 078e5cb03848564b42e30a079101d5a61e0074bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734022"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="50611-102">ICorDebugProcess3::SetEnableCustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="50611-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>

<span data-ttu-id="50611-103">Aktiviert und deaktiviert benutzerdefinierte Debugger-Benachrichtigungen vom angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="50611-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50611-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50611-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50611-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="50611-105">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="50611-106">in Der Typ, der benutzerdefinierte debuggerbenachrichtigungen angibt.</span><span class="sxs-lookup"><span data-stu-id="50611-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="50611-107">[in] `true` So aktivieren Sie benutzerdefinierte Debugger-Benachrichtigungen `false` zum Deaktivieren von Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="50611-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="50611-108">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="50611-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50611-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50611-109">Remarks</span></span>  

 <span data-ttu-id="50611-110">Wenn `fEnable` auf festgelegt ist, wird durch `true` Aufrufe der- <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> Methode ein [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) -Rückruf ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="50611-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="50611-111">Benachrichtigungen sind standardmäßig deaktiviert. Daher muss der Debugger alle Benachrichtigungs Typen angeben, die er kennt und verarbeiten soll.</span><span class="sxs-lookup"><span data-stu-id="50611-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="50611-112">Da die [ICorDebugClass](icordebug-interface.md) -Klasse durch die Anwendungsdomäne begrenzt ist, muss der Debugger `SetEnableCustomNotification` für jede Anwendungsdomäne im Prozess aufrufen, wenn er die Benachrichtigung über den gesamten Prozess empfangen möchte.</span><span class="sxs-lookup"><span data-stu-id="50611-112">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="50611-113">Ab .NET Framework 4 ist die einzige unterstützte Benachrichtigung eine Thread übergreifende Abhängigkeits Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="50611-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50611-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="50611-114">Requirements</span></span>  

 <span data-ttu-id="50611-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50611-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50611-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50611-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50611-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50611-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50611-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50611-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50611-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50611-119">See also</span></span>

- [<span data-ttu-id="50611-120">ICorDebugProcess3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50611-120">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="50611-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="50611-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="50611-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="50611-122">Debugging</span></span>](index.md)
