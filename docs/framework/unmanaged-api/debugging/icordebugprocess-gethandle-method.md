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
ms.openlocfilehash: ed7110cb2e2b7a91ed81d2d81c2989d1733c1ee6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207312"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="e11c7-102">ICorDebugProcess::GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="e11c7-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="e11c7-103">Ruft ein Handle für den Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="e11c7-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e11c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e11c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e11c7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e11c7-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="e11c7-106">vorgenommen Ein Zeiger auf einen `HPROCESS` , der das Handle für den Prozess ist.</span><span class="sxs-lookup"><span data-stu-id="e11c7-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e11c7-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e11c7-107">Remarks</span></span>  
 <span data-ttu-id="e11c7-108">Der Besitzer des abgerufenen Handles ist die Debugschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e11c7-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="e11c7-109">Der Debugger sollte das Handle vor der Verwendung duplizieren.</span><span class="sxs-lookup"><span data-stu-id="e11c7-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e11c7-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e11c7-110">Requirements</span></span>  
 <span data-ttu-id="e11c7-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e11c7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e11c7-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e11c7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e11c7-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e11c7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e11c7-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e11c7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
