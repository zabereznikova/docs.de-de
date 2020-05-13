---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols-Methode
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: 7e9aa01a3fa1c90b0ab4f85970c4eb294b9a4904
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379609"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="45765-102">ICorDebugSymbolProvider::GetMethodLocalSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="45765-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="45765-103">Ruft die lokalen Symbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="45765-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45765-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45765-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45765-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45765-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="45765-106">[in] Die systemeigene relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="45765-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="45765-107">[in] Die Anzahl der angeforderten lokalen Symbole.</span><span class="sxs-lookup"><span data-stu-id="45765-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="45765-108">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symbole.</span><span class="sxs-lookup"><span data-stu-id="45765-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="45765-109">vorgenommen Ein Zeiger auf ein [icordebugvariablesymbol](icordebugvariablesymbol-interface.md) -Array, das die lokalen Symbole der Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="45765-109">[out] A pointer to an [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45765-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45765-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="45765-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="45765-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45765-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="45765-112">Requirements</span></span>  
 <span data-ttu-id="45765-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45765-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45765-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45765-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45765-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45765-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45765-116">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45765-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45765-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45765-117">See also</span></span>

- [<span data-ttu-id="45765-118">GetMethodParameterSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="45765-118">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="45765-119">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45765-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="45765-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="45765-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
