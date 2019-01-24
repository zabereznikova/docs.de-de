---
title: ICorDebugDataTarget3::GetLoadedModules-Methode
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b961e0a84d199f0acf22dfc0f87b1d35c118adc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651057"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="3fc03-102">ICorDebugDataTarget3::GetLoadedModules-Methode</span><span class="sxs-lookup"><span data-stu-id="3fc03-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="3fc03-103">Ruft eine Liste der Module ab, die bisher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="3fc03-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc03-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fc03-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fc03-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3fc03-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="3fc03-106">[in] Die Anzahl der Module, für die Informationen angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="3fc03-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="3fc03-107">[out] Ein Zeiger auf die Anzahl der Module, zu denen Informationen zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="3fc03-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="3fc03-108">[out] Ein Zeiger auf ein Array von [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) Objekte, die Informationen über geladene Module.</span><span class="sxs-lookup"><span data-stu-id="3fc03-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fc03-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3fc03-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fc03-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3fc03-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fc03-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3fc03-111">Requirements</span></span>  
 <span data-ttu-id="3fc03-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fc03-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fc03-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fc03-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fc03-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fc03-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fc03-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fc03-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc03-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fc03-116">See also</span></span>
- [<span data-ttu-id="3fc03-117">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3fc03-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)
- [<span data-ttu-id="3fc03-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3fc03-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
