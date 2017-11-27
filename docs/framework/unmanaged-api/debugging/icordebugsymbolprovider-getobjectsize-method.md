---
title: ICorDebugSymbolProvider::GetObjectSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ea9e0fcae9f98869884ad887a6c24de342512b87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="65b7f-102">ICorDebugSymbolProvider::GetObjectSize-Methode</span><span class="sxs-lookup"><span data-stu-id="65b7f-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="65b7f-103">Gibt die Objektgröße eines Objekts basierend auf seiner TypeSpec-Signatur zurück.</span><span class="sxs-lookup"><span data-stu-id="65b7f-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65b7f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65b7f-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65b7f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="65b7f-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="65b7f-106">[in] Die Anzahl der Bytes in der TypeSpec-Signatur.</span><span class="sxs-lookup"><span data-stu-id="65b7f-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="65b7f-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="65b7f-107">typeSig</span></span>  
 <span data-ttu-id="65b7f-108">[in] Die TypeSpec-Signatur.</span><span class="sxs-lookup"><span data-stu-id="65b7f-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="65b7f-109">[out] Ein Zeiger auf die Größe des Objekts.</span><span class="sxs-lookup"><span data-stu-id="65b7f-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65b7f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65b7f-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65b7f-111">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="65b7f-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65b7f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="65b7f-112">Requirements</span></span>  
 <span data-ttu-id="65b7f-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65b7f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65b7f-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65b7f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65b7f-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65b7f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65b7f-116">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65b7f-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b7f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65b7f-117">See Also</span></span>  
 [<span data-ttu-id="65b7f-118">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65b7f-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="65b7f-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="65b7f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
