---
title: ICorDebugLoadedModule::GetBaseAddress-Methode
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adb01b8aa57bf3ed928578d15e0859b9ac73bc7d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759940"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="02d67-102">ICorDebugLoadedModule::GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="02d67-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="02d67-103">Ruft die Basisadresse für das geladene Modul ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="02d67-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d67-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="02d67-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02d67-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="02d67-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="02d67-106">[out] Ein Zeiger auf die Basisadresse des geladenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="02d67-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02d67-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02d67-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02d67-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="02d67-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02d67-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02d67-109">Requirements</span></span>  
 <span data-ttu-id="02d67-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02d67-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d67-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02d67-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02d67-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02d67-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02d67-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d67-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d67-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02d67-114">See also</span></span>

- [<span data-ttu-id="02d67-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02d67-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="02d67-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="02d67-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
