---
title: ICorDebugInstanceFieldSymbol::GetSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad13dbe8148d4d9507c6a450d2833da049e0e13a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="79257-102">ICorDebugInstanceFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="79257-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="79257-103">Ruft die Größe des Instanzfelds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="79257-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79257-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="79257-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79257-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="79257-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="79257-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="79257-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79257-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79257-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79257-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="79257-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79257-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="79257-109">Requirements</span></span>  
 <span data-ttu-id="79257-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79257-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79257-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79257-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79257-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79257-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79257-113">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79257-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79257-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79257-114">See Also</span></span>  
 [<span data-ttu-id="79257-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79257-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="79257-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="79257-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
