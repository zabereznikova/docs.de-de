---
title: ICorDebugSymbolProvider::GetStaticFieldSymbols-Methode
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7d5195215762c25b2d7dc2b71fcd53959656303
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420894"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="e621f-102">ICorDebugSymbolProvider::GetStaticFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="e621f-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="e621f-103">Ruft die statischen Feldsymbole ab, die einer typespec-Signatur entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e621f-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e621f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e621f-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e621f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e621f-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="e621f-106">[in] Die Anzahl der Bytes im `typeSig`-Array.</span><span class="sxs-lookup"><span data-stu-id="e621f-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="e621f-107">[in] Ein Bytearray, das die `typespec`-Signatur enthält.</span><span class="sxs-lookup"><span data-stu-id="e621f-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="e621f-108">[in] Die Anzahl der angeforderten Symbole.</span><span class="sxs-lookup"><span data-stu-id="e621f-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="e621f-109">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symbole.</span><span class="sxs-lookup"><span data-stu-id="e621f-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="e621f-110">[out] Ein Zeiger auf ein [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) Array, das die angeforderten statischen feldsymbole enthält.</span><span class="sxs-lookup"><span data-stu-id="e621f-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e621f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e621f-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e621f-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e621f-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e621f-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e621f-113">Requirements</span></span>  
 <span data-ttu-id="e621f-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e621f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e621f-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e621f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e621f-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e621f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e621f-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e621f-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e621f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e621f-118">See Also</span></span>  
 [<span data-ttu-id="e621f-119">GetInstanceFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="e621f-119">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)  
 [<span data-ttu-id="e621f-120">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e621f-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="e621f-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e621f-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
