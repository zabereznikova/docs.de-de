---
title: ICorDebugDataTarget3::GetLoadedModules-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3db6449abee4eed4a8e5d6c691834c52dc0717e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="94a08-102">ICorDebugDataTarget3::GetLoadedModules-Methode</span><span class="sxs-lookup"><span data-stu-id="94a08-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="94a08-103">Ruft eine Liste der Module ab, die bisher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="94a08-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94a08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94a08-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94a08-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="94a08-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="94a08-106">[in] Die Anzahl der Module, für die Informationen angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="94a08-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="94a08-107">[out] Ein Zeiger auf die Anzahl der Module, zu denen Informationen zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="94a08-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="94a08-108">[out] Ein Zeiger auf ein Array von [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) Objekte, die Informationen zur geladene Module.</span><span class="sxs-lookup"><span data-stu-id="94a08-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94a08-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94a08-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94a08-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="94a08-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94a08-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94a08-111">Requirements</span></span>  
 <span data-ttu-id="94a08-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94a08-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94a08-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94a08-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94a08-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94a08-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94a08-115">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94a08-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a08-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94a08-116">See Also</span></span>  
 [<span data-ttu-id="94a08-117">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94a08-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 [<span data-ttu-id="94a08-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="94a08-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
