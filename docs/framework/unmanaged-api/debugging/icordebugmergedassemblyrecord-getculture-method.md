---
title: 'Icordebugmergedassemblyrecord:: getculture-Methode'
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0f3ecee5a003587771871a178356d6dbfd8a636
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936844"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="1117c-102">Icordebugmergedassemblyrecord:: getculture-Methode</span><span class="sxs-lookup"><span data-stu-id="1117c-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="1117c-103">Ruft die Kulturnamen-Zeichenfolge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="1117c-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1117c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1117c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1117c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1117c-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="1117c-106">[in] Die Anzahl der Zeichen im `szCulture`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="1117c-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="1117c-107">[out] Die Anzahl der tatsächlich in den `szCulture`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1117c-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="1117c-108">[out] Ein Zeichenarray, das den Kulturnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="1117c-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1117c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1117c-109">Remarks</span></span>  
 <span data-ttu-id="1117c-110">Der Kulturname ist eine eindeutige Zeichenfolge, die eine Kultur identifiziert, z. B. "en-US" (für die Kultur Englisch (USA)), oder "neutral" (für eine neutrale Kultur).</span><span class="sxs-lookup"><span data-stu-id="1117c-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1117c-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1117c-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1117c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1117c-112">Requirements</span></span>  
 <span data-ttu-id="1117c-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1117c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1117c-114">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="1117c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1117c-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1117c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1117c-116">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1117c-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1117c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1117c-117">See also</span></span>

- [<span data-ttu-id="1117c-118">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1117c-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="1117c-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1117c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
