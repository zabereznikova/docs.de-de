---
title: ICorDebugProcess5::EnumerateGCReferences-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b5f66099eb4b1cb84d9911567cac4255bf20480
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421396"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="6e1d9-102">ICorDebugProcess5::EnumerateGCReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="6e1d9-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="6e1d9-103">Ruft einen Enumerator für alle Objekte, die in einem Prozess speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e1d9-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e1d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e1d9-104">Syntax</span></span>  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e1d9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e1d9-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="6e1d9-106">[in] Ein boolescher Wert, der angibt, ob schwache Verweise ebenfalls aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6e1d9-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="6e1d9-107">Wenn `enumerateWeakReferences` ist `true`die `ppEnum` Enumerator enthält, starken Verweise und schwache Verweise.</span><span class="sxs-lookup"><span data-stu-id="6e1d9-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="6e1d9-108">Wenn `enumerateWeakReferences` ist `false`, der Enumerator enthält nur starke Verweise.</span><span class="sxs-lookup"><span data-stu-id="6e1d9-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="6e1d9-109">[out] Ein Zeiger auf die Adresse des ein [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) also einen Enumerator für die Objekte, die Garbage Collection übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="6e1d9-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e1d9-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e1d9-110">Remarks</span></span>  
 <span data-ttu-id="6e1d9-111">Diese Methode bietet eine Möglichkeit, die vollständige rooting-Kette für ein verwaltetes Objekt in einen Prozess zu ermitteln und kann verwendet werden, um zu bestimmen, warum ein Objekt noch aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="6e1d9-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e1d9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6e1d9-112">Requirements</span></span>  
 <span data-ttu-id="6e1d9-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e1d9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e1d9-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e1d9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e1d9-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e1d9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e1d9-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e1d9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e1d9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e1d9-117">See Also</span></span>  
 [<span data-ttu-id="6e1d9-118">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e1d9-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="6e1d9-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6e1d9-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
