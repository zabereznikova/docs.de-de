---
title: ICorDebugSymbolProvider::GetStaticFieldSymbols-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3871a74ee2844835c09a6e395fd63536c7442261
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="8a8eb-102">ICorDebugSymbolProvider::GetStaticFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="8a8eb-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="8a8eb-103">Ruft die statischen Feldsymbole ab, die einer typespec-Signatur entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8a8eb-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a8eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a8eb-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a8eb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a8eb-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="8a8eb-106">[in] Die Anzahl der Bytes im `typeSig`-Array.</span><span class="sxs-lookup"><span data-stu-id="8a8eb-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="8a8eb-107">[in] Ein Bytearray, das die `typespec`-Signatur enthält.</span><span class="sxs-lookup"><span data-stu-id="8a8eb-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="8a8eb-108">[in] Die Anzahl der angeforderten Symbole.</span><span class="sxs-lookup"><span data-stu-id="8a8eb-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="8a8eb-109">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symbole.</span><span class="sxs-lookup"><span data-stu-id="8a8eb-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="8a8eb-110">[out] Ein Zeiger auf ein [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) Array, das die angeforderten statischen feldsymbole enthält.</span><span class="sxs-lookup"><span data-stu-id="8a8eb-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a8eb-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a8eb-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a8eb-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8a8eb-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a8eb-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a8eb-113">Requirements</span></span>  
 <span data-ttu-id="8a8eb-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a8eb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a8eb-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a8eb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a8eb-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a8eb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a8eb-117">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a8eb-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a8eb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a8eb-118">See Also</span></span>  
 [<span data-ttu-id="8a8eb-119">GetInstanceFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="8a8eb-119">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)  
 [<span data-ttu-id="8a8eb-120">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a8eb-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="8a8eb-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8a8eb-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
