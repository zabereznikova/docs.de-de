---
title: ICorDebugAppDomain::EnumerateBreakpoints-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b00afc900a27aea94389ee81065ea22ae359440d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996267"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="da632-102">ICorDebugAppDomain::EnumerateBreakpoints-Methode</span><span class="sxs-lookup"><span data-stu-id="da632-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="da632-103">Ruft einen Enumerator für alle aktiven Haltepunkte in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="da632-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da632-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="da632-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da632-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="da632-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="da632-106">[out] Ein Zeiger auf die Adresse des ICorDebugBreakpointEnum-Objekts, das den Enumerator für alle aktiven Haltepunkte in der Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="da632-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da632-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="da632-107">Remarks</span></span>  
 <span data-ttu-id="da632-108">Der Enumerator schließt alle Typen von Haltepunkten, einschließlich Funktionshaltepunkte und Datenhaltepunkte.</span><span class="sxs-lookup"><span data-stu-id="da632-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da632-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="da632-109">Requirements</span></span>  
 <span data-ttu-id="da632-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da632-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da632-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da632-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da632-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da632-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da632-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da632-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
