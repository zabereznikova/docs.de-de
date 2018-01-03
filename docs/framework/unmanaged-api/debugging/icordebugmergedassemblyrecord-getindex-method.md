---
title: ICorDebugMergedAssemblyRecord::GetIndex-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54ff8d6935f5507ab02d9d566921cb7f8a890bb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="44ddb-102">ICorDebugMergedAssemblyRecord::GetIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="44ddb-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="44ddb-103">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="44ddb-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44ddb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44ddb-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44ddb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44ddb-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="44ddb-106">[out] Ein Zeiger auf den Präfixindex.</span><span class="sxs-lookup"><span data-stu-id="44ddb-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44ddb-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44ddb-107">Remarks</span></span>  
 <span data-ttu-id="44ddb-108">Der Präfixindex wird verwendet, um Namenskonflikte in den zusammengeführten Namen der Metadatentypen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="44ddb-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44ddb-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="44ddb-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44ddb-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44ddb-110">Requirements</span></span>  
 <span data-ttu-id="44ddb-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44ddb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44ddb-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44ddb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44ddb-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44ddb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44ddb-114">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44ddb-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44ddb-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44ddb-115">See Also</span></span>  
 [<span data-ttu-id="44ddb-116">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44ddb-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="44ddb-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="44ddb-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
