---
title: ICorDebugSymbolProvider::GetMethodProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf92727139dc912107484b1e13944c679c944726
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="9efb3-102">ICorDebugSymbolProvider::GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="9efb3-102">ICorDebugSymbolProvider::GetMethodProps Method</span></span>
<span data-ttu-id="9efb3-103">Gibt Informationen zu Methodeneigenschaften wie das Metadatentoken der Methode und Informationen zu den generischen Parametern der Methode zurück, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9efb3-103">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9efb3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9efb3-104">Syntax</span></span>  
  
```  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9efb3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9efb3-105">Parameters</span></span>  
 `codeRVA`  
 <span data-ttu-id="9efb3-106">[in] Eine relative virtuelle Adresse in der Methode, zu der Informationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9efb3-106">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="9efb3-107">[out] Ein Zeiger auf das Metadatentoken der Methode.</span><span class="sxs-lookup"><span data-stu-id="9efb3-107">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="9efb3-108">[out] Ein Zeiger auf die Anzahl der generischen Parameter, die dieser Methode zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9efb3-108">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="9efb3-109">[in] Die Größe des `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="9efb3-109">[in] The size of the `signature` array.</span></span> <span data-ttu-id="9efb3-110">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="9efb3-110">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="9efb3-111">[out] Ein Zeiger auf die Größe des zurückgegebenen `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="9efb3-111">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="9efb3-112">[out] Ein Puffer, der die TypeSpec-Signaturen aller generischen Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="9efb3-112">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9efb3-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9efb3-113">Remarks</span></span>  
 <span data-ttu-id="9efb3-114">Zum Abrufen der erforderlichen Größe der Methode `signature` Arrays, legen Sie die `cbSignature` Argument auf 0 und `signature` auf **null**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-114">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="9efb3-115">Wenn die Methode zurückgegeben wird, enthält `pcbSignature` die Anzahl der für das `signature`-Array erforderlichen Bytes.</span><span class="sxs-lookup"><span data-stu-id="9efb3-115">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9efb3-116">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9efb3-116">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9efb3-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9efb3-117">Requirements</span></span>  
 <span data-ttu-id="9efb3-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9efb3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9efb3-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9efb3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9efb3-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9efb3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9efb3-121">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9efb3-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efb3-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9efb3-122">See Also</span></span>  
 [<span data-ttu-id="9efb3-123">GetTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="9efb3-123">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)  
 [<span data-ttu-id="9efb3-124">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9efb3-124">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="9efb3-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9efb3-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
