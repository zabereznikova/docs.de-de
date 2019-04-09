---
title: ICorDebugDataTarget3::GetLoadedModules-Methode
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 464fd9ac44d6ba5717dbc4ecfbe03b6e6ad52276
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138657"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="e65fe-102">ICorDebugDataTarget3::GetLoadedModules-Methode</span><span class="sxs-lookup"><span data-stu-id="e65fe-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="e65fe-103">Ruft eine Liste der Module ab, die bisher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="e65fe-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e65fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e65fe-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e65fe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e65fe-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="e65fe-106">[in] Die Anzahl der Module, für die Informationen angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="e65fe-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="e65fe-107">[out] Ein Zeiger auf die Anzahl der Module, zu denen Informationen zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="e65fe-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="e65fe-108">[out] Ein Zeiger auf ein Array von [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) Objekte, die Informationen über geladene Module.</span><span class="sxs-lookup"><span data-stu-id="e65fe-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e65fe-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e65fe-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e65fe-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e65fe-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e65fe-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e65fe-111">Requirements</span></span>  
 <span data-ttu-id="e65fe-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e65fe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e65fe-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e65fe-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e65fe-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e65fe-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e65fe-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e65fe-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e65fe-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e65fe-116">See also</span></span>

- [<span data-ttu-id="e65fe-117">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e65fe-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)
- [<span data-ttu-id="e65fe-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e65fe-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
