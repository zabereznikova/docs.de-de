---
title: ICorDebugLoadedModule::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce937b28d705fc35165368fa81a376facce18a30
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476502"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="c2f7b-102">ICorDebugLoadedModule::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="c2f7b-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="c2f7b-103">Ruft die Größe des geladenen Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="c2f7b-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2f7b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2f7b-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2f7b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2f7b-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="c2f7b-106">[out] Ein Zeiger auf die Anzahl von Bytes im geladenen Modul.</span><span class="sxs-lookup"><span data-stu-id="c2f7b-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2f7b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2f7b-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2f7b-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c2f7b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2f7b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2f7b-109">Requirements</span></span>  
 <span data-ttu-id="c2f7b-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2f7b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2f7b-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2f7b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2f7b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2f7b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2f7b-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2f7b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f7b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2f7b-114">See also</span></span>
- [<span data-ttu-id="c2f7b-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2f7b-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="c2f7b-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c2f7b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
