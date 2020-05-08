---
title: ICorDebugDataTarget3::GetLoadedModules-Methode
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: c3565f4f9284bc121b0e2d3b0885cbea927acfdd
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976420"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="24d43-102">ICorDebugDataTarget3::GetLoadedModules-Methode</span><span class="sxs-lookup"><span data-stu-id="24d43-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="24d43-103">Ruft eine Liste der Module ab, die bisher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="24d43-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24d43-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24d43-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24d43-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="24d43-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="24d43-106">[in] Die Anzahl der Module, für die Informationen angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="24d43-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="24d43-107">[out] Ein Zeiger auf die Anzahl der Module, zu denen Informationen zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="24d43-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="24d43-108">vorgenommen Ein Zeiger auf ein Array von [icordebugloadedmodule](icordebugloadedmodule-interface.md) -Objekten, die Informationen über geladene Module bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="24d43-108">[out] A pointer to an array of [ICorDebugLoadedModule](icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24d43-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24d43-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24d43-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="24d43-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24d43-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24d43-111">Requirements</span></span>  
 <span data-ttu-id="24d43-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24d43-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24d43-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24d43-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24d43-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24d43-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24d43-115">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24d43-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24d43-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24d43-116">See also</span></span>

- [<span data-ttu-id="24d43-117">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24d43-117">ICorDebugDataTarget3 Interface</span></span>](icordebugdatatarget3-interface.md)
- [<span data-ttu-id="24d43-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="24d43-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
