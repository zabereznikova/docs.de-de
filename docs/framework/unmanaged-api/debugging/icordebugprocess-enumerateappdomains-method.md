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
ms.openlocfilehash: 4489238df05edef384b4073ee738a184ff8809ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178675"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="fdb8f-102">ICorDebugProcess::EnumerateAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="fdb8f-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="fdb8f-103">Zählt alle Anwendungsdomänen in diesem Prozess auf.</span><span class="sxs-lookup"><span data-stu-id="fdb8f-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdb8f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdb8f-104">Syntax</span></span>  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdb8f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fdb8f-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="fdb8f-106">[out] Ein Zeiger auf die Adresse eines [ICorDebugAppDomainEnum,](icordebugappdomainenum-interface.md) das ein Enumerator für die Anwendungsdomänen in diesem Prozess ist.</span><span class="sxs-lookup"><span data-stu-id="fdb8f-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdb8f-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fdb8f-107">Remarks</span></span>  
 <span data-ttu-id="fdb8f-108">Diese Methode kann vor dem [ICorDebugManagedCallback::CreateProcess-Rückruf](icordebugmanagedcallback-createprocess-method.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fdb8f-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdb8f-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fdb8f-109">Requirements</span></span>  
 <span data-ttu-id="fdb8f-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdb8f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdb8f-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdb8f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdb8f-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdb8f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdb8f-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdb8f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
