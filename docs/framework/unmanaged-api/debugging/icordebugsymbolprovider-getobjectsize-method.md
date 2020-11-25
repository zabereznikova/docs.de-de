---
title: ICorDebugSymbolProvider::GetObjectSize-Methode
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: 4937ff1be7736f98be9efb9b01bdb322bf33e037
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730807"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="6bdcf-102">ICorDebugSymbolProvider::GetObjectSize-Methode</span><span class="sxs-lookup"><span data-stu-id="6bdcf-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>

<span data-ttu-id="6bdcf-103">Gibt die Objektgröße eines Objekts basierend auf seiner TypeSpec-Signatur zurück.</span><span class="sxs-lookup"><span data-stu-id="6bdcf-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bdcf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bdcf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bdcf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6bdcf-105">Parameters</span></span>  

 `cbSignature`  
 <span data-ttu-id="6bdcf-106">[in] Die Anzahl der Bytes in der TypeSpec-Signatur.</span><span class="sxs-lookup"><span data-stu-id="6bdcf-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="6bdcf-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="6bdcf-107">typeSig</span></span>  
 <span data-ttu-id="6bdcf-108">[in] Die TypeSpec-Signatur.</span><span class="sxs-lookup"><span data-stu-id="6bdcf-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="6bdcf-109">[out] Ein Zeiger auf die Größe des Objekts.</span><span class="sxs-lookup"><span data-stu-id="6bdcf-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bdcf-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6bdcf-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6bdcf-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6bdcf-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bdcf-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6bdcf-112">Requirements</span></span>  

 <span data-ttu-id="6bdcf-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bdcf-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bdcf-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6bdcf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bdcf-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bdcf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bdcf-116">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bdcf-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bdcf-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6bdcf-117">See also</span></span>

- [<span data-ttu-id="6bdcf-118">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6bdcf-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6bdcf-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6bdcf-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
