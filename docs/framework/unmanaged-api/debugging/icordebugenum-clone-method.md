---
title: ICorDebugEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d1226f64df379b5c40304221e9e66eebcdb17b4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479232"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="55abd-102">ICorDebugEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="55abd-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="55abd-103">Erstellt eine Kopie dieses ICorDebugEnum-Objekts.</span><span class="sxs-lookup"><span data-stu-id="55abd-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55abd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55abd-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55abd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="55abd-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="55abd-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugEnum` Objekt, das eine Kopie dieses `ICorDebugEnum` Objekt.</span><span class="sxs-lookup"><span data-stu-id="55abd-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55abd-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55abd-107">Requirements</span></span>  
 <span data-ttu-id="55abd-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55abd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55abd-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55abd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55abd-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55abd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55abd-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55abd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
