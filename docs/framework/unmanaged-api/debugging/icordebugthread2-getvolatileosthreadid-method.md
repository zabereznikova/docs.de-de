---
title: ICorDebugThread2::GetVolatileOSThreadID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetVolatileOSThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetVolatileOSThreadID
helpviewer_keywords:
- GetVolatileOSThreadID method [.NET Framework debugging]
- ICorDebugThread2::GetVolatileOSThreadID method [.NET Framework debugging]
ms.assetid: f0922545-c2cf-40c8-9ef6-ca033563e682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e6798c2574167ec1a013429b380d8fa6c878dad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416562"
---
# <a name="icordebugthread2getvolatileosthreadid-method"></a><span data-ttu-id="461b5-102">ICorDebugThread2::GetVolatileOSThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="461b5-102">ICorDebugThread2::GetVolatileOSThreadID Method</span></span>
<span data-ttu-id="461b5-103">Ruft den Threadbezeichner des Betriebssystems für diesen ICorDebugThread2 ab.</span><span class="sxs-lookup"><span data-stu-id="461b5-103">Gets the operating system thread identifier for this ICorDebugThread2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="461b5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="461b5-104">Syntax</span></span>  
  
```  
HRESULT GetVolatileOSThreadID (  
    [out] DWORD    *pdwTid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="461b5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="461b5-105">Parameters</span></span>  
 `pdwTid`  
 <span data-ttu-id="461b5-106">[out] Der Threadbezeichner des Betriebssystems für diesen Thread.</span><span class="sxs-lookup"><span data-stu-id="461b5-106">[out] The operating system thread identifier for this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="461b5-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="461b5-107">Requirements</span></span>  
 <span data-ttu-id="461b5-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="461b5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="461b5-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="461b5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="461b5-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="461b5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="461b5-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="461b5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
