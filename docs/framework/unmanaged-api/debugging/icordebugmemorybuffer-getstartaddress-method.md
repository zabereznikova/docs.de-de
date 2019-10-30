---
title: 'Icordebugmemorybuffer:: getstartaddress-Methode'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: e2876398ceaf863bbb3c7e576d59b89c52f1bdaf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127990"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="c95a8-102">Icordebugmemorybuffer:: getstartaddress-Methode</span><span class="sxs-lookup"><span data-stu-id="c95a8-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="c95a8-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="c95a8-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c95a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c95a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c95a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c95a8-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c95a8-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="c95a8-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c95a8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c95a8-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="c95a8-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c95a8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c95a8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c95a8-109">Requirements</span></span>  
 <span data-ttu-id="c95a8-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c95a8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c95a8-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c95a8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c95a8-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c95a8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c95a8-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c95a8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c95a8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c95a8-114">See also</span></span>

- [<span data-ttu-id="c95a8-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c95a8-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="c95a8-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c95a8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
