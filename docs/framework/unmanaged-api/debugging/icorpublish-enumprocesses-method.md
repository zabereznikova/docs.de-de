---
title: ICorPublish::EnumProcesses-Methode
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
ms.openlocfilehash: 297f672097dd6561a971608f368369c623532907
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716914"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="df91c-102">ICorPublish::EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="df91c-102">ICorPublish::EnumProcesses Method</span></span>

<span data-ttu-id="df91c-103">Ruft einen Enumerator für die verwalteten Prozesse ab, die auf diesem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="df91c-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df91c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df91c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df91c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df91c-105">Parameters</span></span>  

 `Type`  
 <span data-ttu-id="df91c-106">Ein Wert der [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) -Enumeration, die den Typ des abzurufenden Prozesses angibt.</span><span class="sxs-lookup"><span data-stu-id="df91c-106">A value of the [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="df91c-107">In der aktuellen Version ist nur COR_PUB_MANAGEDONLY gültig.</span><span class="sxs-lookup"><span data-stu-id="df91c-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="df91c-108">Ein Zeiger auf die Adresse einer [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) -Instanz, bei der es sich um den Enumerator der Prozesse handelt.</span><span class="sxs-lookup"><span data-stu-id="df91c-108">A pointer to the address of an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df91c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df91c-109">Remarks</span></span>  

 <span data-ttu-id="df91c-110">Die Auflistung der Prozesse des Enumerators basiert auf einer Momentaufnahme der Prozesse, die ausgeführt werden, wenn die- `EnumProcesses` Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="df91c-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="df91c-111">Der Enumerator enthält keine Prozesse, die vor oder nach dem Aufruf von beendet werden `EnumProcesses` .</span><span class="sxs-lookup"><span data-stu-id="df91c-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="df91c-112">Die `EnumProcesses` Methode kann mehrmals für diese [ICorPublish](icorpublish-interface.md) -Instanz aufgerufen werden, um eine neue aktuelle Sammlung von Prozessen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="df91c-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="df91c-113">Bei nachfolgenden Aufrufen der-Methode werden vorhandene Auflistungen nicht beeinträchtigt `EnumProcesses` .</span><span class="sxs-lookup"><span data-stu-id="df91c-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df91c-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="df91c-114">Requirements</span></span>  

 <span data-ttu-id="df91c-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df91c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df91c-116">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="df91c-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="df91c-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df91c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df91c-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df91c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df91c-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df91c-119">See also</span></span>

- [<span data-ttu-id="df91c-120">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df91c-120">ICorPublish Interface</span></span>](icorpublish-interface.md)
