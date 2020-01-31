---
title: ICorDebugLoadedModule::GetName Method
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: 628f85f3045533ead7ace47b11573a0b1a46df46
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782048"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="e84c9-102">ICorDebugLoadedModule::GetName Method</span><span class="sxs-lookup"><span data-stu-id="e84c9-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="e84c9-103">Ruft den Namen des geladenen Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="e84c9-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e84c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e84c9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e84c9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="e84c9-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="e84c9-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="e84c9-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e84c9-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e84c9-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="e84c9-108">[out] Ein Array von Zeichen, die den Namen des geladenen Moduls enthalten.</span><span class="sxs-lookup"><span data-stu-id="e84c9-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e84c9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e84c9-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e84c9-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e84c9-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e84c9-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e84c9-111">Requirements</span></span>  
 <span data-ttu-id="e84c9-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e84c9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e84c9-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e84c9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e84c9-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e84c9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e84c9-115">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e84c9-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e84c9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e84c9-116">See also</span></span>

- [<span data-ttu-id="e84c9-117">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e84c9-117">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="e84c9-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e84c9-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
