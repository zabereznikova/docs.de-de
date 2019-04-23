---
title: 'Icordebugmemorybuffer:: Getstartaddress-Methode'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58649a0fc12ce63a1307af5d831dbf5e0d5a776a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136980"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="c4b92-102">Icordebugmemorybuffer:: Getstartaddress-Methode</span><span class="sxs-lookup"><span data-stu-id="c4b92-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="c4b92-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="c4b92-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4b92-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4b92-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4b92-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c4b92-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="c4b92-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4b92-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4b92-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c4b92-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c4b92-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4b92-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4b92-109">Requirements</span></span>  
 <span data-ttu-id="c4b92-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4b92-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4b92-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4b92-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4b92-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4b92-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4b92-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4b92-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b92-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4b92-114">See also</span></span>

- [<span data-ttu-id="c4b92-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4b92-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="c4b92-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c4b92-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
