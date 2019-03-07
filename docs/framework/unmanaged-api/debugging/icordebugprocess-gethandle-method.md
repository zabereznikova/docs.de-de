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
ms.openlocfilehash: c5d81564a34ed8e7ef75840e3a174661c36f5411
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498085"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="2c6b1-102">ICorDebugProcess::GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="2c6b1-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="2c6b1-103">Ruft ein Handle für den Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="2c6b1-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c6b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c6b1-104">Syntax</span></span>  
  
```  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c6b1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c6b1-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="2c6b1-106">[out] Ein Zeiger auf ein `HPROCESS` , das Handle für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="2c6b1-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c6b1-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c6b1-107">Remarks</span></span>  
 <span data-ttu-id="2c6b1-108">Das abgerufene Handle gehört die Debugschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2c6b1-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="2c6b1-109">Der Debugger sollte das Handle duplizieren, bevor Sie ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c6b1-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c6b1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c6b1-110">Requirements</span></span>  
 <span data-ttu-id="2c6b1-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c6b1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c6b1-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c6b1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c6b1-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c6b1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c6b1-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c6b1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
