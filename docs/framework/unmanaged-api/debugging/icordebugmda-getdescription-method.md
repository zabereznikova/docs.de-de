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
ms.openlocfilehash: da57ecf0c153d902322798e1927c995a34cb93d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761991"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="fa1cb-102">ICorDebugMDA::GetDescription-Methode</span><span class="sxs-lookup"><span data-stu-id="fa1cb-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="fa1cb-103">Ruft eine Zeichenfolge, enthält die Beschreibung des managed debugging Assistant (MDA) durch dargestellt [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="fa1cb-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa1cb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa1cb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa1cb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa1cb-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="fa1cb-106">[in] Die Größe des Zeichenfolgenpuffers, die die Beschreibung gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa1cb-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="fa1cb-107">[out] Ein Zeiger auf die Anzahl der Bytes in den Puffer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fa1cb-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="fa1cb-108">[out] Einen Zeichenfolgenpuffer, der mit der Beschreibung des MDA.</span><span class="sxs-lookup"><span data-stu-id="fa1cb-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa1cb-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa1cb-109">Remarks</span></span>  
 <span data-ttu-id="fa1cb-110">Die Zeichenfolge kann 0 (null) lang sein.</span><span class="sxs-lookup"><span data-stu-id="fa1cb-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa1cb-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa1cb-111">Requirements</span></span>  
 <span data-ttu-id="fa1cb-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa1cb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa1cb-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa1cb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa1cb-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa1cb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa1cb-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa1cb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa1cb-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa1cb-116">See also</span></span>

- [<span data-ttu-id="fa1cb-117">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa1cb-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="fa1cb-118">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="fa1cb-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
