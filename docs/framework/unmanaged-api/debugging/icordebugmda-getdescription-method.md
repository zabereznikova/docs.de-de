---
title: ICorDebugMDA::GetDescription-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 998d4baf03123f1ffc174b2a7aeed0ff4a25b001
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133477"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="a2a97-102">ICorDebugMDA::GetDescription-Methode</span><span class="sxs-lookup"><span data-stu-id="a2a97-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="a2a97-103">Ruft eine Zeichenfolge, enthält die Beschreibung des managed debugging Assistant (MDA) durch dargestellt [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a2a97-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2a97-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2a97-104">Syntax</span></span>  
  
```  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2a97-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a2a97-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="a2a97-106">[in] Die Größe des Zeichenfolgenpuffers, die die Beschreibung gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a2a97-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a2a97-107">[out] Ein Zeiger auf die Anzahl der Bytes in den Puffer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a2a97-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="a2a97-108">[out] Einen Zeichenfolgenpuffer, der mit der Beschreibung des MDA.</span><span class="sxs-lookup"><span data-stu-id="a2a97-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2a97-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2a97-109">Remarks</span></span>  
 <span data-ttu-id="a2a97-110">Die Zeichenfolge kann 0 (null) lang sein.</span><span class="sxs-lookup"><span data-stu-id="a2a97-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2a97-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a2a97-111">Requirements</span></span>  
 <span data-ttu-id="a2a97-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2a97-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2a97-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2a97-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2a97-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2a97-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a2a97-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a2a97-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a2a97-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2a97-116">See also</span></span>

- [<span data-ttu-id="a2a97-117">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a2a97-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="a2a97-118">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="a2a97-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
