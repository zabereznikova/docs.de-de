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
ms.openlocfilehash: 97c08e87f63b36bfee5ade75e44f4867441bee92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="2f047-102">ICorDebugMemoryBuffer::GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="2f047-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="2f047-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="2f047-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f047-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f047-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f047-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2f047-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="2f047-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="2f047-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f047-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f047-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="2f047-108">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2f047-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f047-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f047-109">Requirements</span></span>  
 <span data-ttu-id="2f047-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f047-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f047-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f047-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f047-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f047-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f047-113">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f047-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f047-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f047-114">See Also</span></span>  
 [<span data-ttu-id="2f047-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f047-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="2f047-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2f047-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
