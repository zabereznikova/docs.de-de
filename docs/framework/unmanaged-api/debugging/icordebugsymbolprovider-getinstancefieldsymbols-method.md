---
title: ICorDebugSymbolProvider::GetInstanceFieldSymbols-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2ddb0b9e10314d027d342b34542129fbcdfb075
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="90f14-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="90f14-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="90f14-103">Ruft die Instanzenfeldsymbole ab, die einer TypeSpec-Signatur entsprechen.</span><span class="sxs-lookup"><span data-stu-id="90f14-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90f14-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90f14-104">Syntax</span></span>  
  
```  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90f14-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="90f14-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="90f14-106">[in] Die Anzahl der Bytes im `typeSig`-Array.</span><span class="sxs-lookup"><span data-stu-id="90f14-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="90f14-107">[in] Ein Bytearray, das die `typespec`-Signatur enthält.</span><span class="sxs-lookup"><span data-stu-id="90f14-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="90f14-108">[in] Die Anzahl der angeforderten Symbole.</span><span class="sxs-lookup"><span data-stu-id="90f14-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="90f14-109">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symbole.</span><span class="sxs-lookup"><span data-stu-id="90f14-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="90f14-110">[out] Ein Zeiger auf ein [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) Array, das die angeforderten instanzenfeldsymbole enthält.</span><span class="sxs-lookup"><span data-stu-id="90f14-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90f14-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90f14-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90f14-112">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="90f14-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90f14-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90f14-113">Requirements</span></span>  
 <span data-ttu-id="90f14-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90f14-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90f14-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90f14-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90f14-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90f14-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90f14-117">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90f14-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90f14-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90f14-118">See Also</span></span>  
 [<span data-ttu-id="90f14-119">GetStaticFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="90f14-119">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)  
 [<span data-ttu-id="90f14-120">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90f14-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="90f14-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="90f14-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
