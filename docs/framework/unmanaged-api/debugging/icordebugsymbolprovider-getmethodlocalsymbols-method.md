---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c07151c4cdd43df17025deff4af37a0156ecaf78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="03609-102">ICorDebugSymbolProvider::GetMethodLocalSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="03609-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="03609-103">Ruft die lokalen Symbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="03609-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03609-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03609-104">Syntax</span></span>  
  
```  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03609-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="03609-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="03609-106">[in] Die systemeigene relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="03609-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="03609-107">[in] Die Anzahl der angeforderten lokalen Symbole.</span><span class="sxs-lookup"><span data-stu-id="03609-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="03609-108">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symbole.</span><span class="sxs-lookup"><span data-stu-id="03609-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="03609-109">[out] Ein Zeiger auf ein [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) Array, das die Methode lokale Symbole enthält.</span><span class="sxs-lookup"><span data-stu-id="03609-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03609-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03609-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03609-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="03609-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03609-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="03609-112">Requirements</span></span>  
 <span data-ttu-id="03609-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03609-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03609-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03609-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03609-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03609-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03609-116">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03609-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03609-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03609-117">See Also</span></span>  
 [<span data-ttu-id="03609-118">GetMethodParameterSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="03609-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)  
 [<span data-ttu-id="03609-119">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="03609-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="03609-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="03609-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
