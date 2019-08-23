---
title: ICorDebugMergedAssemblyRecord::GetIndex-Methode
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca304b90cee291ef86e225c2b0691631833e53a2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917946"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="bb6a8-102">ICorDebugMergedAssemblyRecord::GetIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="bb6a8-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="bb6a8-103">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="bb6a8-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb6a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb6a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb6a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb6a8-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="bb6a8-106">[out] Ein Zeiger auf den Präfixindex.</span><span class="sxs-lookup"><span data-stu-id="bb6a8-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb6a8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb6a8-107">Remarks</span></span>  
 <span data-ttu-id="bb6a8-108">Der Präfixindex wird verwendet, um Namenskonflikte in den zusammengeführten Namen der Metadatentypen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="bb6a8-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb6a8-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bb6a8-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb6a8-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb6a8-110">Requirements</span></span>  
 <span data-ttu-id="bb6a8-111">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb6a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb6a8-112">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="bb6a8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb6a8-113">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb6a8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb6a8-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb6a8-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb6a8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb6a8-115">See also</span></span>

- [<span data-ttu-id="bb6a8-116">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb6a8-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="bb6a8-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bb6a8-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
