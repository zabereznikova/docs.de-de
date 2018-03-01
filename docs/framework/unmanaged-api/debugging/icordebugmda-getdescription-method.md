---
title: ICorDebugMDA::GetDescription-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugMDA.GetDescription
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5d527f22693ca912d33d56ae4f0ffeddb9de38ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="f5852-102">ICorDebugMDA::GetDescription-Methode</span><span class="sxs-lookup"><span data-stu-id="f5852-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="f5852-103">Ruft eine Zeichenfolge, enthält die Beschreibung der der Assistent für verwaltetes Debuggen (MDA) dargestellte [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f5852-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5852-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5852-104">Syntax</span></span>  
  
```  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5852-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5852-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f5852-106">[in] Die Größe des Zeichenfolgenpuffers, in denen die Beschreibung gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f5852-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f5852-107">[out] Ein Zeiger auf die Anzahl der Bytes im Zeichenfolgenpuffer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f5852-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="f5852-108">[out] Einen Zeichenfolgenpuffer, enthält die Beschreibung des MDA.</span><span class="sxs-lookup"><span data-stu-id="f5852-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5852-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5852-109">Remarks</span></span>  
 <span data-ttu-id="f5852-110">Die Zeichenfolge kann 0 (null) lang sein.</span><span class="sxs-lookup"><span data-stu-id="f5852-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5852-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5852-111">Requirements</span></span>  
 <span data-ttu-id="f5852-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5852-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5852-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5852-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5852-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5852-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5852-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5852-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5852-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5852-116">See Also</span></span>  
 [<span data-ttu-id="f5852-117">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5852-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="f5852-118">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="f5852-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
