---
title: ICorDebugMemoryBuffer::GetStartAddress-Methode
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29149ceb155cdfdf7b735d6939809e80f2ba4dc0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695542"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="d16ae-102">ICorDebugMemoryBuffer::GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="d16ae-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="d16ae-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="d16ae-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d16ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d16ae-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d16ae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d16ae-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="d16ae-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="d16ae-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d16ae-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d16ae-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="d16ae-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d16ae-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d16ae-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d16ae-109">Requirements</span></span>  
 <span data-ttu-id="d16ae-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d16ae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d16ae-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d16ae-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d16ae-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d16ae-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d16ae-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d16ae-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d16ae-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d16ae-114">See also</span></span>
- [<span data-ttu-id="d16ae-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d16ae-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="d16ae-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d16ae-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
