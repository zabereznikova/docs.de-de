---
title: 'Icordebugmergedassemblyrecord:: getIndex-Methode'
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: 236bd8b22d6c3ec783d787f6c906ede3193cfc1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131407"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="fa7db-102">Icordebugmergedassemblyrecord:: getIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="fa7db-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="fa7db-103">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="fa7db-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa7db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa7db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa7db-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa7db-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="fa7db-106">[out] Ein Zeiger auf den Präfixindex.</span><span class="sxs-lookup"><span data-stu-id="fa7db-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa7db-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa7db-107">Remarks</span></span>  
 <span data-ttu-id="fa7db-108">Der Präfixindex wird verwendet, um Namenskonflikte in den zusammengeführten Namen der Metadatentypen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="fa7db-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa7db-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fa7db-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa7db-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa7db-110">Requirements</span></span>  
 <span data-ttu-id="fa7db-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa7db-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa7db-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa7db-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa7db-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa7db-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa7db-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa7db-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa7db-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa7db-115">See also</span></span>

- [<span data-ttu-id="fa7db-116">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa7db-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="fa7db-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fa7db-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
