---
title: ICorDebugLoadedModule::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3067cdee1d3a5df0ad5594bce581139431fd1846
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936876"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="11bc0-102">ICorDebugLoadedModule::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="11bc0-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="11bc0-103">Ruft die Größe des geladenen Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="11bc0-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11bc0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11bc0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11bc0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="11bc0-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="11bc0-106">[out] Ein Zeiger auf die Anzahl von Bytes im geladenen Modul.</span><span class="sxs-lookup"><span data-stu-id="11bc0-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11bc0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11bc0-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="11bc0-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="11bc0-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11bc0-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="11bc0-109">Requirements</span></span>  
 <span data-ttu-id="11bc0-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11bc0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11bc0-111">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="11bc0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11bc0-112">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11bc0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11bc0-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11bc0-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11bc0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11bc0-114">See also</span></span>

- [<span data-ttu-id="11bc0-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11bc0-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="11bc0-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="11bc0-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
