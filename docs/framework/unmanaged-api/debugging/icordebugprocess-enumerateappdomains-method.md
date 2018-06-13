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
ms.openlocfilehash: a1a29840efa173a6546ca00a9dc437e098d6f2aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423389"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="b50b6-102">ICorDebugProcess::EnumerateAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="b50b6-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="b50b6-103">Listet alle Anwendungsdomänen in diesem Prozess auf.</span><span class="sxs-lookup"><span data-stu-id="b50b6-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b50b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b50b6-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b50b6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b50b6-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="b50b6-106">[out] Ein Zeiger auf die Adresse des ein [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) also einen Enumerator für die Anwendungsdomänen in diesem Prozess.</span><span class="sxs-lookup"><span data-stu-id="b50b6-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b50b6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b50b6-107">Remarks</span></span>  
 <span data-ttu-id="b50b6-108">Diese Methode kann verwendet werden, bevor die [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="b50b6-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b50b6-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b50b6-109">Requirements</span></span>  
 <span data-ttu-id="b50b6-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b50b6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b50b6-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b50b6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b50b6-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b50b6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b50b6-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b50b6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
