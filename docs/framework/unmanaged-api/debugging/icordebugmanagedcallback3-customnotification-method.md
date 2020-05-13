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
ms.openlocfilehash: 8a4620e591cc80efb5c0fd53b0edf3a35849c421
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209759"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="62e82-102">ICorDebugManagedCallback3::CustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="62e82-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="62e82-103">Gibt an, dass eine benutzerdefinierte debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="62e82-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62e82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62e82-104">Syntax</span></span>  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62e82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="62e82-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="62e82-106">in Ein Zeiger auf den Thread, der die Benachrichtigung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="62e82-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="62e82-107">in Ein Zeiger auf die Anwendungsdomäne, die den Thread enthält, der die Benachrichtigung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="62e82-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62e82-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="62e82-108">Return Value</span></span>  
 <span data-ttu-id="62e82-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="62e82-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="62e82-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62e82-110">HRESULT</span></span>|<span data-ttu-id="62e82-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="62e82-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62e82-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="62e82-112">S_OK</span></span>|<span data-ttu-id="62e82-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="62e82-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="62e82-114">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="62e82-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62e82-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62e82-115">Remarks</span></span>  
 <span data-ttu-id="62e82-116">Ein nachfolgendes Aufrufen der [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) -Methode ruft das Thread Objekt ab, das an die-Methode übergeben wurde <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="62e82-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="62e82-117">Der Typ des Thread Objekts muss zuvor durch Aufrufen der [ICorDebugProcess3:: SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) -Methode aktiviert worden sein.</span><span class="sxs-lookup"><span data-stu-id="62e82-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="62e82-118">Der Debugger kann typspezifische Parameter aus den Feldern des Thread Objekts lesen und Antworten in Feldern speichern.</span><span class="sxs-lookup"><span data-stu-id="62e82-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="62e82-119">Die [ICorDebug](icordebug-interface.md) -Schnittstelle erzwingt keine Richtlinien für die Benachrichtigungs Typen oder deren Inhalte, und die Semantik der Benachrichtigungen ist strikt ein Vertrag zwischen Debugger, Anwendungen und der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="62e82-119">The [ICorDebug](icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62e82-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="62e82-120">Requirements</span></span>  
 <span data-ttu-id="62e82-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62e82-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62e82-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62e82-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62e82-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62e82-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62e82-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62e82-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62e82-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62e82-125">See also</span></span>

- [<span data-ttu-id="62e82-126">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62e82-126">ICorDebugManagedCallback3 Interface</span></span>](icordebugmanagedcallback3-interface.md)
- [<span data-ttu-id="62e82-127">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="62e82-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="62e82-128">Debuggen</span><span class="sxs-lookup"><span data-stu-id="62e82-128">Debugging</span></span>](index.md)
