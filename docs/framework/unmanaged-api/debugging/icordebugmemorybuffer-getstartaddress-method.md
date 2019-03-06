---
title: ICorDebugMemoryBuffer::GetStartAddress-Methode
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f4f51c087112053aa7b76bff1f7c55016c8ff57
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474747"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="5e061-102">ICorDebugMemoryBuffer::GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="5e061-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="5e061-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="5e061-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e061-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e061-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e061-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e061-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5e061-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="5e061-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e061-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e061-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5e061-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5e061-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e061-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e061-109">Requirements</span></span>  
 <span data-ttu-id="5e061-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e061-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e061-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e061-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e061-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e061-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e061-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e061-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e061-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e061-114">See also</span></span>
- [<span data-ttu-id="5e061-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e061-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="5e061-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5e061-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
