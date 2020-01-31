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
ms.openlocfilehash: 0c7b8dae756fbb9ab27ff187eeb83a931b016b7f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793284"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="dbd4b-102">ICorDebugMDA::GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="dbd4b-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="dbd4b-103">Ruft die Flags ab, die dem von [ICorDebugMDA](icordebugmda-interface.md)dargestellten Assistenten für verwaltetes Debuggen (MDA) zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="dbd4b-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbd4b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbd4b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbd4b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="dbd4b-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="dbd4b-106">in Eine bitweise Kombination der [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) -Enumerationswerte, die die Einstellungen der Flags für diesen MDA angeben.</span><span class="sxs-lookup"><span data-stu-id="dbd4b-106">[in] A bitwise combination of the [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbd4b-107">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbd4b-107">Requirements</span></span>  
 <span data-ttu-id="dbd4b-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbd4b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbd4b-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbd4b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbd4b-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbd4b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbd4b-111">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbd4b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd4b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbd4b-112">See also</span></span>

- [<span data-ttu-id="dbd4b-113">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbd4b-113">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="dbd4b-114">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="dbd4b-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
