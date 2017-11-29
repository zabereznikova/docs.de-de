---
title: ICorDebugThread2::GetVolatileOSThreadID-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2.GetVolatileOSThreadID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2::GetVolatileOSThreadID
helpviewer_keywords:
- GetVolatileOSThreadID method [.NET Framework debugging]
- ICorDebugThread2::GetVolatileOSThreadID method [.NET Framework debugging]
ms.assetid: f0922545-c2cf-40c8-9ef6-ca033563e682
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ef0df7caad2e903e9325eb692fd318bec0c2c78
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread2getvolatileosthreadid-method"></a><span data-ttu-id="a1a58-102">ICorDebugThread2::GetVolatileOSThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="a1a58-102">ICorDebugThread2::GetVolatileOSThreadID Method</span></span>
<span data-ttu-id="a1a58-103">Ruft den Threadbezeichner des Betriebssystems für diesen ICorDebugThread2 ab.</span><span class="sxs-lookup"><span data-stu-id="a1a58-103">Gets the operating system thread identifier for this ICorDebugThread2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1a58-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1a58-104">Syntax</span></span>  
  
```  
HRESULT GetVolatileOSThreadID (  
    [out] DWORD    *pdwTid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1a58-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1a58-105">Parameters</span></span>  
 `pdwTid`  
 <span data-ttu-id="a1a58-106">[out] Der Threadbezeichner des Betriebssystems für diesen Thread.</span><span class="sxs-lookup"><span data-stu-id="a1a58-106">[out] The operating system thread identifier for this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1a58-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1a58-107">Requirements</span></span>  
 <span data-ttu-id="a1a58-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1a58-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1a58-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1a58-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1a58-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1a58-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1a58-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1a58-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
