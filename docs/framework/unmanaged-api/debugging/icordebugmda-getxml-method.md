---
title: ICorDebugMDA::GetXML-Methode
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
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 387c9bf53dfbe146ccc1526404a1aed7386b2519
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="91a5f-102">ICorDebugMDA::GetXML-Methode</span><span class="sxs-lookup"><span data-stu-id="91a5f-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="91a5f-103">Ruft den vollständigen XML-Stream der Assistent für verwaltetes Debuggen (MDA) dargestellte zugeordneten [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="91a5f-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a5f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91a5f-104">Syntax</span></span>  
  
```  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91a5f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="91a5f-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="91a5f-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="91a5f-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="91a5f-107">[out] Ein Zeiger auf die Länge des XML-Streams.</span><span class="sxs-lookup"><span data-stu-id="91a5f-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="91a5f-108">[out] Ein Array, in dem die XML-Stream gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="91a5f-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="91a5f-109">Das Array kann leer sein.</span><span class="sxs-lookup"><span data-stu-id="91a5f-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91a5f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91a5f-110">Remarks</span></span>  
 <span data-ttu-id="91a5f-111">Die `GetXML` Methode kann abhängig von der Größe des zugeordneten XML-Streams die Leistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="91a5f-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91a5f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91a5f-112">Requirements</span></span>  
 <span data-ttu-id="91a5f-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91a5f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91a5f-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91a5f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91a5f-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91a5f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91a5f-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91a5f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a5f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91a5f-117">See Also</span></span>  
 [<span data-ttu-id="91a5f-118">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91a5f-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="91a5f-119">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="91a5f-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
