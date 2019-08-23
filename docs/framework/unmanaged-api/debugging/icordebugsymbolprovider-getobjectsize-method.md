---
title: ICorDebugSymbolProvider::GetObjectSize-Methode
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59054d7b939ab29cb08c30961601a323529ce06b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955630"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="30360-102">ICorDebugSymbolProvider::GetObjectSize-Methode</span><span class="sxs-lookup"><span data-stu-id="30360-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="30360-103">Gibt die Objektgröße eines Objekts basierend auf seiner TypeSpec-Signatur zurück.</span><span class="sxs-lookup"><span data-stu-id="30360-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30360-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30360-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30360-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="30360-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="30360-106">[in] Die Anzahl der Bytes in der TypeSpec-Signatur.</span><span class="sxs-lookup"><span data-stu-id="30360-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="30360-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="30360-107">typeSig</span></span>  
 <span data-ttu-id="30360-108">[in] Die TypeSpec-Signatur.</span><span class="sxs-lookup"><span data-stu-id="30360-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="30360-109">[out] Ein Zeiger auf die Größe des Objekts.</span><span class="sxs-lookup"><span data-stu-id="30360-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30360-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30360-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30360-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="30360-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30360-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30360-112">Requirements</span></span>  
 <span data-ttu-id="30360-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30360-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30360-114">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="30360-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30360-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30360-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30360-116">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30360-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30360-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30360-117">See also</span></span>

- [<span data-ttu-id="30360-118">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30360-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="30360-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="30360-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
