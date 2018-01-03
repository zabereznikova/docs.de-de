---
title: ICorDebugStaticFieldSymbol::GetSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b67cbe6858e91e089c36047d6ed83743e45e1d1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="1719c-102">ICorDebugStaticFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="1719c-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="1719c-103">Ruft die Größe des statischen Felds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="1719c-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1719c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1719c-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1719c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1719c-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="1719c-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="1719c-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1719c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1719c-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1719c-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1719c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1719c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1719c-109">Requirements</span></span>  
 <span data-ttu-id="1719c-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1719c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1719c-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1719c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1719c-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1719c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1719c-113">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1719c-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1719c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1719c-114">See Also</span></span>  
 [<span data-ttu-id="1719c-115">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1719c-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="1719c-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1719c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
