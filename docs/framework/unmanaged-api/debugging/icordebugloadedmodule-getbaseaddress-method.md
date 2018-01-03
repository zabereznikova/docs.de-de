---
title: ICorDebugLoadedModule::GetBaseAddress-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d71b1db35a9e2747e7e14787f385f42f98305c61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="57642-102">ICorDebugLoadedModule::GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="57642-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="57642-103">Ruft die Basisadresse für das geladene Modul ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="57642-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57642-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="57642-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57642-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="57642-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="57642-106">[out] Ein Zeiger auf die Basisadresse des geladenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="57642-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57642-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57642-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57642-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="57642-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57642-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57642-109">Requirements</span></span>  
 <span data-ttu-id="57642-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57642-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57642-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57642-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57642-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57642-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57642-113">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57642-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57642-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57642-114">See Also</span></span>  
 [<span data-ttu-id="57642-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57642-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="57642-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="57642-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
