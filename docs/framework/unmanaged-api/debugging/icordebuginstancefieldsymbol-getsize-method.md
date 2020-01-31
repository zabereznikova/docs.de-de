---
title: ICorDebugInstanceFieldSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: eb70c441441954e2ffce6ca832c58369c606b128
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782280"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="6869a-102">ICorDebugInstanceFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="6869a-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="6869a-103">Ruft die Größe des Instanzfelds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="6869a-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6869a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6869a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6869a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6869a-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="6869a-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="6869a-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6869a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6869a-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6869a-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6869a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6869a-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6869a-109">Requirements</span></span>  
 <span data-ttu-id="6869a-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6869a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6869a-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6869a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6869a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6869a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6869a-113">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6869a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6869a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6869a-114">See also</span></span>

- [<span data-ttu-id="6869a-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6869a-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="6869a-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6869a-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
