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
ms.openlocfilehash: bc4820d2c71830b297ed690c440c90cfff1f9601
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="73bb8-102">ICorDebugDataTarget3::GetLoadedModules-Methode</span><span class="sxs-lookup"><span data-stu-id="73bb8-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="73bb8-103">Ruft eine Liste der Module ab, die bisher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="73bb8-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73bb8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="73bb8-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73bb8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="73bb8-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="73bb8-106">[in] Die Anzahl der Module, für die Informationen angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="73bb8-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="73bb8-107">[out] Ein Zeiger auf die Anzahl der Module, zu denen Informationen zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="73bb8-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="73bb8-108">[out] Ein Zeiger auf ein Array von [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) Objekte, die Informationen zur geladene Module.</span><span class="sxs-lookup"><span data-stu-id="73bb8-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73bb8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="73bb8-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73bb8-110">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="73bb8-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73bb8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73bb8-111">Requirements</span></span>  
 <span data-ttu-id="73bb8-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73bb8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73bb8-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73bb8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73bb8-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73bb8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73bb8-115">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73bb8-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73bb8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73bb8-116">See Also</span></span>  
 [<span data-ttu-id="73bb8-117">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73bb8-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 [<span data-ttu-id="73bb8-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="73bb8-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
