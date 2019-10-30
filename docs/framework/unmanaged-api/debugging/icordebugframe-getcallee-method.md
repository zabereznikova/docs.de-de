---
title: ICorDebugFrame::GetCallee-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
ms.openlocfilehash: b83dec65e1dd4fc610be3190e8126e6d9d38a6e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121225"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="ec697-102">ICorDebugFrame::GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="ec697-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="ec697-103">Ruft einen Zeiger auf das ICorDebug Frame-Objekt in der aktuellen Kette ab, das in diesem Frame aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ec697-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec697-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec697-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec697-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec697-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="ec697-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugFrame` Objekts, das den aufgerufenen Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="ec697-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="ec697-107">Dieser Wert ist NULL, wenn der aufrufenden Frame der innerste Frame in der aktuellen Kette ist.</span><span class="sxs-lookup"><span data-stu-id="ec697-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec697-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec697-108">Requirements</span></span>  
 <span data-ttu-id="ec697-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec697-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec697-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec697-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec697-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec697-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec697-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec697-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
