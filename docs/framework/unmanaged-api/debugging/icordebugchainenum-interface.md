---
title: ICorDebugChainEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum
helpviewer_keywords:
- ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6639335c-48e1-4e74-a4f3-70a6a0f54af1
topic_type:
- apiref
ms.openlocfilehash: 4556ebbd05e0660da14fb59d806c8feb0b45b9bb
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894227"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="770e7-102">ICorDebugChainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="770e7-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="770e7-103">Implementiert ICorDebugEnum-Methoden und listet ICorDebugChain-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="770e7-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="770e7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="770e7-104">Methods</span></span>  
  
|<span data-ttu-id="770e7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="770e7-105">Method</span></span>|<span data-ttu-id="770e7-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="770e7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="770e7-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="770e7-107">Next Method</span></span>](icordebugchainenum-next-method.md)|<span data-ttu-id="770e7-108">Ruft die angegebene Anzahl von `ICorDebugChain` -Instanzen ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="770e7-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="770e7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="770e7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="770e7-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="770e7-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="770e7-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="770e7-111">Requirements</span></span>  
 <span data-ttu-id="770e7-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="770e7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="770e7-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="770e7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="770e7-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="770e7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="770e7-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="770e7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="770e7-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="770e7-116">See also</span></span>

- [<span data-ttu-id="770e7-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="770e7-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
