---
title: 'Icordebugstaticfieldsymbol:: GetAddress-Methode'
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: 65761e48491b2a4c81ccd05b17d8723f71f52e5c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131796"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="c5ac9-102">Icordebugstaticfieldsymbol:: GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="c5ac9-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="c5ac9-103">Ruft die Adresse eines statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="c5ac9-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5ac9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5ac9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5ac9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5ac9-105">Parameters</span></span>  
 <span data-ttu-id="c5ac9-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="c5ac9-106">pRVA</span></span>  
 <span data-ttu-id="c5ac9-107">[out] Ein Zeiger auf die relative virtuelle Adresse (RVA) des statischen Felds.</span><span class="sxs-lookup"><span data-stu-id="c5ac9-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5ac9-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5ac9-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5ac9-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c5ac9-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5ac9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c5ac9-110">Requirements</span></span>  
 <span data-ttu-id="c5ac9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5ac9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5ac9-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5ac9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5ac9-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5ac9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5ac9-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5ac9-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5ac9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5ac9-115">See also</span></span>

- [<span data-ttu-id="c5ac9-116">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5ac9-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="c5ac9-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c5ac9-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
