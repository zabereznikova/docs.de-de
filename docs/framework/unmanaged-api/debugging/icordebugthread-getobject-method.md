---
title: ICorDebugThread::GetObject-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
ms.openlocfilehash: 624469ca1ae4c96b4143f8768b4c5ff9c2601a2f
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378881"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="e3552-102">ICorDebugThread::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="e3552-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="e3552-103">Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR)-Thread ab.</span><span class="sxs-lookup"><span data-stu-id="e3552-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3552-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3552-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3552-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3552-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="e3552-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Schnittstellen Objekts, das den CLR-Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="e3552-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3552-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e3552-107">Requirements</span></span>  
 <span data-ttu-id="e3552-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3552-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3552-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3552-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3552-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3552-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3552-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3552-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3552-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3552-112">See also</span></span>

- <xref:System.Threading.Thread>
