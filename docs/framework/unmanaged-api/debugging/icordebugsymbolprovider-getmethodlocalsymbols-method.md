---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols-Methode
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24671c371ae8a0a9f3c7ca650a71298c69e2fae1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955673"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="23dea-102">ICorDebugSymbolProvider::GetMethodLocalSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="23dea-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="23dea-103">Ruft die lokalen Symbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="23dea-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23dea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23dea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23dea-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23dea-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="23dea-106">[in] Die systemeigene relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="23dea-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="23dea-107">[in] Die Anzahl der angeforderten lokalen Symbole.</span><span class="sxs-lookup"><span data-stu-id="23dea-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="23dea-108">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symbole.</span><span class="sxs-lookup"><span data-stu-id="23dea-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="23dea-109">vorgenommen Ein Zeiger auf ein [icordebugvariablesymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) -Array, das die lokalen Symbole der Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="23dea-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23dea-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23dea-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23dea-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="23dea-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23dea-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23dea-112">Requirements</span></span>  
 <span data-ttu-id="23dea-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23dea-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23dea-114">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="23dea-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23dea-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23dea-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23dea-116">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23dea-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23dea-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23dea-117">See also</span></span>

- [<span data-ttu-id="23dea-118">GetMethodParameterSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="23dea-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="23dea-119">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23dea-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="23dea-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="23dea-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
