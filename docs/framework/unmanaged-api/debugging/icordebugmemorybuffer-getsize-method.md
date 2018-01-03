---
title: ICorDebugMemoryBuffer::GetSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 658fb2ce289b4b8cabfcf0cc2ea5f8dace2ec754
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="67ae8-102">ICorDebugMemoryBuffer::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="67ae8-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="67ae8-103">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="67ae8-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67ae8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67ae8-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67ae8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67ae8-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="67ae8-106">[out] Ein Zeiger auf die Größe des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="67ae8-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67ae8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67ae8-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67ae8-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="67ae8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67ae8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67ae8-109">Requirements</span></span>  
 <span data-ttu-id="67ae8-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67ae8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67ae8-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67ae8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67ae8-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67ae8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67ae8-113">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67ae8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ae8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67ae8-114">See Also</span></span>  
 [<span data-ttu-id="67ae8-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67ae8-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="67ae8-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="67ae8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
