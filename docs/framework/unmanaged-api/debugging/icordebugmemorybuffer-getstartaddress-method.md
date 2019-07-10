---
title: 'Icordebugmemorybuffer:: Getstartaddress-Methode'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9208d07b697c3bb8a99e13582eda70dcb8dd826b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752773"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="bc4c7-102">Icordebugmemorybuffer:: Getstartaddress-Methode</span><span class="sxs-lookup"><span data-stu-id="bc4c7-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="bc4c7-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="bc4c7-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc4c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc4c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc4c7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bc4c7-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="bc4c7-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="bc4c7-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc4c7-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc4c7-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bc4c7-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc4c7-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc4c7-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc4c7-109">Requirements</span></span>  
 <span data-ttu-id="bc4c7-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc4c7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc4c7-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc4c7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc4c7-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc4c7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc4c7-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc4c7-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc4c7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc4c7-114">See also</span></span>

- [<span data-ttu-id="bc4c7-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc4c7-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="bc4c7-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bc4c7-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
