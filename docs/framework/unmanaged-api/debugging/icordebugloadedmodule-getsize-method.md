---
title: ICorDebugLoadedModule::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 6a1c8c94b3c45ac995501b84bb4a69d73e7db25b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209850"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="f1179-102">ICorDebugLoadedModule::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="f1179-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="f1179-103">Ruft die Größe des geladenen Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="f1179-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1179-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1179-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1179-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1179-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="f1179-106">[out] Ein Zeiger auf die Anzahl von Bytes im geladenen Modul.</span><span class="sxs-lookup"><span data-stu-id="f1179-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1179-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f1179-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1179-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f1179-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1179-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f1179-109">Requirements</span></span>  
 <span data-ttu-id="f1179-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1179-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1179-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1179-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1179-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1179-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1179-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1179-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1179-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1179-114">See also</span></span>

- [<span data-ttu-id="f1179-115">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1179-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="f1179-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f1179-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
