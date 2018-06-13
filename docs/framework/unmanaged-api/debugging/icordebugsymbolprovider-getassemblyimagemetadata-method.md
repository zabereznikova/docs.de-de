---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata-Methode
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bf032f3bf525d2dca535e6f62dd65d5acd8e7f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420988"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="d5642-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata-Methode</span><span class="sxs-lookup"><span data-stu-id="d5642-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="d5642-103">Gibt die Metadaten aus einer zusammengeführten Assembly zurück.</span><span class="sxs-lookup"><span data-stu-id="d5642-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5642-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5642-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5642-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5642-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="d5642-106">[out] Ein Zeiger auf die Adresse des ein [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) -Objekt, das Informationen über die Größe und die Adresse der Metadaten der zusammengeführten Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="d5642-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5642-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5642-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5642-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d5642-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5642-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5642-109">Requirements</span></span>  
 <span data-ttu-id="d5642-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5642-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5642-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5642-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5642-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5642-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5642-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5642-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5642-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5642-114">See Also</span></span>  
 [<span data-ttu-id="d5642-115">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5642-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="d5642-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d5642-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
