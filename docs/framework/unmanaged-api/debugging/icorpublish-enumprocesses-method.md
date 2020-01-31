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
ms.openlocfilehash: 5f785b22a3fbda6403c124ec70757b16f5335907
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790768"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="f42c2-102">ICorPublish::EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="f42c2-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="f42c2-103">Ruft einen Enumerator für die verwalteten Prozesse ab, die auf diesem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f42c2-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f42c2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f42c2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f42c2-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f42c2-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="f42c2-106">Ein Wert der [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) -Enumeration, die den Typ des abzurufenden Prozesses angibt.</span><span class="sxs-lookup"><span data-stu-id="f42c2-106">A value of the [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="f42c2-107">In der aktuellen Version ist nur COR_PUB_MANAGEDONLY gültig.</span><span class="sxs-lookup"><span data-stu-id="f42c2-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="f42c2-108">Ein Zeiger auf die Adresse einer [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) -Instanz, bei der es sich um den Enumerator der Prozesse handelt.</span><span class="sxs-lookup"><span data-stu-id="f42c2-108">A pointer to the address of an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f42c2-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f42c2-109">Remarks</span></span>  
 <span data-ttu-id="f42c2-110">Die Auflistung der Prozesse des Enumerators basiert auf einer Momentaufnahme der Prozesse, die ausgeführt werden, wenn die `EnumProcesses`-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f42c2-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="f42c2-111">Der Enumerator enthält keine Prozesse, die vor oder nach dem Aufruf von `EnumProcesses` beendet werden.</span><span class="sxs-lookup"><span data-stu-id="f42c2-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="f42c2-112">Die `EnumProcesses`-Methode kann mehrmals für diese [ICorPublish](icorpublish-interface.md) -Instanz aufgerufen werden, um eine neue aktuelle Sammlung von Prozessen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f42c2-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="f42c2-113">Vorhandene Auflistungen werden von nachfolgenden Aufrufen der `EnumProcesses`-Methode nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="f42c2-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f42c2-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f42c2-114">Requirements</span></span>  
 <span data-ttu-id="f42c2-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f42c2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f42c2-116">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="f42c2-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f42c2-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f42c2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f42c2-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f42c2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f42c2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f42c2-119">See also</span></span>

- [<span data-ttu-id="f42c2-120">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f42c2-120">ICorPublish Interface</span></span>](icorpublish-interface.md)
