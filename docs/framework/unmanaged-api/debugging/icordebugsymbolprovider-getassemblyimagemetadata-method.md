---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata-Methode
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0be0722db374ff49541b3c4b68f295774f34163e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953451"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="048e2-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata-Methode</span><span class="sxs-lookup"><span data-stu-id="048e2-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="048e2-103">Gibt die Metadaten aus einer zusammengeführten Assembly zurück.</span><span class="sxs-lookup"><span data-stu-id="048e2-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="048e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="048e2-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="048e2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="048e2-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="048e2-106">[out] Ein Zeiger auf die Adresse einer [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) -Objekt, das Informationen über die Größe und die Adresse der Metadaten der zusammengeführten Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="048e2-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="048e2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="048e2-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="048e2-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="048e2-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="048e2-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="048e2-109">Requirements</span></span>  
 <span data-ttu-id="048e2-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="048e2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="048e2-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="048e2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="048e2-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="048e2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="048e2-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="048e2-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="048e2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="048e2-114">See also</span></span>

- [<span data-ttu-id="048e2-115">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="048e2-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="048e2-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="048e2-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
