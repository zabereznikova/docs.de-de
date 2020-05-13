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
ms.openlocfilehash: 4d954057c519263da49f8aaeeeef6ab9402b6956
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378373"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="27848-102">ICorDebugThread4::HadUnhandledException-Methode</span><span class="sxs-lookup"><span data-stu-id="27848-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="27848-103">Gibt an, ob für den Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="27848-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27848-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27848-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="27848-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="27848-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="27848-106">vorgenommen Ein Zeiger auf die Adresse einer geordneten Enumeration von [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Strukturen.</span><span class="sxs-lookup"><span data-stu-id="27848-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27848-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="27848-107">Return Value</span></span>  
 <span data-ttu-id="27848-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="27848-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="27848-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27848-109">HRESULT</span></span>|<span data-ttu-id="27848-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="27848-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27848-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="27848-111">S_OK</span></span>|<span data-ttu-id="27848-112">Der Thread weist seit seiner Erstellung eine nicht behandelte Ausnahme auf.</span><span class="sxs-lookup"><span data-stu-id="27848-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="27848-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="27848-113">S_FALSE</span></span>|<span data-ttu-id="27848-114">Der Thread weist nie eine nicht behandelte Ausnahme auf.</span><span class="sxs-lookup"><span data-stu-id="27848-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27848-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27848-115">Remarks</span></span>  
 <span data-ttu-id="27848-116">Diese Methode gibt an, ob für den Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="27848-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="27848-117">Zum Zeitpunkt der Auslösung des nicht behandelten Ausnahme Rückrufs oder des nativen JIT-Anfügens wird von dieser Methode garantiert S_OK zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="27848-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="27848-118">Es gibt keine Garantie dafür, dass die [ICorDebugThread. geteption TException](icordebugthread-getcurrentexception-method.md) -Methode die nicht behandelte Ausnahme zurückgibt. Dies ist jedoch der Fall, wenn der Prozess noch nicht fortgesetzt wurde, nachdem der Rückruf für nicht behandelte Ausnahmen oder das systemeigene JIT-Anfügen erhalten wurde.</span><span class="sxs-lookup"><span data-stu-id="27848-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="27848-119">Darüber hinaus ist es möglich (auch wenn unwahrscheinlich), dass zum Zeitpunkt der Auslösung des nativen JIT-Anfügens mehr als ein Thread mit einer nicht behandelten Ausnahme vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="27848-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="27848-120">In einem solchen Fall gibt es keine Möglichkeit, zu bestimmen, welche Ausnahme das JIT-attach ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="27848-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27848-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="27848-121">Requirements</span></span>  
 <span data-ttu-id="27848-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27848-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27848-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27848-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27848-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27848-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27848-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27848-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27848-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27848-126">See also</span></span>

- [<span data-ttu-id="27848-127">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27848-127">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="27848-128">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="27848-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="27848-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="27848-129">Debugging</span></span>](index.md)
