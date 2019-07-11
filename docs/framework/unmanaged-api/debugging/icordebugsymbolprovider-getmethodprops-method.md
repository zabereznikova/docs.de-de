---
title: ICorDebugSymbolProvider::GetMethodProps-Methode
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f6971c7991f5e54973d96d9b3f662b54be564d9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771334"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="0832f-102">ICorDebugSymbolProvider::GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="0832f-102">ICorDebugSymbolProvider::GetMethodProps Method</span></span>
<span data-ttu-id="0832f-103">Gibt Informationen zu Methodeneigenschaften wie das Metadatentoken der Methode und Informationen zu den generischen Parametern der Methode zurück, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="0832f-103">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0832f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0832f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0832f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0832f-105">Parameters</span></span>  
 `codeRVA`  
 <span data-ttu-id="0832f-106">[in] Eine relative virtuelle Adresse in der Methode, zu der Informationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0832f-106">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="0832f-107">[out] Ein Zeiger auf das Metadatentoken der Methode.</span><span class="sxs-lookup"><span data-stu-id="0832f-107">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="0832f-108">[out] Ein Zeiger auf die Anzahl der generischen Parameter, die dieser Methode zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0832f-108">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="0832f-109">[in] Die Größe des `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="0832f-109">[in] The size of the `signature` array.</span></span> <span data-ttu-id="0832f-110">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="0832f-110">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="0832f-111">[out] Ein Zeiger auf die Größe des zurückgegebenen `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="0832f-111">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="0832f-112">[out] Ein Puffer, der die TypeSpec-Signaturen aller generischen Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="0832f-112">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0832f-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0832f-113">Remarks</span></span>  
 <span data-ttu-id="0832f-114">Zum Abrufen der erforderlichen Größe von der Methode `signature` Arrays, legen Sie die `cbSignature` Argument auf 0 und `signature` zu **null**.</span><span class="sxs-lookup"><span data-stu-id="0832f-114">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="0832f-115">Wenn die Methode zurückgegeben wird, enthält `pcbSignature` die Anzahl der für das `signature`-Array erforderlichen Bytes.</span><span class="sxs-lookup"><span data-stu-id="0832f-115">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0832f-116">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0832f-116">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0832f-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0832f-117">Requirements</span></span>  
 <span data-ttu-id="0832f-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0832f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0832f-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0832f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0832f-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0832f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0832f-121">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0832f-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0832f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0832f-122">See also</span></span>

- [<span data-ttu-id="0832f-123">GetTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="0832f-123">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)
- [<span data-ttu-id="0832f-124">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0832f-124">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="0832f-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0832f-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
