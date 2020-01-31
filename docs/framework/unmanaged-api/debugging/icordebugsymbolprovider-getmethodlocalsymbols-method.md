---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols-Methode
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: 41fc8e94ec8a5c8794674bebb32494bb3806e69d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791607"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="1d873-102">ICorDebugSymbolProvider::GetMethodLocalSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="1d873-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="1d873-103">Ruft die lokalen Symbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="1d873-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d873-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d873-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d873-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="1d873-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="1d873-106">[in] Die systemeigene relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="1d873-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="1d873-107">[in] Die Anzahl der angeforderten lokalen Symbole.</span><span class="sxs-lookup"><span data-stu-id="1d873-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="1d873-108">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symbole.</span><span class="sxs-lookup"><span data-stu-id="1d873-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="1d873-109">vorgenommen Ein Zeiger auf ein [icordebugvariablesymbol](icordebugvariablesymbol-interface.md) -Array, das die lokalen Symbole der Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="1d873-109">[out] A pointer to an [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d873-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d873-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d873-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1d873-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d873-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1d873-112">Requirements</span></span>  
 <span data-ttu-id="1d873-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d873-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d873-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d873-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d873-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d873-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d873-116">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d873-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d873-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d873-117">See also</span></span>

- [<span data-ttu-id="1d873-118">GetMethodParameterSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="1d873-118">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="1d873-119">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d873-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="1d873-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1d873-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
