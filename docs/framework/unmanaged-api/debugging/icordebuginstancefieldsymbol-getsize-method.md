---
title: 'Icordebuginstancefieldsymbol:: GetSize-Methode'
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: 71828cd8486e2ff09190d23473dbab303b92f933
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139018"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="eeadd-102">Icordebuginstancefieldsymbol:: GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="eeadd-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="eeadd-103">Ruft die Größe des Instanzfelds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="eeadd-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeadd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eeadd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eeadd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eeadd-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="eeadd-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="eeadd-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eeadd-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eeadd-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eeadd-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eeadd-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeadd-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eeadd-109">Requirements</span></span>  
 <span data-ttu-id="eeadd-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eeadd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeadd-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eeadd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eeadd-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eeadd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eeadd-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeadd-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeadd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eeadd-114">See also</span></span>

- [<span data-ttu-id="eeadd-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eeadd-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="eeadd-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="eeadd-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
