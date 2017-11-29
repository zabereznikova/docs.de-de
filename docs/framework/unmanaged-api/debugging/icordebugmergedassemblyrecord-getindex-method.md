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
ms.openlocfilehash: dac64c785077fc3901e712498e66e11b9c9f3279
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="8d310-102">ICorDebugMergedAssemblyRecord::GetIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="8d310-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="8d310-103">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="8d310-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d310-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d310-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d310-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8d310-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="8d310-106">[out] Ein Zeiger auf den Präfixindex.</span><span class="sxs-lookup"><span data-stu-id="8d310-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d310-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8d310-107">Remarks</span></span>  
 <span data-ttu-id="8d310-108">Der Präfixindex wird verwendet, um Namenskonflikte in den zusammengeführten Namen der Metadatentypen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="8d310-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d310-109">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8d310-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d310-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8d310-110">Requirements</span></span>  
 <span data-ttu-id="8d310-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d310-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d310-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d310-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d310-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d310-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d310-114">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d310-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d310-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d310-115">See Also</span></span>  
 [<span data-ttu-id="8d310-116">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8d310-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="8d310-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8d310-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
