---
title: ICorDebugInstanceFieldSymbol::GetName-Methode
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64357f873c9f125712fce33a1d9995c79a8cc006
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533454"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="b5a7d-102">ICorDebugInstanceFieldSymbol::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="b5a7d-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="b5a7d-103">Ruft den Namen des Instanzfelds ab.</span><span class="sxs-lookup"><span data-stu-id="b5a7d-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5a7d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5a7d-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5a7d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5a7d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="b5a7d-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="b5a7d-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b5a7d-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b5a7d-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="b5a7d-108">[out] Ein Array von Zeichen, das den zurückgegebenen Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="b5a7d-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5a7d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5a7d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5a7d-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b5a7d-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5a7d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b5a7d-111">Requirements</span></span>  
 <span data-ttu-id="b5a7d-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5a7d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5a7d-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5a7d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5a7d-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5a7d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5a7d-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5a7d-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5a7d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5a7d-116">See also</span></span>
- [<span data-ttu-id="b5a7d-117">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b5a7d-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="b5a7d-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b5a7d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
