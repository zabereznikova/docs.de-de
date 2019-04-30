---
title: ICorDebugLoadedModule::GetName-Methode
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9bf09c01d24315c3f239911326f1844a0b2cc101
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946262"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="8957b-102">ICorDebugLoadedModule::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="8957b-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="8957b-103">Ruft den Namen des geladenen Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="8957b-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8957b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8957b-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8957b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8957b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="8957b-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="8957b-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8957b-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8957b-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="8957b-108">[out] Ein Array von Zeichen, die den Namen des geladenen Moduls enthalten.</span><span class="sxs-lookup"><span data-stu-id="8957b-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8957b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8957b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8957b-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8957b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8957b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8957b-111">Requirements</span></span>  
 <span data-ttu-id="8957b-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8957b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8957b-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8957b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8957b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8957b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8957b-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8957b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8957b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8957b-116">See also</span></span>

- [<span data-ttu-id="8957b-117">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8957b-117">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="8957b-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8957b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
