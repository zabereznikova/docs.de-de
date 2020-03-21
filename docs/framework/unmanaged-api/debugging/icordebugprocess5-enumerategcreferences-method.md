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
ms.openlocfilehash: a97c14d83f99c847bb8569a33e175ab6eb5bccd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178619"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="08dcf-102">ICorDebugProcess5::EnumerateGCReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="08dcf-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="08dcf-103">Ruft einen Enumerator für alle Objekte ab, die in einem Prozess Garbage Collection sein sollen.</span><span class="sxs-lookup"><span data-stu-id="08dcf-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08dcf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08dcf-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08dcf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08dcf-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="08dcf-106">[in] Ein boolescher Wert, der angibt, ob auch schwache Referenzen aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="08dcf-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="08dcf-107">Wenn `enumerateWeakReferences` `true`ist `ppEnum` , enthält der Enumerator sowohl starke als auch schwache Verweise.</span><span class="sxs-lookup"><span data-stu-id="08dcf-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="08dcf-108">Wenn `enumerateWeakReferences` `false`dies der Ansicht ist, enthält der Enumerator nur starke Verweise.</span><span class="sxs-lookup"><span data-stu-id="08dcf-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="08dcf-109">[out] Ein Zeiger auf die Adresse eines [ICorDebugGCReferenceEnum,](icordebuggcreferenceenum-interface.md) das ein Enumerator für die Objekte ist, die Garbage Collection sein sollen.</span><span class="sxs-lookup"><span data-stu-id="08dcf-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08dcf-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="08dcf-110">Remarks</span></span>  
 <span data-ttu-id="08dcf-111">Diese Methode bietet eine Möglichkeit, die vollständige Verwurzelungskette für jedes verwaltete Objekt in einem Prozess zu bestimmen, und kann verwendet werden, um zu bestimmen, warum ein Objekt noch am Leben ist.</span><span class="sxs-lookup"><span data-stu-id="08dcf-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08dcf-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="08dcf-112">Requirements</span></span>  
 <span data-ttu-id="08dcf-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08dcf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08dcf-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08dcf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08dcf-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08dcf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08dcf-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08dcf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08dcf-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08dcf-117">See also</span></span>

- [<span data-ttu-id="08dcf-118">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08dcf-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="08dcf-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="08dcf-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
