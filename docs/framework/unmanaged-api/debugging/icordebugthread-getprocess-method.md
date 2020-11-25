---
title: ICorDebugThread::GetProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
ms.openlocfilehash: d3697bd8a3f32c802ab2e335f89c84efaf3e4db0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727990"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="8d03e-102">ICorDebugThread::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="8d03e-102">ICorDebugThread::GetProcess Method</span></span>

<span data-ttu-id="8d03e-103">Ruft einen Schnittstellen Zeiger auf den Prozess ab, von dem dieser ICorDebugThread ein Part bildet.</span><span class="sxs-lookup"><span data-stu-id="8d03e-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d03e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d03e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d03e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8d03e-105">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="8d03e-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Schnittstellen Objekts, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="8d03e-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d03e-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8d03e-107">Requirements</span></span>  

 <span data-ttu-id="8d03e-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d03e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d03e-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d03e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d03e-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d03e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d03e-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d03e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
