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
ms.openlocfilehash: e09e25503ad00ab3542f0c4f50221b6014b25561
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128882"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="8d3b8-102">ICorDebugProcess::EnumerateAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="8d3b8-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="8d3b8-103">Listet alle Anwendungs Domänen in diesem Prozess auf.</span><span class="sxs-lookup"><span data-stu-id="8d3b8-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d3b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d3b8-104">Syntax</span></span>  
  
``` cpp 
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d3b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8d3b8-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="8d3b8-106">vorgenommen Ein Zeiger auf die Adresse eines [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) , der ein Enumerator für die Anwendungs Domänen in diesem Prozess ist.</span><span class="sxs-lookup"><span data-stu-id="8d3b8-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d3b8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8d3b8-107">Remarks</span></span>  
 <span data-ttu-id="8d3b8-108">Diese Methode kann vor dem [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) -Rückruf verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8d3b8-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d3b8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8d3b8-109">Requirements</span></span>  
 <span data-ttu-id="8d3b8-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d3b8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d3b8-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d3b8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d3b8-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d3b8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d3b8-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d3b8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
