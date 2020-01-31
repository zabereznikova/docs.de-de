---
title: ICorDebugMemoryBuffer::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 51c13b67951c714d1aec602ffea22891328565a0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793176"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="8c5a6-102">ICorDebugMemoryBuffer::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="8c5a6-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="8c5a6-103">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="8c5a6-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c5a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c5a6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c5a6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8c5a6-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="8c5a6-106">[out] Ein Zeiger auf die Größe des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="8c5a6-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c5a6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c5a6-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c5a6-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8c5a6-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c5a6-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c5a6-109">Requirements</span></span>  
 <span data-ttu-id="8c5a6-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c5a6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c5a6-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c5a6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c5a6-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c5a6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c5a6-113">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c5a6-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c5a6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c5a6-114">See also</span></span>

- [<span data-ttu-id="8c5a6-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c5a6-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="8c5a6-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8c5a6-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
