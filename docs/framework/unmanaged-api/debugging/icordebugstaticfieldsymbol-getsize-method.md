---
title: ICorDebugStaticFieldSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acb72a7d6c39efa5fa93bfddc314d07ec6cd8348
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419093"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="96d23-102">ICorDebugStaticFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="96d23-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="96d23-103">Ruft die Größe des statischen Felds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="96d23-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d23-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="96d23-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96d23-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="96d23-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="96d23-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="96d23-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96d23-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96d23-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96d23-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="96d23-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96d23-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96d23-109">Requirements</span></span>  
 <span data-ttu-id="96d23-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96d23-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96d23-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96d23-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96d23-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96d23-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96d23-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96d23-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d23-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96d23-114">See Also</span></span>  
 [<span data-ttu-id="96d23-115">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96d23-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="96d23-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="96d23-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
