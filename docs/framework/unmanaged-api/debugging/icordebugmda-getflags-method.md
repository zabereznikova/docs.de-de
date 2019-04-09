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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a35e9f7cf43105db05408f285cd89dbd839a4cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093487"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="9a778-102">ICorDebugMDA::GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="9a778-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="9a778-103">Ruft die Flags, die mit managed debugging Assistant (MDA) durch dargestellt [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9a778-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a778-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a778-104">Syntax</span></span>  
  
```  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a778-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a778-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="9a778-106">[in] Eine bitweise Kombination der [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) Enumerationswerte, der die Einstellungen der Flags, die für diesen MDA angeben.</span><span class="sxs-lookup"><span data-stu-id="9a778-106">[in] A bitwise combination of the [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a778-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a778-107">Requirements</span></span>  
 <span data-ttu-id="9a778-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a778-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a778-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a778-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a778-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a778-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9a778-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="9a778-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9a778-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a778-112">See also</span></span>

- [<span data-ttu-id="9a778-113">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a778-113">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="9a778-114">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="9a778-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
