---
title: ICorDebugLoadedModule::GetBaseAddress-Methode
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: d8c91c10577efd6a76af778cd01002de006df43a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209876"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="b2a7c-102">ICorDebugLoadedModule::GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="b2a7c-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="b2a7c-103">Ruft die Basisadresse für das geladene Modul ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="b2a7c-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2a7c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2a7c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2a7c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2a7c-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="b2a7c-106">[out] Ein Zeiger auf die Basisadresse des geladenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="b2a7c-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2a7c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2a7c-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2a7c-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b2a7c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2a7c-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b2a7c-109">Requirements</span></span>  
 <span data-ttu-id="b2a7c-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2a7c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2a7c-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2a7c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2a7c-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2a7c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2a7c-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2a7c-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a7c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2a7c-114">See also</span></span>

- [<span data-ttu-id="b2a7c-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b2a7c-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="b2a7c-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b2a7c-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
