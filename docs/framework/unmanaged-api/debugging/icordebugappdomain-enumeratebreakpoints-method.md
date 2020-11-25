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
ms.openlocfilehash: 20c8a1987e48a88a3b8c92cf9f36fb58166cda9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715978"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="ebc08-102">ICorDebugAppDomain::EnumerateBreakpoints-Methode</span><span class="sxs-lookup"><span data-stu-id="ebc08-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>

<span data-ttu-id="ebc08-103">Ruft einen Enumerator für alle aktiven Breakpoints in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="ebc08-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebc08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebc08-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebc08-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ebc08-105">Parameters</span></span>  

 `ppBreakpoints`  
 <span data-ttu-id="ebc08-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugBreakpointEnum-Objekts, das der Enumerator für alle aktiven Breakpoints in der Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="ebc08-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebc08-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ebc08-107">Remarks</span></span>  

 <span data-ttu-id="ebc08-108">Der Enumerator enthält alle Arten von Breakpoints, einschließlich Funktions Haltepunkten und Daten Breakpoints.</span><span class="sxs-lookup"><span data-stu-id="ebc08-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebc08-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ebc08-109">Requirements</span></span>  

 <span data-ttu-id="ebc08-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebc08-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebc08-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebc08-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebc08-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebc08-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebc08-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebc08-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
