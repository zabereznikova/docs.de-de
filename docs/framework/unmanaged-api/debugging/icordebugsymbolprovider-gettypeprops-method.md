---
title: ICorDebugSymbolProvider::GetTypeProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ba736caf8d8d823a4cb56c75aa2202ad616983fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a><span data-ttu-id="d8da5-102">ICorDebugSymbolProvider::GetTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="d8da5-102">ICorDebugSymbolProvider::GetTypeProps Method</span></span>
<span data-ttu-id="d8da5-103">Gibt Informationen zu den Eigenschaften eines Typs wie die Anzahl der Signaturen der generischen Parameter zurück, wenn eine relative virtuelle Adresse (RVA) in einer Vtable angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d8da5-103">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8da5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8da5-104">Syntax</span></span>  
  
```  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8da5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d8da5-105">Parameters</span></span>  
 `tableRva`  
 <span data-ttu-id="d8da5-106">[in] Eine relative virtuelle Adresse (RVA) in einem VTable.</span><span class="sxs-lookup"><span data-stu-id="d8da5-106">[in] A relative virtual address (RVA) in a vtable.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="d8da5-107">[in] Die Größe des `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="d8da5-107">[in] The size of the `signature` array.</span></span> <span data-ttu-id="d8da5-108">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="d8da5-108">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="d8da5-109">[out] [out] Ein Zeiger auf die Größe des zurückgegebenen `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="d8da5-109">[out] [out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="d8da5-110">[out] Ein Puffer, der die TypeSpec-Signaturen aller generischen Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="d8da5-110">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8da5-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8da5-111">Remarks</span></span>  
 <span data-ttu-id="d8da5-112">Zum Abrufen der erforderlichen Größe des Typs `signature` Arrays, legen Sie die `cbSignature` Argument auf 0 und `signature` auf **null**.</span><span class="sxs-lookup"><span data-stu-id="d8da5-112">To get the required size of the type's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="d8da5-113">Wenn die Methode zurückgegeben wird, enthält `pcbSignature` die Anzahl der für das `signature`-Array erforderlichen Bytes.</span><span class="sxs-lookup"><span data-stu-id="d8da5-113">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8da5-114">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d8da5-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8da5-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d8da5-115">Requirements</span></span>  
 <span data-ttu-id="d8da5-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8da5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8da5-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8da5-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8da5-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8da5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8da5-119">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8da5-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8da5-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8da5-120">See Also</span></span>  
 [<span data-ttu-id="d8da5-121">GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="d8da5-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)  
 [<span data-ttu-id="d8da5-122">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8da5-122">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="d8da5-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d8da5-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
