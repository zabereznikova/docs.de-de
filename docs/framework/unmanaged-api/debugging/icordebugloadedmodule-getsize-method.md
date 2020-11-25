---
title: ICorDebugLoadedModule::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 2ed19cb4a190f2af7581a827e8bd11b748b3d4a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721321"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="f3d2d-102">ICorDebugLoadedModule::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="f3d2d-102">ICorDebugLoadedModule::GetSize Method</span></span>

<span data-ttu-id="f3d2d-103">Ruft die Größe des geladenen Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="f3d2d-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3d2d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3d2d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3d2d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3d2d-105">Parameters</span></span>  

 `pcBytes`  
 <span data-ttu-id="f3d2d-106">[out] Ein Zeiger auf die Anzahl von Bytes im geladenen Modul.</span><span class="sxs-lookup"><span data-stu-id="f3d2d-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3d2d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f3d2d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3d2d-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f3d2d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3d2d-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f3d2d-109">Requirements</span></span>  

 <span data-ttu-id="f3d2d-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3d2d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3d2d-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3d2d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3d2d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3d2d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3d2d-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3d2d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d2d-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3d2d-114">See also</span></span>

- [<span data-ttu-id="f3d2d-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3d2d-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="f3d2d-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f3d2d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
