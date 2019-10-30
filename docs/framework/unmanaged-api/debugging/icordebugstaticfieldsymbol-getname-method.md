---
title: 'Icordebugstaticfieldsymbol:: GetName-Methode'
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: e961ae064bd5bb2c97175b4506ddd8c0f17d3b32
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131785"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="c4bde-102">Icordebugstaticfieldsymbol:: GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="c4bde-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="c4bde-103">Ruft den Namen des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="c4bde-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4bde-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4bde-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4bde-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4bde-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="c4bde-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="c4bde-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c4bde-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c4bde-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="c4bde-108">[out] Ein Array von Zeichen, das den zurückgegebenen Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="c4bde-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4bde-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4bde-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4bde-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c4bde-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4bde-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4bde-111">Requirements</span></span>  
 <span data-ttu-id="c4bde-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4bde-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4bde-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4bde-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4bde-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4bde-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4bde-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4bde-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4bde-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4bde-116">See also</span></span>

- [<span data-ttu-id="c4bde-117">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4bde-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="c4bde-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c4bde-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
