---
title: ICorDebugProcess::ModifyLogSwitch-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.ModifyLogSwitch
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e5fb515229c566ee47bf99fe1a5985389e2a425
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="2b546-102">ICorDebugProcess::ModifyLogSwitch-Methode</span><span class="sxs-lookup"><span data-stu-id="2b546-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="2b546-103">Legt den Schweregrad der angegebenen Log-Schalter.</span><span class="sxs-lookup"><span data-stu-id="2b546-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b546-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b546-104">Syntax</span></span>  
  
```  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b546-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b546-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="2b546-106">[in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Log-Schalter angibt.</span><span class="sxs-lookup"><span data-stu-id="2b546-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="2b546-107">[in] Der Schweregrad für die angegebene Log-Schalter festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2b546-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b546-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b546-108">Remarks</span></span>  
 <span data-ttu-id="2b546-109">Diese Methode ist nur gültig, nachdem die [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2b546-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b546-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b546-110">Requirements</span></span>  
 <span data-ttu-id="2b546-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b546-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b546-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b546-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b546-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b546-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b546-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b546-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
