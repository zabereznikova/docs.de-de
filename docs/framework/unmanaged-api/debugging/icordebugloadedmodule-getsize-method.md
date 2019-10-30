---
title: ICorDebugLoadedModule::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 3f2f8a1721847b8f7b845c42aa3c91e032c2d474
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122636"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="0ee86-102">ICorDebugLoadedModule::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="0ee86-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="0ee86-103">Ruft die Größe des geladenen Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="0ee86-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ee86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ee86-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ee86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ee86-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="0ee86-106">[out] Ein Zeiger auf die Anzahl von Bytes im geladenen Modul.</span><span class="sxs-lookup"><span data-stu-id="0ee86-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ee86-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ee86-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ee86-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0ee86-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ee86-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ee86-109">Requirements</span></span>  
 <span data-ttu-id="0ee86-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ee86-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ee86-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ee86-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ee86-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ee86-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ee86-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ee86-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee86-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ee86-114">See also</span></span>

- [<span data-ttu-id="0ee86-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ee86-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="0ee86-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0ee86-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
