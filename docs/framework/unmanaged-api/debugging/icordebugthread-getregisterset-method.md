---
title: ICorDebugThread::GetRegisterSet-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8769293364c111754f4bfe9360a0dca93c0ba13c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770603"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="e0bd8-102">ICorDebugThread::GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="e0bd8-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="e0bd8-103">Ruft einen Schnittstellenzeiger auf das Register-Satz, der der aktive Teil dieses ICorDebugThread-Objekt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e0bd8-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0bd8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0bd8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0bd8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0bd8-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="e0bd8-106">[out] Ein Zeiger auf die Adresse einer [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) Schnittstellenobjekt, das Register darstellt, für den aktiven Teil dieses Threads festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e0bd8-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0bd8-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0bd8-107">Requirements</span></span>  
 <span data-ttu-id="e0bd8-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0bd8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0bd8-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0bd8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0bd8-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0bd8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0bd8-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0bd8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
