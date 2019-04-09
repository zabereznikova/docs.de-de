---
title: ICorDebugMemoryBuffer::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d687f2bbd3c20564368d4246961b56382ea14cf5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099676"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="d06aa-102">ICorDebugMemoryBuffer::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="d06aa-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="d06aa-103">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="d06aa-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d06aa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d06aa-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d06aa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d06aa-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="d06aa-106">[out] Ein Zeiger auf die Größe des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="d06aa-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d06aa-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d06aa-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d06aa-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d06aa-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d06aa-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d06aa-109">Requirements</span></span>  
 <span data-ttu-id="d06aa-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d06aa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d06aa-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d06aa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d06aa-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d06aa-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d06aa-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d06aa-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d06aa-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d06aa-114">See also</span></span>

- [<span data-ttu-id="d06aa-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d06aa-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="d06aa-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d06aa-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
