---
title: ICorDebugSymbolProvider::GetTypeProps-Methode
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e21273506e91c5ab69b1b0b4a52d6c0f72692dab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712771"
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a><span data-ttu-id="b9f4b-102">ICorDebugSymbolProvider::GetTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="b9f4b-102">ICorDebugSymbolProvider::GetTypeProps Method</span></span>
<span data-ttu-id="b9f4b-103">Gibt Informationen zu den Eigenschaften eines Typs wie die Anzahl der Signaturen der generischen Parameter zurück, wenn eine relative virtuelle Adresse (RVA) in einer Vtable angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="b9f4b-103">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9f4b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9f4b-104">Syntax</span></span>  
  
```  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9f4b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b9f4b-105">Parameters</span></span>  
 `tableRva`  
 <span data-ttu-id="b9f4b-106">[in] Eine relative virtuelle Adresse (RVA) in einem VTable.</span><span class="sxs-lookup"><span data-stu-id="b9f4b-106">[in] A relative virtual address (RVA) in a vtable.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="b9f4b-107">[in] Die Größe des `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="b9f4b-107">[in] The size of the `signature` array.</span></span> <span data-ttu-id="b9f4b-108">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="b9f4b-108">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="b9f4b-109">[out] [out] Ein Zeiger auf die Größe des zurückgegebenen `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="b9f4b-109">[out] [out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="b9f4b-110">[out] Ein Puffer, der die TypeSpec-Signaturen aller generischen Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="b9f4b-110">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9f4b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9f4b-111">Remarks</span></span>  
 <span data-ttu-id="b9f4b-112">Zum Abrufen der erforderlichen Größe des Typs `signature` Arrays, legen Sie die `cbSignature` Argument auf 0 und `signature` zu **null**.</span><span class="sxs-lookup"><span data-stu-id="b9f4b-112">To get the required size of the type's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="b9f4b-113">Wenn die Methode zurückgegeben wird, enthält `pcbSignature` die Anzahl der für das `signature`-Array erforderlichen Bytes.</span><span class="sxs-lookup"><span data-stu-id="b9f4b-113">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9f4b-114">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b9f4b-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9f4b-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9f4b-115">Requirements</span></span>  
 <span data-ttu-id="b9f4b-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9f4b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9f4b-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9f4b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9f4b-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9f4b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9f4b-119">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9f4b-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f4b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9f4b-120">See also</span></span>
- [<span data-ttu-id="b9f4b-121">GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="b9f4b-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)
- [<span data-ttu-id="b9f4b-122">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9f4b-122">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="b9f4b-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b9f4b-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
