---
title: ICorDebugEval::IsActive-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
ms.openlocfilehash: 5ac221b0b5837175b8073ab29f94c1f28078d3e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729771"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="b0f36-102">ICorDebugEval::IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="b0f36-102">ICorDebugEval::IsActive Method</span></span>

<span data-ttu-id="b0f36-103">Ruft einen Wert ab, der angibt, ob dieses ICorDebugEval-Objekt gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b0f36-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0f36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0f36-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0f36-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b0f36-105">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="b0f36-106">vorgenommen Ein Zeiger auf einen Wert, der angibt, ob diese Auswertung aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="b0f36-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0f36-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b0f36-107">Requirements</span></span>  

 <span data-ttu-id="b0f36-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0f36-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0f36-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0f36-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0f36-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0f36-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0f36-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0f36-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
