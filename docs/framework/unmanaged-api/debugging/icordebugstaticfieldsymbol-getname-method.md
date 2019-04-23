---
title: ICorDebugStaticFieldSymbol::GetName-Methode
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5f52999c3f680fbccefe4681f83d473cdb86306
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206485"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="9af47-102">ICorDebugStaticFieldSymbol::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="9af47-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="9af47-103">Ruft den Namen des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="9af47-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9af47-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9af47-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9af47-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9af47-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="9af47-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="9af47-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9af47-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="9af47-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="9af47-108">[out] Ein Array von Zeichen, das den zurückgegebenen Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="9af47-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9af47-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9af47-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9af47-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9af47-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9af47-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9af47-111">Requirements</span></span>  
 <span data-ttu-id="9af47-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9af47-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9af47-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9af47-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9af47-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9af47-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9af47-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9af47-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af47-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9af47-116">See also</span></span>

- [<span data-ttu-id="9af47-117">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9af47-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="9af47-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9af47-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
