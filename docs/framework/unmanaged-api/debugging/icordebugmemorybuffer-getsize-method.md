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
ms.openlocfilehash: a21198c70512af703e106870d1bc3f7882d62fe9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="bbfa7-102">ICorDebugMemoryBuffer::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="bbfa7-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="bbfa7-103">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="bbfa7-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbfa7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bbfa7-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbfa7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bbfa7-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="bbfa7-106">[out] Ein Zeiger auf die Größe des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="bbfa7-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbfa7-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bbfa7-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbfa7-108">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bbfa7-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbfa7-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bbfa7-109">Requirements</span></span>  
 <span data-ttu-id="bbfa7-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbfa7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbfa7-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbfa7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbfa7-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbfa7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbfa7-113">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbfa7-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbfa7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbfa7-114">See Also</span></span>  
 [<span data-ttu-id="bbfa7-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bbfa7-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="bbfa7-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bbfa7-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
