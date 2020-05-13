---
title: ICorDebugMDA::GetFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type:
- apiref
ms.openlocfilehash: 4e5939e9e74899a33f28927c4fda09d0a8fb30a0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209733"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="afc33-102">ICorDebugMDA::GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="afc33-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="afc33-103">Ruft die Flags ab, die dem von [ICorDebugMDA](icordebugmda-interface.md)dargestellten Assistenten für verwaltetes Debuggen (MDA) zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="afc33-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afc33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="afc33-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afc33-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="afc33-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="afc33-106">in Eine bitweise Kombination der [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) -Enumerationswerte, die die Einstellungen der Flags für diesen MDA angeben.</span><span class="sxs-lookup"><span data-stu-id="afc33-106">[in] A bitwise combination of the [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afc33-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="afc33-107">Requirements</span></span>  
 <span data-ttu-id="afc33-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afc33-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afc33-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afc33-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afc33-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afc33-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afc33-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afc33-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afc33-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afc33-112">See also</span></span>

- [<span data-ttu-id="afc33-113">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="afc33-113">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="afc33-114">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="afc33-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
