---
title: ICorDebugMemoryBuffer::GetStartAddress-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5519b9dd0d85114e08311e1263c2f2e4ab095ae6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="12372-102">ICorDebugMemoryBuffer::GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="12372-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="12372-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="12372-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12372-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12372-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12372-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="12372-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="12372-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="12372-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12372-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12372-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="12372-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="12372-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12372-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="12372-109">Requirements</span></span>  
 <span data-ttu-id="12372-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12372-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12372-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12372-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12372-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12372-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12372-113">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12372-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12372-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12372-114">See Also</span></span>  
 [<span data-ttu-id="12372-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12372-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="12372-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="12372-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
