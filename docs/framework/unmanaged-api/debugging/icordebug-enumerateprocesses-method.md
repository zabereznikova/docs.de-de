---
title: ICorDebug::EnumerateProcesses-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1a4da6df58c928582a830ef92d286437cb5003c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738213"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="665b2-102">ICorDebug::EnumerateProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="665b2-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="665b2-103">Ruft einen Enumerator für die Prozesse, die gedebuggt werden.</span><span class="sxs-lookup"><span data-stu-id="665b2-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="665b2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="665b2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="665b2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="665b2-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="665b2-106">Ein Zeiger auf die Adresse des ICorDebugProcessEnum-Objekts, das den Enumerator für die zu debuggenden Prozesse ist.</span><span class="sxs-lookup"><span data-stu-id="665b2-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="665b2-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="665b2-107">Requirements</span></span>  
 <span data-ttu-id="665b2-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="665b2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="665b2-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="665b2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="665b2-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="665b2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="665b2-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="665b2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="665b2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="665b2-112">See also</span></span>

- [<span data-ttu-id="665b2-113">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="665b2-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
