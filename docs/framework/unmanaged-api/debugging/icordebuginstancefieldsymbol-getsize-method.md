---
title: ICorDebugInstanceFieldSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04d866888c15585ff5058f870257b317ac888be7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696983"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="69cc6-102">ICorDebugInstanceFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="69cc6-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="69cc6-103">Ruft die Größe des Instanzfelds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="69cc6-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69cc6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69cc6-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69cc6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="69cc6-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="69cc6-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="69cc6-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69cc6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="69cc6-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69cc6-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="69cc6-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69cc6-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="69cc6-109">Requirements</span></span>  
 <span data-ttu-id="69cc6-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69cc6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69cc6-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69cc6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69cc6-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69cc6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69cc6-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69cc6-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69cc6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69cc6-114">See also</span></span>
- [<span data-ttu-id="69cc6-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69cc6-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="69cc6-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="69cc6-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
