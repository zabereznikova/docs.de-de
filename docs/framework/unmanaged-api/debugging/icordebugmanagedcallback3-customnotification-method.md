---
title: ICorDebugManagedCallback3::CustomNotification-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
ms.openlocfilehash: f30c9b6746d0e1594994870a96e94eb8105e4c94
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700833"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="83f74-102">ICorDebugManagedCallback3::CustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="83f74-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>

<span data-ttu-id="83f74-103">Gibt an, dass eine benutzerdefinierte debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="83f74-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83f74-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83f74-104">Syntax</span></span>  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83f74-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="83f74-105">Parameters</span></span>  

 `pThread`  
 <span data-ttu-id="83f74-106">in Ein Zeiger auf den Thread, der die Benachrichtigung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="83f74-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="83f74-107">in Ein Zeiger auf die Anwendungsdomäne, die den Thread enthält, der die Benachrichtigung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="83f74-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83f74-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="83f74-108">Return Value</span></span>  

 <span data-ttu-id="83f74-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="83f74-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="83f74-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="83f74-110">HRESULT</span></span>|<span data-ttu-id="83f74-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="83f74-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="83f74-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="83f74-112">S_OK</span></span>|<span data-ttu-id="83f74-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="83f74-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="83f74-114">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="83f74-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83f74-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="83f74-115">Remarks</span></span>  

 <span data-ttu-id="83f74-116">Ein nachfolgendes Aufrufen der [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) -Methode ruft das Thread Objekt ab, das an die-Methode übergeben wurde <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="83f74-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="83f74-117">Der Typ des Thread Objekts muss zuvor durch Aufrufen der [ICorDebugProcess3:: SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) -Methode aktiviert worden sein.</span><span class="sxs-lookup"><span data-stu-id="83f74-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="83f74-118">Der Debugger kann typspezifische Parameter aus den Feldern des Thread Objekts lesen und Antworten in Feldern speichern.</span><span class="sxs-lookup"><span data-stu-id="83f74-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="83f74-119">Die [ICorDebug](icordebug-interface.md) -Schnittstelle erzwingt keine Richtlinien für die Benachrichtigungs Typen oder deren Inhalte, und die Semantik der Benachrichtigungen ist strikt ein Vertrag zwischen Debugger, Anwendungen und der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83f74-119">The [ICorDebug](icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83f74-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="83f74-120">Requirements</span></span>  

 <span data-ttu-id="83f74-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83f74-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83f74-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83f74-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83f74-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83f74-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83f74-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83f74-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83f74-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="83f74-125">See also</span></span>

- [<span data-ttu-id="83f74-126">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83f74-126">ICorDebugManagedCallback3 Interface</span></span>](icordebugmanagedcallback3-interface.md)
- [<span data-ttu-id="83f74-127">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="83f74-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="83f74-128">Debuggen</span><span class="sxs-lookup"><span data-stu-id="83f74-128">Debugging</span></span>](index.md)
