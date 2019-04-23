---
title: ICorDebugLoadedModule::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4601261971cce32b6d6d9ee7377f725a85103a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183468"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="2df2d-102">ICorDebugLoadedModule::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="2df2d-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="2df2d-103">Ruft die Größe des geladenen Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="2df2d-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df2d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2df2d-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2df2d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2df2d-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="2df2d-106">[out] Ein Zeiger auf die Anzahl von Bytes im geladenen Modul.</span><span class="sxs-lookup"><span data-stu-id="2df2d-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2df2d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2df2d-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2df2d-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2df2d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2df2d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2df2d-109">Requirements</span></span>  
 <span data-ttu-id="2df2d-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2df2d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2df2d-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2df2d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2df2d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2df2d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2df2d-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2df2d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df2d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2df2d-114">See also</span></span>

- [<span data-ttu-id="2df2d-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2df2d-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="2df2d-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2df2d-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
