---
title: ICorDebugValueBreakpoint::GetValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugValueBreakpoint interface [.NET Framework debugging]
- ICorDebugValueBreakpoint::GetValue method [.NET Framework debugging]
ms.assetid: 52a73654-bc47-48b6-b2b1-a4456b10140c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acdfddd015013215bba9039d871837a60ead1405
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986816"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="be95b-102">ICorDebugValueBreakpoint::GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="be95b-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="be95b-103">Ruft einen Schnittstellenzeiger auf ein "ICorDebugValue"-Objekt, das den Wert des Objekts darstellt, auf denen der Haltepunkt gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="be95b-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be95b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be95b-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be95b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="be95b-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="be95b-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="be95b-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be95b-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be95b-107">Requirements</span></span>  
 <span data-ttu-id="be95b-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be95b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be95b-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be95b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be95b-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be95b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be95b-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be95b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be95b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be95b-112">See also</span></span>
