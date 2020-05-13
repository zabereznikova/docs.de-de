---
title: ICorDebugModuleEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
ms.openlocfilehash: ccb9eff963da1d502d1ed789640f1a108676754c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213347"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="cc088-102">ICorDebugModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cc088-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="cc088-103">Implementiert ICorDebugEnum-Methoden und listet ICorDebugModule-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="cc088-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cc088-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="cc088-104">Methods</span></span>  
  
|<span data-ttu-id="cc088-105">Methode</span><span class="sxs-lookup"><span data-stu-id="cc088-105">Method</span></span>|<span data-ttu-id="cc088-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc088-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cc088-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="cc088-107">Next Method</span></span>](icordebugmoduleenum-next-method.md)|<span data-ttu-id="cc088-108">Ruft die angegebene Anzahl von- `ICorDebugModule` Instanzen ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="cc088-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc088-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc088-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc088-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cc088-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc088-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cc088-111">Requirements</span></span>  
 <span data-ttu-id="cc088-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc088-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc088-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc088-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc088-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc088-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc088-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc088-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc088-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc088-116">See also</span></span>

- [<span data-ttu-id="cc088-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="cc088-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
