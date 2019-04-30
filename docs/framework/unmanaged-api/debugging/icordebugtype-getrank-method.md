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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 134fe55de71e3d6a9a68249febc4c70f11d4f36f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993862"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="9c3fe-102">ICorDebugType::GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="9c3fe-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="9c3fe-103">Ruft die Anzahl der Dimensionen im Array-Typ ab.</span><span class="sxs-lookup"><span data-stu-id="9c3fe-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c3fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c3fe-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c3fe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9c3fe-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="9c3fe-106">[out] Ein Zeiger auf die Anzahl der Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="9c3fe-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c3fe-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c3fe-107">Requirements</span></span>  
 <span data-ttu-id="9c3fe-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c3fe-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c3fe-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c3fe-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c3fe-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c3fe-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c3fe-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c3fe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
