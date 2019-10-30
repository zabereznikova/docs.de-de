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
ms.openlocfilehash: 9a00177faabfcad56d70ec5c64328c90675c1532
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138762"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="e96d1-102">ICorDebugType::GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="e96d1-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="e96d1-103">Ruft die Anzahl der Dimensionen in einem Arraytyp ab.</span><span class="sxs-lookup"><span data-stu-id="e96d1-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e96d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e96d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e96d1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e96d1-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="e96d1-106">vorgenommen Ein Zeiger auf die Anzahl von Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="e96d1-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e96d1-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e96d1-107">Requirements</span></span>  
 <span data-ttu-id="e96d1-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e96d1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e96d1-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e96d1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e96d1-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e96d1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e96d1-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e96d1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
