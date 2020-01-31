---
title: ICorDebugStaticFieldSymbol::GetAddress-Methode
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: be4d59fe668026c4b40be4c6d0afcf718c8157bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791848"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="2b65d-102">ICorDebugStaticFieldSymbol::GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="2b65d-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="2b65d-103">Ruft die Adresse eines statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="2b65d-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b65d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b65d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b65d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2b65d-105">Parameters</span></span>  
 <span data-ttu-id="2b65d-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="2b65d-106">pRVA</span></span>  
 <span data-ttu-id="2b65d-107">[out] Ein Zeiger auf die relative virtuelle Adresse (RVA) des statischen Felds.</span><span class="sxs-lookup"><span data-stu-id="2b65d-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b65d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b65d-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b65d-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2b65d-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b65d-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b65d-110">Requirements</span></span>  
 <span data-ttu-id="2b65d-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b65d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b65d-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b65d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b65d-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b65d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b65d-114">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b65d-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b65d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b65d-115">See also</span></span>

- [<span data-ttu-id="2b65d-116">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b65d-116">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="2b65d-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2b65d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
