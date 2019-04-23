---
title: ICorDebugLoadedModule::GetBaseAddress-Methode
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e84d6deca0cd09cc547636007208c70ab91c1ab1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223536"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="dee02-102">ICorDebugLoadedModule::GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="dee02-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="dee02-103">Ruft die Basisadresse für das geladene Modul ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="dee02-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dee02-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dee02-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dee02-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dee02-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="dee02-106">[out] Ein Zeiger auf die Basisadresse des geladenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="dee02-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dee02-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dee02-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dee02-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dee02-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dee02-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dee02-109">Requirements</span></span>  
 <span data-ttu-id="dee02-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dee02-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dee02-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dee02-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dee02-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dee02-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dee02-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dee02-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dee02-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dee02-114">See also</span></span>

- [<span data-ttu-id="dee02-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dee02-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="dee02-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dee02-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
