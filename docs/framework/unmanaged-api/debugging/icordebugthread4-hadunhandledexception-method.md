---
title: ICorDebugThread4::HadUnhandledException-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12433786f353212c1ffbd57e9bf526c3ecc60e9a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163630"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="ea595-102">ICorDebugThread4::HadUnhandledException-Methode</span><span class="sxs-lookup"><span data-stu-id="ea595-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="ea595-103">Gibt an, ob der Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ea595-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea595-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea595-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea595-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea595-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="ea595-106">[out] Ein Zeiger auf die Adresse des eine geordnete Enumeration von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="ea595-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea595-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ea595-107">Return Value</span></span>  
 <span data-ttu-id="ea595-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ea595-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ea595-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea595-109">HRESULT</span></span>|<span data-ttu-id="ea595-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea595-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ea595-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea595-111">S_OK</span></span>|<span data-ttu-id="ea595-112">Der Thread ist seit seiner Erstellung eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ea595-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="ea595-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ea595-113">S_FALSE</span></span>|<span data-ttu-id="ea595-114">Der Thread ist nie eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ea595-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea595-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea595-115">Remarks</span></span>  
 <span data-ttu-id="ea595-116">Diese Methode gibt an, ob der Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ea595-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="ea595-117">Mit der Zeit wird der Rückruf nicht behandelte Ausnahme ausgelöst oder systemeigenes JIT-attach initiiert wird, diese Methode wird immer S_OK zurück.</span><span class="sxs-lookup"><span data-stu-id="ea595-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="ea595-118">Es gibt keine Garantie, die die [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) Methode gibt zurück, die nicht behandelte Ausnahme; allerdings es tritt ein, wenn der Prozess nicht noch fortgesetzt wurde nach dem Abrufen des nicht behandelten Ausnahmerückrufs oder nach systemeigenes JIT-attach.</span><span class="sxs-lookup"><span data-stu-id="ea595-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="ea595-119">Außerdem ist es möglich (wenn auch unwahrscheinlich), sodass mehr als ein Thread mit einem Ausnahmefehler, die zum Zeitpunkt der nativen JIT-attach wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ea595-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="ea595-120">In diesem Fall besteht keine Möglichkeit festzustellen, welche Ausnahme ausgelöst, der JIT-attach zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ea595-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea595-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea595-121">Requirements</span></span>  
 <span data-ttu-id="ea595-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea595-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea595-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea595-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea595-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea595-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea595-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea595-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea595-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea595-126">See also</span></span>

- [<span data-ttu-id="ea595-127">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea595-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="ea595-128">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ea595-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ea595-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ea595-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
