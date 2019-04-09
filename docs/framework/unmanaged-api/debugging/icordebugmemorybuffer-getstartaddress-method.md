---
title: 'Icordebugmemorybuffer:: Getstartaddress-Methode'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58649a0fc12ce63a1307af5d831dbf5e0d5a776a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136980"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="1577e-102">Icordebugmemorybuffer:: Getstartaddress-Methode</span><span class="sxs-lookup"><span data-stu-id="1577e-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="1577e-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="1577e-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1577e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1577e-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1577e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1577e-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="1577e-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="1577e-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1577e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1577e-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="1577e-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1577e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1577e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1577e-109">Requirements</span></span>  
 <span data-ttu-id="1577e-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1577e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1577e-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1577e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1577e-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1577e-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1577e-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1577e-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1577e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1577e-114">See also</span></span>

- [<span data-ttu-id="1577e-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1577e-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="1577e-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1577e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
