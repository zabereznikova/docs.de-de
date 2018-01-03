---
title: ICorDebugMDA::GetName-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c31125b1faf9f14262e8e4a4c6269671a35519f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="75ba9-102">ICorDebugMDA::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="75ba9-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="75ba9-103">Ruft eine Zeichenfolge mit dem Namen der der Assistent für verwaltetes Debuggen (MDA) dargestellte [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="75ba9-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75ba9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="75ba9-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75ba9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="75ba9-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="75ba9-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="75ba9-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="75ba9-107">[out] Ein Zeiger auf die Länge des Namens.</span><span class="sxs-lookup"><span data-stu-id="75ba9-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="75ba9-108">[out] Ein Array, in dem Sie den Namen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="75ba9-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75ba9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75ba9-109">Remarks</span></span>  
 <span data-ttu-id="75ba9-110">MDA-Namen sind eindeutige Werte.</span><span class="sxs-lookup"><span data-stu-id="75ba9-110">MDA names are unique values.</span></span> <span data-ttu-id="75ba9-111">Die `GetName` Methode ist eine praktische Alternative zum Abrufen des XML-Streams und zum Extrahieren des Namens aus dem Stream basierend auf dem Schema.</span><span class="sxs-lookup"><span data-stu-id="75ba9-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75ba9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="75ba9-112">Requirements</span></span>  
 <span data-ttu-id="75ba9-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75ba9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75ba9-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75ba9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75ba9-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75ba9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75ba9-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75ba9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ba9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75ba9-117">See Also</span></span>  
 [<span data-ttu-id="75ba9-118">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75ba9-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="75ba9-119">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="75ba9-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
