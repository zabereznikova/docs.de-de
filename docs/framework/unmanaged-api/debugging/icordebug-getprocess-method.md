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
ms.openlocfilehash: 6020950a7ee742f09af67fe856692e19c066e288
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658042"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="5b86a-102">ICorDebug::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="5b86a-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="5b86a-103">Ruft einen Zeiger auf die "ICorDebugProcess"-Instanz für den angegebenen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="5b86a-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b86a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b86a-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b86a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b86a-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="5b86a-106">[in] Die ID des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="5b86a-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="5b86a-107">[out] Ein Zeiger auf die Adresse einer `ICorDebugProcess` Instanz für den angegebenen Prozess.</span><span class="sxs-lookup"><span data-stu-id="5b86a-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b86a-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b86a-108">Requirements</span></span>  
 <span data-ttu-id="5b86a-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b86a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b86a-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b86a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b86a-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b86a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b86a-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b86a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b86a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b86a-113">See also</span></span>
- [<span data-ttu-id="5b86a-114">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b86a-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
