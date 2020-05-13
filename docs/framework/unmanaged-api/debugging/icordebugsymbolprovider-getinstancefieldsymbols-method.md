---
title: ICorDebugSymbolProvider::GetInstanceFieldSymbols-Methode
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 9ecc61ed6cac73a519f33e00cbfbfecc20ac2ebe
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379634"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="1c21c-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="1c21c-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="1c21c-103">Ruft die Instanzenfeldsymbole ab, die einer TypeSpec-Signatur entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1c21c-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c21c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c21c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c21c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c21c-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="1c21c-106">[in] Die Anzahl der Bytes im `typeSig`-Array.</span><span class="sxs-lookup"><span data-stu-id="1c21c-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="1c21c-107">[in] Ein Bytearray, das die `typespec`-Signatur enthält.</span><span class="sxs-lookup"><span data-stu-id="1c21c-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="1c21c-108">[in] Die Anzahl der angeforderten Symbole.</span><span class="sxs-lookup"><span data-stu-id="1c21c-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="1c21c-109">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symbole.</span><span class="sxs-lookup"><span data-stu-id="1c21c-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="1c21c-110">vorgenommen Ein Zeiger auf ein [icordebugstaticfieldsymbol](icordebugstaticfieldsymbol-interface.md) -Array, das die angeforderten instanzfeldsymbole enthält.</span><span class="sxs-lookup"><span data-stu-id="1c21c-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c21c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c21c-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c21c-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1c21c-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c21c-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1c21c-113">Requirements</span></span>  
 <span data-ttu-id="1c21c-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c21c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c21c-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c21c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c21c-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c21c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c21c-117">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c21c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c21c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c21c-118">See also</span></span>

- [<span data-ttu-id="1c21c-119">GetStaticFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="1c21c-119">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="1c21c-120">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c21c-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="1c21c-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1c21c-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
