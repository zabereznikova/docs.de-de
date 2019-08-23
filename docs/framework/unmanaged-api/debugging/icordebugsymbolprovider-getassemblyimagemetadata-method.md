---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata-Methode
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad86c42d0f23de25fe0e5b9123a0dba3695d8d64
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964659"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="9b046-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata-Methode</span><span class="sxs-lookup"><span data-stu-id="9b046-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="9b046-103">Gibt die Metadaten aus einer zusammengeführten Assembly zurück.</span><span class="sxs-lookup"><span data-stu-id="9b046-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b046-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b046-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b046-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b046-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="9b046-106">vorgenommen Ein Zeiger auf die Adresse eines [icordebugmemorybuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) -Objekts, das Informationen über die Größe und die Adresse der Metadaten der zusammengeführten Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="9b046-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b046-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b046-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b046-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9b046-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b046-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b046-109">Requirements</span></span>  
 <span data-ttu-id="9b046-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b046-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b046-111">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="9b046-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b046-112">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b046-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b046-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b046-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b046-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b046-114">See also</span></span>

- [<span data-ttu-id="9b046-115">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b046-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="9b046-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9b046-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
