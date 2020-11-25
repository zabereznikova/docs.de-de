---
title: ICorDebugLoadedModule::GetBaseAddress-Methode
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 29153da86812583a0ea789da0c0816f08e0a6b43
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698077"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="2a002-102">ICorDebugLoadedModule::GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="2a002-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>

<span data-ttu-id="2a002-103">Ruft die Basisadresse für das geladene Modul ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="2a002-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a002-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a002-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a002-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a002-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="2a002-106">[out] Ein Zeiger auf die Basisadresse des geladenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="2a002-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a002-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2a002-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a002-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2a002-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a002-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2a002-109">Requirements</span></span>  

 <span data-ttu-id="2a002-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a002-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a002-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a002-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a002-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a002-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a002-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a002-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a002-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2a002-114">See also</span></span>

- [<span data-ttu-id="2a002-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a002-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="2a002-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2a002-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
