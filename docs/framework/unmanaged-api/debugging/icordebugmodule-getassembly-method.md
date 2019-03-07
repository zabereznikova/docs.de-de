---
title: ICorDebugModule::GetAssembly-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce1e42d74dc611032d941e833bb8f248a56488b4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486251"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="b5a82-102">ICorDebugModule::GetAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="b5a82-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="b5a82-103">Ruft die übergeordnete Assembly für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="b5a82-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5a82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5a82-104">Syntax</span></span>  
  
```  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5a82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5a82-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="b5a82-106">[out] Ein Zeiger auf ein ICorDebugAssembly-Objekt, das die Assembly mit diesem Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="b5a82-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5a82-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b5a82-107">Requirements</span></span>  
 <span data-ttu-id="b5a82-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5a82-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5a82-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5a82-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5a82-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5a82-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5a82-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5a82-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
