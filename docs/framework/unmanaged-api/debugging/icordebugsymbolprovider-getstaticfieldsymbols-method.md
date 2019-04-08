---
title: ICorDebugSymbolProvider::GetStaticFieldSymbols-Methode
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18bfab7a666a4c715b2236f5101bcceacb5b2fed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072687"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="3ed34-102">ICorDebugSymbolProvider::GetStaticFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed34-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="3ed34-103">Ruft die statischen Feldsymbole ab, die einer TypeSpec-Signatur entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3ed34-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ed34-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ed34-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ed34-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ed34-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="3ed34-106">[in] Die Anzahl der Bytes im `typeSig`-Array.</span><span class="sxs-lookup"><span data-stu-id="3ed34-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="3ed34-107">[in] Ein Bytearray, das die `typespec`-Signatur enthält.</span><span class="sxs-lookup"><span data-stu-id="3ed34-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="3ed34-108">[in] Die Anzahl der angeforderten Symbole.</span><span class="sxs-lookup"><span data-stu-id="3ed34-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="3ed34-109">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symbole.</span><span class="sxs-lookup"><span data-stu-id="3ed34-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="3ed34-110">[out] Ein Zeiger auf ein [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) Array, das die angeforderten statischen feldsymbole enthält.</span><span class="sxs-lookup"><span data-stu-id="3ed34-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ed34-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ed34-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ed34-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3ed34-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ed34-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ed34-113">Requirements</span></span>  
 <span data-ttu-id="3ed34-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ed34-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ed34-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ed34-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ed34-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ed34-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3ed34-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="3ed34-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3ed34-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ed34-118">See also</span></span>

- [<span data-ttu-id="3ed34-119">GetInstanceFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed34-119">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="3ed34-120">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ed34-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="3ed34-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3ed34-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
