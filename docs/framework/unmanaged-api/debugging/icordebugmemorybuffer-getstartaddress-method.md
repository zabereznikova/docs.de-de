---
title: ICorDebugMemoryBuffer::GetStartAddress-Methode
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1aa816ea9e6185791e09bcdb0e47c50761a5ebc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422932"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="b0610-102">ICorDebugMemoryBuffer::GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="b0610-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="b0610-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="b0610-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0610-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0610-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0610-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b0610-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="b0610-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="b0610-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0610-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0610-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="b0610-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b0610-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0610-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b0610-109">Requirements</span></span>  
 <span data-ttu-id="b0610-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0610-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0610-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0610-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0610-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0610-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0610-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0610-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0610-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0610-114">See Also</span></span>  
 [<span data-ttu-id="b0610-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b0610-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="b0610-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b0610-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
