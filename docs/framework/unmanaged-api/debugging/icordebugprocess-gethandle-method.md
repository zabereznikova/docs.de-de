---
title: ICorDebugProcess::GetHandle-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56f1dd892429724866182248b0c0413a7d2437cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766074"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="71fac-102">ICorDebugProcess::GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="71fac-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="71fac-103">Ruft ein Handle für den Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="71fac-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71fac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71fac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71fac-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71fac-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="71fac-106">[out] Ein Zeiger auf ein `HPROCESS` , das Handle für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="71fac-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71fac-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71fac-107">Remarks</span></span>  
 <span data-ttu-id="71fac-108">Das abgerufene Handle gehört die Debugschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="71fac-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="71fac-109">Der Debugger sollte das Handle duplizieren, bevor Sie ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="71fac-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71fac-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71fac-110">Requirements</span></span>  
 <span data-ttu-id="71fac-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71fac-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71fac-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71fac-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71fac-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71fac-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71fac-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71fac-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
