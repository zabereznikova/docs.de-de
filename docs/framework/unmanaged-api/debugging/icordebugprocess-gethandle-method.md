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
ms.openlocfilehash: 87b7b7381ef53f7e2abebc053b5c9f87f94d96c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695061"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="1b3fc-102">ICorDebugProcess::GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="1b3fc-102">ICorDebugProcess::GetHandle Method</span></span>

<span data-ttu-id="1b3fc-103">Ruft ein Handle für den Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="1b3fc-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b3fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b3fc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b3fc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b3fc-105">Parameters</span></span>  

 `phProcessHandle`  
 <span data-ttu-id="1b3fc-106">vorgenommen Ein Zeiger auf einen `HPROCESS` , der das Handle für den Prozess ist.</span><span class="sxs-lookup"><span data-stu-id="1b3fc-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b3fc-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b3fc-107">Remarks</span></span>  

 <span data-ttu-id="1b3fc-108">Der Besitzer des abgerufenen Handles ist die Debugschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1b3fc-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="1b3fc-109">Der Debugger sollte das Handle vor der Verwendung duplizieren.</span><span class="sxs-lookup"><span data-stu-id="1b3fc-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b3fc-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1b3fc-110">Requirements</span></span>  

 <span data-ttu-id="1b3fc-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b3fc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b3fc-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b3fc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b3fc-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b3fc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b3fc-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b3fc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
