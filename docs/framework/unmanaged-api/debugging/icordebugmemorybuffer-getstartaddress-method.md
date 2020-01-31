---
title: ICorDebugMemoryBuffer::GetStartAddress-Methode
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f2b09c847a6bf577b78c8155f85f07b93877fbe9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793168"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="af56a-102">ICorDebugMemoryBuffer::GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="af56a-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="af56a-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="af56a-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af56a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af56a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af56a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="af56a-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="af56a-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="af56a-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af56a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af56a-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="af56a-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="af56a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af56a-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af56a-109">Requirements</span></span>  
 <span data-ttu-id="af56a-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af56a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af56a-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af56a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af56a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af56a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af56a-113">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af56a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af56a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af56a-114">See also</span></span>

- [<span data-ttu-id="af56a-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af56a-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="af56a-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="af56a-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
