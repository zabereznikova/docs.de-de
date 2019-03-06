---
title: ICorDebugMemoryBuffer::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fdf5e6e52b0c650e56368493074ea7db8e5bac9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485433"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="7e846-102">ICorDebugMemoryBuffer::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="7e846-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="7e846-103">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="7e846-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e846-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e846-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e846-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7e846-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="7e846-106">[out] Ein Zeiger auf die Größe des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="7e846-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e846-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e846-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e846-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7e846-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e846-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7e846-109">Requirements</span></span>  
 <span data-ttu-id="7e846-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e846-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e846-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e846-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e846-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e846-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e846-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e846-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e846-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e846-114">See also</span></span>
- [<span data-ttu-id="7e846-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e846-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="7e846-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7e846-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
