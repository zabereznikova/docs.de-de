---
title: ICorDebugEval::Abort-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
ms.openlocfilehash: 98a9b285323bc3ad94b4f555e72a4b3242519801
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976290"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="0b49c-102">ICorDebugEval::Abort-Methode</span><span class="sxs-lookup"><span data-stu-id="0b49c-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="0b49c-103">Bricht die Berechnung ab, die dieses ICorDebugEval-Objekt gerade ausführt.</span><span class="sxs-lookup"><span data-stu-id="0b49c-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b49c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b49c-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0b49c-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b49c-105">Remarks</span></span>  
 <span data-ttu-id="0b49c-106">Wenn die Auswertung geschnistet und nicht die neueste ist, schlägt die `Abort` Methode möglicherweise fehl.</span><span class="sxs-lookup"><span data-stu-id="0b49c-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b49c-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0b49c-107">Requirements</span></span>  
 <span data-ttu-id="0b49c-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b49c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b49c-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b49c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b49c-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b49c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b49c-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b49c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
