---
title: ICorDebug::GetProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e04bef30d4a9edf9898b27e15a79b2b70e3a7f31
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477855"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="a4628-102">ICorDebug::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="a4628-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="a4628-103">Ruft einen Zeiger auf die "ICorDebugProcess"-Instanz für den angegebenen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="a4628-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4628-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4628-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4628-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a4628-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="a4628-106">[in] Die ID des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="a4628-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="a4628-107">[out] Ein Zeiger auf die Adresse einer `ICorDebugProcess` Instanz für den angegebenen Prozess.</span><span class="sxs-lookup"><span data-stu-id="a4628-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4628-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4628-108">Requirements</span></span>  
 <span data-ttu-id="a4628-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4628-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4628-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4628-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4628-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4628-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4628-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4628-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4628-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4628-113">See also</span></span>
- [<span data-ttu-id="a4628-114">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4628-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
