---
title: ICorDebugType::GetRank-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetRank
helpviewer_keywords:
- GetRank method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetRank method [.NET Framework debugging]
ms.assetid: 72d3d927-f590-4f2d-8f60-448f3dfb96af
topic_type:
- apiref
ms.openlocfilehash: defd2623b85225f4139ff0bfce8495d16e3b4182
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684417"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="b2997-102">ICorDebugType::GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="b2997-102">ICorDebugType::GetRank Method</span></span>

<span data-ttu-id="b2997-103">Ruft die Anzahl der Dimensionen in einem Arraytyp ab.</span><span class="sxs-lookup"><span data-stu-id="b2997-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2997-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2997-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2997-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2997-105">Parameters</span></span>  

 `pnRank`  
 <span data-ttu-id="b2997-106">vorgenommen Ein Zeiger auf die Anzahl von Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="b2997-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2997-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b2997-107">Requirements</span></span>  

 <span data-ttu-id="b2997-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2997-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2997-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2997-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2997-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2997-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2997-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2997-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
