---
title: 'Icordebugmemorybuffer:: getstartaddress-Methode'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1394624051baa9e7dd21e29788d5fab28332081b
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987546"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="77108-102">Icordebugmemorybuffer:: getstartaddress-Methode</span><span class="sxs-lookup"><span data-stu-id="77108-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="77108-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="77108-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77108-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77108-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77108-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="77108-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="77108-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="77108-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77108-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77108-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="77108-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="77108-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77108-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77108-109">Requirements</span></span>  
 <span data-ttu-id="77108-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77108-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77108-111">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="77108-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77108-112">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77108-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77108-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77108-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77108-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77108-114">See also</span></span>

- [<span data-ttu-id="77108-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77108-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="77108-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="77108-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
