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
ms.openlocfilehash: 58406f3f47e5d6eabd55420dc57148dc7f264726
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="c50f0-102">ICorDebugSymbolProvider::GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="c50f0-102">ICorDebugSymbolProvider::GetMethodProps Method</span></span>
<span data-ttu-id="c50f0-103">Gibt Informationen zu Methodeneigenschaften wie das Metadatentoken der Methode und Informationen zu den generischen Parametern der Methode zurück, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c50f0-103">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c50f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c50f0-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="c50f0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c50f0-105">Parameters</span></span>  
 `codeRVA`  
 <span data-ttu-id="c50f0-106">[in] Eine relative virtuelle Adresse in der Methode, zu der Informationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c50f0-106">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="c50f0-107">[out] Ein Zeiger auf das Metadatentoken der Methode.</span><span class="sxs-lookup"><span data-stu-id="c50f0-107">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="c50f0-108">[out] Ein Zeiger auf die Anzahl der generischen Parameter, die dieser Methode zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c50f0-108">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="c50f0-109">[in] Die Größe des `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="c50f0-109">[in] The size of the `signature` array.</span></span> <span data-ttu-id="c50f0-110">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="c50f0-110">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="c50f0-111">[out] Ein Zeiger auf die Größe des zurückgegebenen `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="c50f0-111">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="c50f0-112">[out] Ein Puffer, der die TypeSpec-Signaturen aller generischen Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="c50f0-112">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c50f0-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c50f0-113">Remarks</span></span>  
 <span data-ttu-id="c50f0-114">Zum Abrufen der erforderlichen Größe der Methode `signature` Arrays, legen Sie die `cbSignature` Argument auf 0 und `signature` auf **null**.</span><span class="sxs-lookup"><span data-stu-id="c50f0-114">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="c50f0-115">Wenn die Methode zurückgegeben wird, enthält `pcbSignature` die Anzahl der für das `signature`-Array erforderlichen Bytes.</span><span class="sxs-lookup"><span data-stu-id="c50f0-115">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c50f0-116">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c50f0-116">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c50f0-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c50f0-117">Requirements</span></span>  
 <span data-ttu-id="c50f0-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c50f0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c50f0-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c50f0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c50f0-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c50f0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c50f0-121">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c50f0-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c50f0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c50f0-122">See Also</span></span>  
 [<span data-ttu-id="c50f0-123">GetTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="c50f0-123">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)  
 [<span data-ttu-id="c50f0-124">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c50f0-124">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="c50f0-125">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c50f0-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
