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
ms.openlocfilehash: bb994ae32c9e0e61c06c60521361a5c6c78d12fa
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895277"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="4532a-102">ICorDebugAppDomain::EnumerateBreakpoints-Methode</span><span class="sxs-lookup"><span data-stu-id="4532a-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="4532a-103">Ruft einen Enumerator für alle aktiven Breakpoints in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="4532a-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4532a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4532a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4532a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4532a-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="4532a-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugBreakpointEnum-Objekts, das der Enumerator für alle aktiven Breakpoints in der Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="4532a-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4532a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4532a-107">Remarks</span></span>  
 <span data-ttu-id="4532a-108">Der Enumerator enthält alle Arten von Breakpoints, einschließlich Funktions Haltepunkten und Daten Breakpoints.</span><span class="sxs-lookup"><span data-stu-id="4532a-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4532a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4532a-109">Requirements</span></span>  
 <span data-ttu-id="4532a-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4532a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4532a-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4532a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4532a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4532a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4532a-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4532a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
