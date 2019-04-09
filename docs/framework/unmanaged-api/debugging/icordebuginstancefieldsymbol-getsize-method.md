---
title: ICorDebugInstanceFieldSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cc09de2120399dcfe309757d554e1de72e55f07
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081449"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="df966-102">ICorDebugInstanceFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="df966-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="df966-103">Ruft die Größe des Instanzfelds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="df966-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df966-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df966-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df966-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df966-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="df966-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="df966-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df966-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df966-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df966-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="df966-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df966-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="df966-109">Requirements</span></span>  
 <span data-ttu-id="df966-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df966-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df966-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df966-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df966-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df966-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="df966-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="df966-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df966-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df966-114">See also</span></span>

- [<span data-ttu-id="df966-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df966-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="df966-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="df966-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
