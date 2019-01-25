---
title: ICorDebugStaticFieldSymbol::GetName-Methode
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6da390fb7de3c248fa5389f133d65f9914d5260a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714693"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="ae125-102">ICorDebugStaticFieldSymbol::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="ae125-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="ae125-103">Ruft den Namen des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="ae125-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae125-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae125-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae125-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ae125-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="ae125-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="ae125-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ae125-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ae125-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="ae125-108">[out] Ein Array von Zeichen, das den zurückgegebenen Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="ae125-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae125-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ae125-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae125-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ae125-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae125-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ae125-111">Requirements</span></span>  
 <span data-ttu-id="ae125-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae125-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae125-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae125-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae125-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae125-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae125-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae125-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae125-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae125-116">See also</span></span>
- [<span data-ttu-id="ae125-117">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ae125-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="ae125-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ae125-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
