---
title: ICorDebugMemoryBuffer::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caf95e0b5c8d4ae942bb428f53d4e58313e0e78e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414751"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="7ea3e-102">ICorDebugMemoryBuffer::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="7ea3e-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="7ea3e-103">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="7ea3e-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ea3e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ea3e-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ea3e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ea3e-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="7ea3e-106">[out] Ein Zeiger auf die Größe des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="7ea3e-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ea3e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ea3e-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ea3e-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7ea3e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ea3e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ea3e-109">Requirements</span></span>  
 <span data-ttu-id="7ea3e-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ea3e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ea3e-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ea3e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ea3e-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ea3e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ea3e-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ea3e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea3e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ea3e-114">See Also</span></span>  
 [<span data-ttu-id="7ea3e-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ea3e-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="7ea3e-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7ea3e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
