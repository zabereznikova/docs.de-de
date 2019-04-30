---
title: ICorDebugInstanceFieldSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cc09de2120399dcfe309757d554e1de72e55f07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946371"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="47b0e-102">ICorDebugInstanceFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="47b0e-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="47b0e-103">Ruft die Größe des Instanzfelds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="47b0e-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47b0e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47b0e-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47b0e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="47b0e-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="47b0e-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="47b0e-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47b0e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="47b0e-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47b0e-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="47b0e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47b0e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47b0e-109">Requirements</span></span>  
 <span data-ttu-id="47b0e-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47b0e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47b0e-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47b0e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47b0e-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47b0e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47b0e-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47b0e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47b0e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47b0e-114">See also</span></span>

- [<span data-ttu-id="47b0e-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47b0e-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="47b0e-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="47b0e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
