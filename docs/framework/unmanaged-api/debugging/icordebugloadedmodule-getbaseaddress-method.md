---
title: ICorDebugLoadedModule::GetBaseAddress Method
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 190c9114cffa537ba162b19abdf30d5a6aee87f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788446"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="3dc3b-102">ICorDebugLoadedModule::GetBaseAddress Method</span><span class="sxs-lookup"><span data-stu-id="3dc3b-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="3dc3b-103">Ruft die Basisadresse für das geladene Modul ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="3dc3b-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dc3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3dc3b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3dc3b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3dc3b-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="3dc3b-106">[out] Ein Zeiger auf die Basisadresse des geladenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="3dc3b-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dc3b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3dc3b-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3dc3b-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3dc3b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dc3b-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3dc3b-109">Requirements</span></span>  
 <span data-ttu-id="3dc3b-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dc3b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dc3b-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3dc3b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dc3b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dc3b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dc3b-113">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dc3b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dc3b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3dc3b-114">See also</span></span>

- [<span data-ttu-id="3dc3b-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3dc3b-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="3dc3b-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3dc3b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
