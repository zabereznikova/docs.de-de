---
title: ICorDebugStaticFieldSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fed264da3767ffa74a1b61583639887adbea4a71
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490735"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="afa48-102">ICorDebugStaticFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="afa48-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="afa48-103">Ruft die Größe des statischen Felds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="afa48-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afa48-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="afa48-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afa48-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="afa48-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="afa48-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="afa48-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afa48-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="afa48-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afa48-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="afa48-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afa48-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="afa48-109">Requirements</span></span>  
 <span data-ttu-id="afa48-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afa48-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afa48-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afa48-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afa48-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afa48-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afa48-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afa48-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa48-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afa48-114">See also</span></span>
- [<span data-ttu-id="afa48-115">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="afa48-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="afa48-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="afa48-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
