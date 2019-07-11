---
title: ICorDebugMDA::GetXML-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 003a6546b3316f2a2a65bce4537c60dcf62b3197
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752849"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="7870b-102">ICorDebugMDA::GetXML-Methode</span><span class="sxs-lookup"><span data-stu-id="7870b-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="7870b-103">Ruft den vollständigen XML-Stream zugeordnete managed debugging Assistant (MDA) durch dargestellt [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="7870b-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7870b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7870b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7870b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7870b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="7870b-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="7870b-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="7870b-107">[out] Ein Zeiger auf die Länge des XML-Stream.</span><span class="sxs-lookup"><span data-stu-id="7870b-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="7870b-108">[out] Ein Array, in dem den XML-Stream gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7870b-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="7870b-109">Das Array kann leer sein.</span><span class="sxs-lookup"><span data-stu-id="7870b-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7870b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7870b-110">Remarks</span></span>  
 <span data-ttu-id="7870b-111">Die `GetXML` Methode möglicherweise Leistungseinbußen führen kann, abhängig von der Größe des zugeordneten XML-Streams.</span><span class="sxs-lookup"><span data-stu-id="7870b-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7870b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7870b-112">Requirements</span></span>  
 <span data-ttu-id="7870b-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7870b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7870b-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7870b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7870b-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7870b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7870b-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7870b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7870b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7870b-117">See also</span></span>

- [<span data-ttu-id="7870b-118">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7870b-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="7870b-119">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="7870b-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
