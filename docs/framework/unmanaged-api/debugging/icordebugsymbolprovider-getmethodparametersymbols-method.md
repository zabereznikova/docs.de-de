---
title: ICorDebugSymbolProvider::GetMethodParameterSymbols-Methode
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be103b8f9d6f94d5b7a265ec2ef01c551622c9e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714294"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="dbca8-102">ICorDebugSymbolProvider::GetMethodParameterSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="dbca8-102">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>
<span data-ttu-id="dbca8-103">Ruft die Parametersymbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="dbca8-103">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbca8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbca8-104">Syntax</span></span>  
  
```  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbca8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dbca8-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="dbca8-106">[in] Die systemeigene relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="dbca8-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="dbca8-107">[in] Die Anzahl der angeforderten lokalen Symbole.</span><span class="sxs-lookup"><span data-stu-id="dbca8-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="dbca8-108">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symbole.</span><span class="sxs-lookup"><span data-stu-id="dbca8-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="dbca8-109">[out] Ein Zeiger auf ein [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) Array, das lokale Symbole der Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="dbca8-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbca8-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dbca8-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbca8-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dbca8-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbca8-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbca8-112">Requirements</span></span>  
 <span data-ttu-id="dbca8-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbca8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbca8-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbca8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbca8-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbca8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbca8-116">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbca8-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbca8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbca8-117">See also</span></span>
- [<span data-ttu-id="dbca8-118">GetMethodLocalSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="dbca8-118">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [<span data-ttu-id="dbca8-119">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbca8-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="dbca8-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dbca8-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
