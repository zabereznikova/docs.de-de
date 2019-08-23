---
title: ICorDebugInstanceFieldSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ff0ddc266ef9a3f5fabf56f43f1eba2c74e3a8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910171"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="fdd26-102">ICorDebugInstanceFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="fdd26-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="fdd26-103">Ruft die Größe des Instanzfelds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="fdd26-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdd26-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdd26-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdd26-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fdd26-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="fdd26-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="fdd26-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdd26-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fdd26-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdd26-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fdd26-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdd26-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fdd26-109">Requirements</span></span>  
 <span data-ttu-id="fdd26-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdd26-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdd26-111">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="fdd26-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdd26-112">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdd26-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdd26-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdd26-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdd26-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdd26-114">See also</span></span>

- [<span data-ttu-id="fdd26-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fdd26-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="fdd26-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fdd26-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
