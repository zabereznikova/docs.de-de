---
title: ICorDebugStaticFieldSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: deeb887dad38417e3ebb980f5ef2f89392388d65
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791819"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="9799c-102">ICorDebugStaticFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="9799c-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="9799c-103">Ruft die Größe des statischen Felds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="9799c-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9799c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9799c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9799c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9799c-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="9799c-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="9799c-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9799c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9799c-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9799c-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9799c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9799c-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9799c-109">Requirements</span></span>  
 <span data-ttu-id="9799c-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9799c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9799c-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9799c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9799c-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9799c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9799c-113">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9799c-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9799c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9799c-114">See also</span></span>

- [<span data-ttu-id="9799c-115">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9799c-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="9799c-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9799c-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
