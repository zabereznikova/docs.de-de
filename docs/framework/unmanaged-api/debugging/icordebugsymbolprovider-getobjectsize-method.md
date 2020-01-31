---
title: ICorDebugSymbolProvider::GetObjectSize-Methode
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: fce7410b5ae9571af0c8a5963596e2af41737798
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791572"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="a6613-102">ICorDebugSymbolProvider::GetObjectSize-Methode</span><span class="sxs-lookup"><span data-stu-id="a6613-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="a6613-103">Gibt die Objektgröße eines Objekts basierend auf seiner TypeSpec-Signatur zurück.</span><span class="sxs-lookup"><span data-stu-id="a6613-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6613-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6613-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6613-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="a6613-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="a6613-106">[in] Die Anzahl der Bytes in der TypeSpec-Signatur.</span><span class="sxs-lookup"><span data-stu-id="a6613-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="a6613-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="a6613-107">typeSig</span></span>  
 <span data-ttu-id="a6613-108">[in] Die TypeSpec-Signatur.</span><span class="sxs-lookup"><span data-stu-id="a6613-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="a6613-109">[out] Ein Zeiger auf die Größe des Objekts.</span><span class="sxs-lookup"><span data-stu-id="a6613-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6613-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6613-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6613-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a6613-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6613-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a6613-112">Requirements</span></span>  
 <span data-ttu-id="a6613-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6613-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6613-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6613-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6613-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6613-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6613-116">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6613-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6613-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6613-117">See also</span></span>

- [<span data-ttu-id="a6613-118">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a6613-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a6613-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a6613-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
