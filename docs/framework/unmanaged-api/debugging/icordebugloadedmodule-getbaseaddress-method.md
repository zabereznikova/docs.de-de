---
title: ICorDebugLoadedModule::GetBaseAddress-Methode
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85748106edb34b98f975a40bcc2617401536e271
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910102"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="074e5-102">ICorDebugLoadedModule::GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="074e5-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="074e5-103">Ruft die Basisadresse für das geladene Modul ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="074e5-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="074e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="074e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="074e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="074e5-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="074e5-106">[out] Ein Zeiger auf die Basisadresse des geladenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="074e5-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="074e5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="074e5-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="074e5-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="074e5-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="074e5-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="074e5-109">Requirements</span></span>  
 <span data-ttu-id="074e5-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="074e5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="074e5-111">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="074e5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="074e5-112">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="074e5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="074e5-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="074e5-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="074e5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="074e5-114">See also</span></span>

- [<span data-ttu-id="074e5-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="074e5-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="074e5-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="074e5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
