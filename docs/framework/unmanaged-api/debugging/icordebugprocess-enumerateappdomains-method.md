---
title: ICorDebugProcess::EnumerateAppDomains-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02e051d311e447475bea724b0bd7420ee8b590f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749084"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="35360-102">ICorDebugProcess::EnumerateAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="35360-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="35360-103">Listet alle Anwendungsdomänen in diesem Prozess.</span><span class="sxs-lookup"><span data-stu-id="35360-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35360-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35360-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35360-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="35360-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="35360-106">[out] Ein Zeiger auf die Adresse einer [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) , einen Enumerator für die Anwendungsdomänen in diesem Prozess.</span><span class="sxs-lookup"><span data-stu-id="35360-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35360-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="35360-107">Remarks</span></span>  
 <span data-ttu-id="35360-108">Diese Methode kann verwendet werden, bevor die [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="35360-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35360-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="35360-109">Requirements</span></span>  
 <span data-ttu-id="35360-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35360-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35360-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35360-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35360-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35360-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35360-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35360-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
