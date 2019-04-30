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
ms.openlocfilehash: 909bcad035516c494d1f867b71bb8f52939eba13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993992"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="f619b-102">ICorDebugThread::GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="f619b-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="f619b-103">Ruft einen Schnittstellenzeiger auf das Register-Satz, der der aktive Teil dieses ICorDebugThread-Objekt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f619b-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f619b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f619b-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f619b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f619b-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="f619b-106">[out] Ein Zeiger auf die Adresse einer [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) Schnittstellenobjekt, das Register darstellt, für den aktiven Teil dieses Threads festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f619b-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f619b-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f619b-107">Requirements</span></span>  
 <span data-ttu-id="f619b-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f619b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f619b-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f619b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f619b-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f619b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f619b-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f619b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
