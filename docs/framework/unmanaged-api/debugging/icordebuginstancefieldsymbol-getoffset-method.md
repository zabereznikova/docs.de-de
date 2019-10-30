---
title: 'Icordebuginstancefieldsymbol:: gedeffset-Methode'
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 3886e29a1c2fd44fbe50d1eef722f99da7abdbe5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139014"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="03a98-102">Icordebuginstancefieldsymbol:: gedeffset-Methode</span><span class="sxs-lookup"><span data-stu-id="03a98-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="03a98-103">Ruft den Offset dieses Instanzenfelds in der übergeordneten Klasse in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="03a98-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03a98-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03a98-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03a98-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="03a98-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="03a98-106">Ein Zeiger auf die Anzahl der Bytes, die der Offset dieses Instanzenfelds in der übergeordneten Klasse aufweist.</span><span class="sxs-lookup"><span data-stu-id="03a98-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03a98-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03a98-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03a98-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="03a98-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03a98-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="03a98-109">Requirements</span></span>  
 <span data-ttu-id="03a98-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03a98-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03a98-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03a98-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03a98-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03a98-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03a98-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03a98-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a98-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03a98-114">See also</span></span>

- [<span data-ttu-id="03a98-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="03a98-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="03a98-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="03a98-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
