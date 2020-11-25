---
title: ICorDebugEval::GetThread-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
ms.openlocfilehash: 0680c47e4390e876c5df99ee7eb200e7d187f0ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722192"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="682b9-102">ICorDebugEval::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="682b9-102">ICorDebugEval::GetThread Method</span></span>

<span data-ttu-id="682b9-103">Ruft den Thread ab, in dem diese Auswertung ausgeführt wird oder ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="682b9-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="682b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="682b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="682b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="682b9-105">Parameters</span></span>  

 `ppThread`  
 <span data-ttu-id="682b9-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugThread-Objekts, das den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="682b9-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="682b9-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="682b9-107">Requirements</span></span>  

 <span data-ttu-id="682b9-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="682b9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="682b9-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="682b9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="682b9-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="682b9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="682b9-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="682b9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
