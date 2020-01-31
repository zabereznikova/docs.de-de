---
title: ICorDebugLoadedModule::GetSize Method
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: f207cd1c612b6444a9512adaa356ac2d01de7b9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788466"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="9c733-102">ICorDebugLoadedModule::GetSize Method</span><span class="sxs-lookup"><span data-stu-id="9c733-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="9c733-103">Ruft die Größe des geladenen Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="9c733-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c733-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c733-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c733-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9c733-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="9c733-106">[out] Ein Zeiger auf die Anzahl von Bytes im geladenen Modul.</span><span class="sxs-lookup"><span data-stu-id="9c733-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c733-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c733-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c733-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9c733-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c733-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c733-109">Requirements</span></span>  
 <span data-ttu-id="9c733-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c733-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c733-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c733-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c733-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c733-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c733-113">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c733-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c733-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c733-114">See also</span></span>

- [<span data-ttu-id="9c733-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9c733-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="9c733-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9c733-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
