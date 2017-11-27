---
title: ICorDebugMergedAssemblyRecord::GetCulture-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7791491a050e31d8d6c5dfb6ef9ffe209921753d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="e40e0-102">ICorDebugMergedAssemblyRecord::GetCulture-Methode</span><span class="sxs-lookup"><span data-stu-id="e40e0-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="e40e0-103">Ruft die Kulturnamen-Zeichenfolge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="e40e0-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e40e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e40e0-104">Syntax</span></span>  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e40e0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e40e0-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="e40e0-106">[in] Die Anzahl der Zeichen im `szCulture`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="e40e0-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="e40e0-107">[out] Die Anzahl der tatsächlich in den `szCulture`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e40e0-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="e40e0-108">[out] Ein Zeichenarray, das den Kulturnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="e40e0-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e40e0-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e40e0-109">Remarks</span></span>  
 <span data-ttu-id="e40e0-110">Der Kulturname ist eine eindeutige Zeichenfolge, die eine Kultur identifiziert, z. B. "en-US" (für die Kultur Englisch (USA)), oder "neutral" (für eine neutrale Kultur).</span><span class="sxs-lookup"><span data-stu-id="e40e0-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e40e0-111">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e40e0-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e40e0-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e40e0-112">Requirements</span></span>  
 <span data-ttu-id="e40e0-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e40e0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e40e0-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e40e0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e40e0-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e40e0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e40e0-116">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e40e0-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e40e0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e40e0-117">See Also</span></span>  
 [<span data-ttu-id="e40e0-118">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e40e0-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="e40e0-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e40e0-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
